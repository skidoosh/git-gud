## A Beginner's Guide to Git Stash: Saving Your Work in Progress

From time to time.. That's a lie. A lot of the time, you will be working on a new feature, or fix and your Supreme Leader, will come crashing in to your life with a *new* high priority ticket! You'll likely have code, not ready to commit as it is half written, and untested. Don't panic though, Git has your back!

Let's Git Started!

1.  **Stashing Your Changes:**

    The most basic way to stash your changes is with the git stash command:

    ```bash
    git stash
    ```

    This command does the following:
    * Saves Unstaged and Staged Changes: It saves both your staged (added to the index) and unstaged changes.
    *  Cleans Your Working Directory: It reverts your working directory to the state of the last commit. Your files will appear as if you hadn't made any changes since that last commit.

2.  **Viewing Your Stash List:**

    You can see a list of all your stashes with:

    ```bash
    git stash list
    ```

    This will display a list of your stashes, each identified by an index (e.g., stash@{0}, stash@{1}).  The list also includes a brief description of the changes stashed.

3.  **Applying Stashed Changes:**

    To apply the most recent stash (stash@{0}) to your working directory:

    ```bash
    git stash apply
    ```
    
    This will attempt to merge the stashed changes into your current working directory. If there are conflicts (changes that overlap with existing files), you'll need to resolve them manually.

    To apply a specific stash (e.g., stash@{1}):

    ```bash
    git stash apply stash@{1}
    ```

4.  **Popping Stashed Changes (Applying and Removing):**

    git apply leaves the stash in your list. If you want to apply the changes and remove the stash from the list, use git pop:

    ```bash
    git stash pop
    ```
    
    Or to apply a specific stash and remove it:

    ```bash
    git stash pop stash@{1}
    ```

    git pop also attempts to merge the stashed changes into your current working directory. If there are conflicts, again you'll need to resolve them manually.

5.  **Stashing with a Message:**

    You can add a message to your stash, making it easier to remember what changes were stashed:

    ```bash
    git stash save "My work in progress on feature X"
    ```

    This is highly recommended, especially when you have multiple stashes.  The message will be displayed in git stash list.

6.  **Stashing Untracked Files:**

    By default, git stash doesn't include untracked files (files that Git isn’t tracking yet). To stash them too, use the -u or --include-untracked flag:

    ```bash
    git stash -u save "Stashing with untracked files"
    ```

7.  **Stashing Ignored Files:**

    To include ignored files (files listed in your .gitignore file), use the -a or --all flag:

    ```bash
    git stash -a save "Stashing with ignored files"
    ```

8.  **Creating a Branch from a Stash:**

    Sometimes, you might stash changes because you realise they belong in a new branch. You can create a new branch from a stash:

    ```bash
    git stash branch <branch_name> stash@{0}
    ```
    
    This command creates a new branch named <branch_name>, checks out that branch, and applies the changes from stash@{0}.  The stash is then removed from the list.

9. **Clearing Your Stash List:**

  To remove all stashes from your stash list:

  ```bash
  git stash clear
  ```

  **Summary of Commands:**

* `git stash`: Stashes your changes (unstaged and staged).
* `git stash save "<message>"`: Stashes your changes with a message.
* `git stash list`: Lists all stashes.
* `git apply`: Applies the most recent stash (stash@{0}).
* `git pop`: Applies and removes the most recent stash.
* `git stash branch <branch_name> stash@{0}`: Creates a new branch from a stash.
* `git stash clear`: Clears the entire stash list.
