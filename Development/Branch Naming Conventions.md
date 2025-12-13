# Best Practices for Branch Naming Conventions

A crucial aspect of using Git effectively is the proper usage and naming of branches. This  document outlines the naming convention that should be used when creating a new feature branches.
### Benefits

- **Clear Communication**: The branch name alone should provide a clear understanding of the code change's purpose.
- **Scalability**: Works well in large teams where many developers are working on different tasks simultaneously.
- **Automation**:  We should be able to add triggers to our CI/CD Integration based on the naming conventions outlined in this document.

## 1. Core Principles

* **`main` is Always Deployable:** The `main` branch should always contain production-ready code and be able to be deployed to production at anytime.
* **Create Branches from `main`:** When starting new work (feature, bugfix, etc.), create a new  branch from the latest `main` branch.
* **Commit Early and Often:** New work should be committed to your local branches early and you should regularly push work to the remote.
* **Review Pull Requests (PRs) Early:** This facilitates collaboration and early feedback. PRs should be created after the developer has verified their changes work locally.
* **Merge after Review** Code should only be merged into `main` after a peer review.

## 2. Branch Naming Conventions

Branch names (or titles) should be made up of 3 separate sections that are separated by forward slashes (/). 

``` markdown
{type}/{author}/{description}
```

| **Argument**    | **Description**                                                             |
| --------------- | --------------------------------------------------------------------------- |
| `{type}`        | Branch Type — standard values indicating the type of branch.                |
| `{author}`      | Branch Author — initials of the author for context of the owner.            |
| `{description}` | Branch Description — short title that describes why the branch was created. |

### Basic Rules

1. **Lowercase**: All alphabetic characters should be lowercase.  For example, `feature/fl/t-988-add-login` or `bugfix/fl/issue-987-business-rule-missing`.
2. **Alphanumeric Characters:** Use only alphanumeric characters (a-z, A-Z, 0–9), forward slashes and hyphens in the name of branches. Avoid punctuation, spaces, underscores, or any non-alphanumeric character. **Exception:** Release branches may include dots (`.`) for version numbers.

### Section 1: Branch Type Rules

1. **No Spaces**: The branch prefix should be a single word.
2. **Standard Prefixes:** Common prefixes in branch names helps us quickly identify the purpose of the branches. Here are some types of branches with their corresponding prefixes:
	- **Feature Branches:** These branches are used for developing new features. Use the prefix **`feature/`** (or **`feat/`**). For example, `feature/js/t-678-login-page` or `feat/js/t-486-logout-page`.
	- **Proof-of-Concepts**: These branches are experiments outside of an issue/ticket. Use the prefix **`poc/`**. For example, `test/jd/no-ref-shared-cache`.
	- **Bugfix Branches:** These branches are used to fix bugs in the code. Use the prefix **`bugfix/`** (or **`fix/`** ). For example, `bugfix/js/t-432-header-styling`.
	- **Hotfix Branches:** These branches are made directly from the production branch to fix critical bugs in the production environment. Use the prefix **`hotfix/`**. For example, `hotfix/jd/issue-432-critical-security-issue`.
	- **Release Branches:** These branches are used to prepare for a new production release. Use the prefix **`release/`**. For example, `release/jd/no-ref-v1.0.1`.
	- **Documentation Branches:** These branches are used to write, update, or fix documentation e.g. the README.md file. Use the prefix **`docs/`**. For example, `docs/jd/no-ref-api-endpoints`.

### Section 2: Branch Author Rules

1. **Use Your Initials or Full Name**: Choose one style and use it consistently for all your branches. Identify yourself using either:
	- Your initials: `feature/jd/t-123-add-login`
	- Your full name: `feature/john-doe/t-123-add-login`
2. **No Spaces**: Use hyphens (-) to separate your first name and last name.  For example, `feature/john-doe/add-login` or `bugfix/jane-smith/business-rule-missing`.
3. **Lowercase Only**: Use lowercase letters (e.g., `jd` not `JD`, `john-doe` not `John-Doe`).

### Section 3: Branch Description Rules

1. **No Spaces**: Use hyphens (-) to separate words instead of spaces.  For example, `feature/jd/issue-34-add-login` or `bugfix/js/t-43-business-rule-missing`.
2. **Keep It Clear and Concise**: The branch description should be descriptive yet concise, clearly indicating the purpose of the work.  Avoid generic terms like `update`, `changes`, or `stuff`.
3. **Include Ticket Number**: **Include Ticket Number**: Your description should start with the ticket reference from your project management system. Use your ticketing system's format (e.g., `t-123`, `issue-432`, `jira-456`).  For example, if you are working on a ticket number “T-123” and it is related to adding a password to the log-in page, the branch name could be `feature/jd/t-123-add-password`. 
	* **Include No Reference**:  When there is no ticket to reference, use `no-ref` instead of the ticket number to indicate the changes were not caused by a ticket. For example, `hotfix/jd/no-ref-registration-form-broken` indicates that a ticket doesn't exist yet for the production issue. 

## Examples

### Good Branch Names ✓
- `feature/jd/t-456-user-authentication`
- `bugfix/sarah-jones/issue-789-fix-login-redirect`
- `hotfix/mk/no-ref-critical-payment-bug`
- `release/js/no-ref-v2.1.0`
- `docs/ab/t-234-update-api-documentation`
- `test/jd/no-ref-redis-caching-experiment`

### Bad Branch Names ✗
- `feature/new-stuff` ❌ (no author, vague description)
- `Feature/JD/add_login` ❌ (uppercase, underscores)
- `jd-feature-login` ❌ (wrong format)
- `feature/jd/login page with spaces` ❌ (spaces)
- `fix-bug` ❌ (missing author and proper structure)
