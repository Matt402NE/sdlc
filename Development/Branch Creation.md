# Overview of Branch Creation

Branch creation using Git is the process of creating an isolated copy of your codebase to work on new features, fixes, or experiments without affecting the main project.

You will need to define your `<new-branch-name>` based on [our branch naming convention](Branch%20Naming%20Conventions.md).
### Key Git Commands for Branch Creation

- **`git branch <new-branch-name>`**: Creates a new branch but keeps you on your current one.
- **`git checkout <new-branch-name>`**: Switches to an existing branch.
	- **`git checkout -b <new-branch-name>`**: Creates the branch _and_ switches to it in one step (shortcut).
	- **`git checkout -b <new-branch-name> <base-branch>`**: Creates a new branch from a specific existing branch (e.g., `git checkout -b my-feature main`).
- **`git push -u origin <new-branch-name>`**: Pushes your new local branch to the remote repository (like GitHub).

## Branch Creation Methods

* [Branch Creation in Visual Studio 2026](Branch%20Creation%20in%20Visual%20Studio%202026.md)

