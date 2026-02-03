# Task Worksheet Template

## Purpose

This template defines the standard format for task worksheets. A task represents a concrete, actionable unit of work that can be completed in one sitting. Each worksheet is a single `.md` file representing one task category (e.g., "Weekly Personal," "One-Time Home," "Sprint B," "Project 123 Plan").

## When to Use

Create a new worksheet whenever a distinct category of work emerges that doesn't fit cleanly into an existing file. Prefer fewer, broader categories over many narrow ones.

`category-slug` is a lowercase, hyphenated version of the category name (e.g., `"Weekly Personal"` → `weekly-personal`).

## Frontmatter Reference

|Field|Required|Description|
|---|---|---|
|`category`|Yes|Human-readable category name|
|`recurrence`|Yes|`weekly`, `monthly`, or `none`|
|`reset-schedule`|If recurring|Parseable reset trigger (see grammar below)|
|`tags`|Yes|Always include `tasks/recurring` or `tasks/one-time`|
|`agent-hint`|Yes|One-line instruction for AI on when/how to use this file|
|`last-reset`|If recurring|Date of most recent reset (YYYY-MM-DD)|
|`updated`|Yes|Date of last modification (YYYY-MM-DD)|

### `reset-schedule` Grammar

The `recurrence` field defines the cycle (`weekly` or `monthly`). The `reset-schedule` field defines where in that cycle the reset falls. Values must conform to one of the following formats:

**When `recurrence: weekly`** — a lowercase day name:

```yaml
reset-schedule: monday
```

Allowed values: `monday`, `tuesday`, `wednesday`, `thursday`, `friday`, `saturday`, `sunday`

**When `recurrence: monthly`** — a day-of-month number or an ordinal-weekday pattern:

```yaml
# Fixed date
reset-schedule: 1
reset-schedule: 15

# Nth weekday
reset-schedule: 1st-monday
reset-schedule: 3rd-friday

# Last weekday
reset-schedule: last-friday
```

Day-of-month range is `1`–`28` (avoids end-of-month ambiguity). For end-of-month, use `last-<day-name>`.

```
reset-schedule ::= <day-name>                        # weekly
                 | <day-of-month>                     # monthly, fixed date
                 | <ordinal>-<day-name>               # monthly, nth weekday

day-name       ::= monday | tuesday | wednesday | thursday
                 | friday | saturday | sunday

day-of-month   ::= 1..28

ordinal        ::= 1st | 2nd | 3rd | 4th | last
```

## Section Rules

Not all sections apply to every worksheet. The `recurrence` field determines which sections are relevant:

|Section|`recurrence: weekly/monthly`|`recurrence: none`|
|:--|:--|:--|
|Focus|✅ Update each cycle|✅ Stable goal|
|Tasks|✅|✅|
|Completed|❌ Reset clears the slate|✅ Keep for reference|
|Backlog|❌ Recurring tasks are fixed|✅ Optional|

All worksheets use the heading `## Tasks`. **If a section doesn't apply, omit it entirely.** Do not leave empty sections.

Blocked tasks are not a separate section. They live in the main task list and always appear above unblocked tasks.

## Task Line Format

The default task is a single line:

```
- [ ] Task description
```

Task descriptions must fit on a single line; use sub-bullets for clarification.

Add inline metadata **only when the task needs it**. Do not include empty fields.

Add a plain sub-bullet for notes only when a task needs explanation:

```
- [ ] Fix leaky kitchen faucet [p:: high] [due:: 2025-02-15]
  - Plumber recommended by neighbor, needs to happen before guests visit
```

Do **not** add a notes sub-bullet to tasks that don't need one. When adding a sub-bullet note, consider whether it is evergreen (procedural context, permanent references) or cycle-specific (dates, names, one-time instructions). Evergreen notes are preserved across resets; cycle-specific notes are removed. Write accordingly.

### Checkbox Linting

Normalize malformed checkboxes when encountered:

- `[x ]` → `[x]`
- `[ x]` → `[x]`
- `[X]` → `[x]`
- `[X ]` → `[x]`
- `[ X]` → `[x]`
- `[]` → `[ ]`

### Available Inline Fields (Dataview syntax)

|Field|Syntax|When to Use|
|---|---|---|
|`p`|`[p:: high\|med\|low]`|Task priority. Omit for `med` (default)|
|`due`|`[due:: YYYY-MM-DD]`|Task has a real deadline|
|`blocked`|`[blocked:: reason or person]`|Task cannot proceed until dependency clears|
|`context`|`[context:: @home]`|Optional — useful for batching tasks by location or mode|

**Field order on a task line:** `[p::]` → `[due::]` → `[blocked::]` → `[context::]`. Not all fields will be present; maintain this order for the ones that are.

### Display Order

The agent maintains a consistent sort order within the task list:

1. **Blocked tasks** (any task with a `[blocked::]` field) — sorted among themselves by priority, then due date
2. **Unblocked tasks** — sorted by priority (`high` → `med` → `low`), then by due date (soonest first; undated tasks after dated ones within the same priority)

Blocked tasks always appear above all unblocked tasks, regardless of priority.

Tasks without a `[p::]` field are treated as `med` priority. New undated tasks within the same priority group are appended to the end of that group.

