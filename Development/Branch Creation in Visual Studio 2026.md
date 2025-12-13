# Creating a Branch in Visual Studio 2026

Visual Studio 2026 is the latest version of Visual Studio. The Git integration features for branch creation follow the same robust process as its immediate predecessors (Visual Studio 2022).

## Recommended Steps to Create a Branch

1. **Open your repository**: Ensure you have a previously created or cloned Git repository open in Visual Studio.
2. **Access the "New Branch" dialog**: You have two primary options:
    - **Menu Bar**: In the menu bar in the upper left-hand corner of the window — go to the "**Git**" menu and then choose the "**New Branch**" option in the menu.
    - **Current Branch Menu**: In the bottom right-hand corner of the window — click the current branch name in the status bar and then select **New Branch** button.
3. Submit "New Branch" dialog
   ![[vs-2026-new-branch-dialog.png]]
	- **Enter a name**: In the **Create a new branch** dialog box, enter a [branch name following our naming convention](Branch%20Naming%20Conventions.md).
	- **Select the base branch**: Use the **Based on** drop-down list to choose the existing local or remote branch from which your new branch will start (`main` should be used the majority of the time).
	- **Choose checkout behavior: The **Checkout branch** checkbox is selected by default, which automatically switches your working context to the newly created branch. Uncheck this only if you want to remain in your current branch. The majority of the time you should leave this checked.
	- **Create the branch**: Select the **Create** button to finalize the process.





