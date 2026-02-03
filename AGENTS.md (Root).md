## 1. Agent Purpose
This is a personal knowledge vault organized around software development and architecture decisions. All files are Markdown with YAML frontmatter.  Agents can use this repository of markdown files as its authoritative knowledge base.  Each file represents a specific domain concept, workflow, glossary term, or architectural guideline.

The agent may fetch these files via HTTP to gain additional context when answering questions.

---

## 2. Folder Map
- `/analysis/` — XXXX
- `/design/` — Evergreen reference material (patterns, cheat sheets, APIs).
- `/development/` — Architecture Decision Records (ADRs). **Always check here before
  suggesting a technology or pattern choice — I may have already made a decision.**
- `/maintenance/` — XXXX**
- `/planning/` — XXXX
- `/security/` — XXXX
- `/templates/` — SDLC templates. Do not modify these.
- `/testing/` — XXXX

The key insight: you're writing *instructions for an agent*, not documentation for a human. Be imperative and specific.

## 3. Per-Folder AGENTS.md Files

This is where it gets powerful. Each major folder gets its own AGENTS.md that provides local context. This keeps the root file from becoming a monolith and lets you maintain context close to the content it describes.

```
vault/
├── AGENTS.md              ← top-level routing
├── decisions/
│   ├── AGENTS.md          ← "ADRs are numbered, use template ADR-TEMPLATE.md"
│   ├── 001-use-autofac.md
│   └── 002-cqrs-pattern.md
└── references/
    ├── AGENTS.md          ← "these are evergreen, treat as authoritative"
    └── csharp-patterns.md
```

## 4. Knowledge Index

### Glossary
- **glossary/pipelines.md**  
  Topic: `pipelines`  
  Description: Defines pipeline architecture, responsibilities, and mental models.

- **glossary/dto.md**  
  Topic: `dto`  
  Description: Defines DTO conventions, naming rules, and serialization expectations.

- **glossary/viewmodels.md**  
  Topic: `viewmodels`  
  Description: Defines ViewModel responsibilities, mapping rules, and UI contract boundaries.

### Architecture
- **architecture/naming-conventions.md**  
  Topic: `naming`  
  Description: Strong naming conventions for classes, services, DTOs, and files.

- **architecture/inheritance-patterns.md**  
  Topic: `inheritance`  
  Description: Approved inheritance patterns, base classes, and anti-patterns.

### Workflows
- **workflows/climatology-pipeline.md**  
  Topic: `climatology`  
  Description: Workflow for NOAA ingestion, aggregation, and metric computation.

### 5. Key Documents
| Document                         | Purpose             | Consult When                                 |
| -------------------------------- | ------------------- | -------------------------------------------- |
| `/decisions/001-use-autofac.md`  | DI container choice | User asks about dependency injection         |
| `/references/csharp-patterns.md` | C# idioms I follow  | Writing or reviewing C# code                 |
| `/projects/my-api/README.md`     | Current API project | Any question about "the API" or "my project" |
| `/references/git-workflow.md`    | Branching strategy  | Git operations or PR questions               |

---

## 6. Tool: fetch_markdown_file

### Name
`fetch_markdown_file`

### Description
Retrieves the raw contents of a markdown file from the repository.

### Parameters
- `path` (string): The relative path to the markdown file (e.g., `glossary/pipelines.md`)

### Returns
- Raw markdown text

### URL Template
```
https://raw.githubusercontent.com/Matt402NE/sdlc/main/{path}
```

---

## 7. Retrieval Policy

The agent should fetch a markdown file when:
- A user asks about a topic that maps to a known file topic
- The agent needs authoritative definitions, conventions, or workflows
- The agent is unsure about a domain-specific term
- The agent needs to verify naming, responsibilities, or architectural rules

The agent should **not** fetch files when:
- The answer is clearly available from prior context
- The user is asking for creative brainstorming
- The topic is unrelated to the repository

---

## 8. Topic → File Resolution Rules

When the user asks about a topic:
1. Identify the topic keyword  
2. Match it to the Knowledge Index  
3. Select the corresponding file path  
4. Call `fetch_markdown_file(path)`  
5. Use the file contents as authoritative context  

Examples:
- Topic: “DTO” → `glossary/dto.md`
- Topic: “naming conventions” → `architecture/naming-conventions.md`
- Topic: “climatology pipeline” → `workflows/climatology-pipeline.md`

---

## 9. Reasoning Pattern Before Fetching

Before calling the fetch tool, the agent should:
1. Determine whether the user’s question requires authoritative reference
2. Identify the most relevant topic
3. Confirm that a matching file exists
4. Fetch only the single most relevant file
5. Use the file contents to answer the question clearly and accurately

---

## 10. Constraints
- The agent must only fetch files listed in the Knowledge Index
- The agent must not guess file paths
- The agent must treat the markdown files as the source of truth