Overdue tasks (where `[due::]` is before today) are not modified, moved, or flagged automatically. Their past due date keeps them sorted near the top of their priority group per the existing date-sort rules.

The agent re-sorts **only** when:

- Adding a new task
- Modifying a `[p::]`, `[due::]`, or `[blocked::]` field on an existing task
- The user explicitly asks to re-sort or reorganize

The agent does **not** re-sort during unrelated edits such as updating frontmatter, editing sub-bullet notes, or checking/unchecking boxes.

## AI Agent Instructions

### Reset Behavior (Recurring Worksheets Only)

When asked to reset a recurring worksheet:

1. Uncheck all boxes (`[x]` → `[ ]`) in the Tasks section
2. Remove cycle-specific sub-bullets (dates, names, one-time instructions) but preserve evergreen notes (always-true procedures, permanent context)
3. Update `last-reset` in frontmatter to today's date
4. Update `updated` in frontmatter to today's date
5. Rewrite the Focus section if the user provides a new one
6. Do **not** remove or modify `[blocked::]` fields — blocked items carry over across cycles
7. If a task has a `[due::]` date in the past, retain it unchanged unless the user provides a new date

### Adding Tasks

- Add new tasks to the list in the correct sort position per the Display Order rules
- If the user does not specify a priority, omit `[p::]` (the task defaults to `med`)
- Add inline fields only if the user provides the information — never add empty `[due:: ]`, `[blocked:: ]`, or `[p:: ]` placeholders
- If the user says a task is blocked, add a `[blocked:: reason]` field and re-sort so the task appears in the blocked group at the top

### Completing Tasks

- Check the box: `[ ]` → `[x]`
- For `recurrence: none` worksheets, move completed tasks to the Completed section with a date stamp: `- [x] Task description — YYYY-MM-DD`
- For recurring worksheets, just check the box — it will be cleared on reset
- Do not reorder remaining tasks or change their priority when completing a task

### Querying Across Worksheets

When the user asks broad questions like "what's overdue?" or "what should I work on?", scan **all** task worksheets in the tasks folder:

- Filter out items with `[blocked::]` fields unless specifically asked about them
- Sort results by priority (`high` → `med` → `low`), then by `[due::]` date
- Ignore Backlog items unless the user specifically asks about them
- When the user asks "what's overdue?", return all tasks where `[due::]` is before today, excluding blocked and completed items, sorted by how overdue they are (oldest first)

### Archiving

When the Completed section exceeds ~15 items, suggest archiving older entries to a separate `{{category-slug}}-archive.md` file. Do not archive automatically.

---

## Recurring Worksheet Template

Use this template when `recurrence` is `weekly` or `monthly`. Omit Completed and Backlog sections. Tasks are retained between cycles so they can be reset (unchecked), not removed.

```markdown
---
category: {{Category Name}}
recurrence: {{weekly or monthly}}
reset-schedule: {{see grammar above}}
tags: [tasks/recurring, {{category-slug}}]
agent-hint: >
  {{One-line description of this checklist and its reset behavior.}}
last-reset: {{YYYY-MM-DD}}
updated: {{YYYY-MM-DD}}
---

# {{Category Name}} Tasks

## Focus
- {{One sentence about the main outcome you want this cycle.}}

## Tasks
<!-- Tasks without [p::] default to med priority. -->
- [ ] {{Task description}} [p:: high] [blocked:: {{reason}}]
  - {{Context explaining the blocker}}
- [ ] {{Task description}} [p:: high] [due:: {{YYYY-MM-DD}}]
- [ ] {{Task description}} [p:: high]
- [ ] {{Task description}} [due:: {{YYYY-MM-DD}}]
- [ ] {{Task description}}
- [ ] {{Task description}}
- [ ] {{Task description}} [p:: low]
- [ ] {{Task description}} [p:: low]
```

## One-Time Worksheet Template

Use this template when `recurrence` is `none`. Include Completed section. Backlog is optional.

```markdown
---
category: {{Category Name}}
recurrence: none
tags: [tasks/one-time, {{category-slug}}]
agent-hint: >
  {{One-line description of this task list and when it's relevant.}}
updated: {{YYYY-MM-DD}}
---

# {{Category Name}} Tasks

## Focus
- {{One sentence about the main outcome or goal.}}

## Tasks
<!-- Tasks without [p::] default to med priority. -->
- [ ] {{Task description}} [p:: high] [blocked:: {{reason}}]
  - {{Context explaining the blocker}}
- [ ] {{Task description}} [blocked:: {{reason}}]
- [ ] {{Task description}} [p:: high] [due:: {{YYYY-MM-DD}}]
  - {{Context or notes only if needed}}
- [ ] {{Task description}} [p:: high]
- [ ] {{Task description}} [due:: {{YYYY-MM-DD}}]
- [ ] {{Task description}}
- [ ] {{Task description}} [p:: low]

## Completed
> Completed tasks kept for reference.
- [x] {{Task description}} — {{YYYY-MM-DD}}
- [x] {{Task description}} — {{YYYY-MM-DD}}

## Backlog (Optional)
> Tasks you might do someday but don't want cluttering Active.
- [ ] {{Task description}}
- [ ] {{Task description}}
```