
# Managing Pull Requests in Visual Studio 2026 with Git

A pull request (PR) 

is a proposal to merge a set of changes from one branch into a target branch.

Branch Pull Request



### Step 3: Update your Local `main` Branch

You need to pull the latest changes from the remote repository and update your local `main` branch. You can perform a merge to download the latest changes.  Go to **Git Repository Window** and locate the remote main branch. Right-click on it can choose the "Merge 'origin/main' into 'main'" option in the menu.

![Screenshot of branch menu](vs-2026-remote-branch-merge.png)

### Step 4: Delete the Feature Branch

Once your local `main` branch is updated, you can safely delete both the local and the remote feature branch.  You should delete your local \[feature] branch first.  Then you can delete the feature branch on the remote.

To delete the local branch — go to **Git Repository Window**.  Locate your branch and right-click on it to get additional options.  You can choose the "Delete" option in the menu.

![Screenshot of branch menu](vs-2026-local-branch-delete.png)
Once you have deleted the branch locally — you can repeat the steps on the remote version of your \[feature] branch.

## Online Resources

These are additional resource that you can reference to learn more about this topic:

- Mads Kristensen, "Streamlining your Git workflow with Visual Studio 2026", December 10, 2025, https://devblogs.microsoft.com/visualstudio/streamlining-your-git-workflow-with-visual-studio-2026/