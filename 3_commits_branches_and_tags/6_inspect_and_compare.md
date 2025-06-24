## A Beginner's Guide to Inspecting & Comparing Git Commits

This guide will walk you through inspecting individual commits and comparing them to each other in Git. Understanding commit history is crucial for debugging, understanding changes, collaborating, and automation.

**Let's Git Started!**

**1. Viewing Commit History:**

The first step is to see the history of your repository. The most common command for this is `git log`.

* **Basic Log:**

   ```bash
   git log
   ```

   This displays a chronological list of commits, showing the commit hash (SHA-1), author, date, and commit message.

* **Concise Log:**  For a more compact view:

   ```bash
   git log --oneline
   ```

   This shows each commit on a single line, displaying the shortened hash and the commit message.

* **Showing Graphically (Visual History):**  Git can display the commit graph visually, which is helpful for understanding branching and merging:

   ```bash
   git log --graph --oneline --decorate
   ```

   * `--graph`:  Displays the commit graph.
   * `--oneline`: Shows each commit on a single line (as before).
   * `--decorate`:  Shows branch and tag names associated with each commit.

**2. Inspecting a Single Commit:**

Once you're interested in a specific commit, you can inspect it to see the changes introduced by that commit.

* **`git show <commit_hash>`:** This is the primary command for inspecting a commit. Replace `<commit_hash>` with the SHA-1 hash of the commit you want to examine.

   ```bash
   git show 79fc70c
   ```

   `git show` displays the following information for the commit:

    * **Commit Hash:** The SHA-1 hash of the commit.
    * **Author and Date:** Who made the change and when.
    * **Commit Message:** The description of the changes.
    * **Diff (Patch):**  The actual code changes introduced by the commit, shown as a "diff" or "patch." This shows what lines were added, deleted, or modified.

* **`git show <commit_hash>`:**  This command does essentially the same thing as `git show`, but will only display the latest commit on the current branch`.

**3. Comparing Two Commits:**

Comparing two commits is useful for understanding the differences between versions of your code.

* **`git diff <commit_hash1>..<commit_hash2>`:** This command shows the differences between two commits.  `<commit_hash1>` is the "older" commit, and `<commit_hash2>` is the "newer" commit.

   ```bash
   git diff 57c3ca6..0149346
   ```

   The output is a "diff" showing the lines added, deleted, or modified between the two commits.

* **Comparing to HEAD (Current State):** You can compare a commit to the current state of your working directory (HEAD) or to another branch.

   * **`git diff <commit_hash>..HEAD`:**  Shows the differences between a specific commit and your current working directory.
   * **`git diff <branch_name>..HEAD`:** Shows the differences between a branch and your current working directory.

**4. Comparing Branches:**

Comparing branches is useful for seeing the differences between two lines of development.

* **`git diff <branch_name1>..<branch_name2>`:** Shows the differences between two branches.

   ```bash
   git diff main..develop  
   ```

**5. Using a Graphical Diff Tool (Optional):**

For more visual and interactive diffing, you can configure Git to use a graphical diff tool.  Many IDEs (like VS Code, IntelliJ IDEA) have built-in Git integration with graphical diff viewers.  You can also install standalone tools like Meld or DiffMerge.

**Summary of Commands:**

* `git log`: Shows commit history.
* `git log --oneline`: Concise commit history.
* `git show <commit_hash>`: Inspects a single commit.
* `git diff <commit1>..<commit2>`: Compares two commits.
* `git diff <branch1>..<branch2>`: Compares two branches.
