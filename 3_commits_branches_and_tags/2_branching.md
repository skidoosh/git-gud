## A Beginner's Guide to Git Branches: Creating Your Own Paths

This guide will walk you through creating branches in Git, a crucial skill for collaborative software development and managing different features or fixes. We'll focus on creating branches *off* the `main` branch.

**What are Branches?**

Git branches are parallel lines of development of the `main` line. The `main` (or `master`) branch represents the stable, production-ready version of your code. 

Branches allow you to work on new features, or bug fixes, *without* directly affecting the main codebase.  When you're done with your work on a branch, you can merge it back into the `main` branch.

**Let's Git Started!**

Navigate to `~/projects` and execite the following commands:

```bash
mkdir branches
cd branches
git init
```

Now we have a new, local repository ready to start staging changes and creating commits! Before we create a branch, let's add a file, stage, and commit the changes:

```bash
echo "Ready to branch out" > README.md
git add README.md
git status
git commit -m "Initial commit"
```

**1. Checking Your Current Branch:**

Before creating a branch, it's good to know which branch you're currently on and *ideally* only branch from `main`. Use the following command:

```bash
git branch
```

You'll see a list of branches in your repository. The current branch will have an asterisk (*) next to it.

**2. Creating a New Branch:**

The core, but not the best command to create a new branch is `git branch`.  Let's say you want to add a "quick-fix" to your project. You would create a branch named `quick-fix` like this:

```bash
git branch quick-fix
```

This command *creates* the `quick-fix` branch, but it **doesn't switch to it**. You are still on the `main` branch.

**3. Switching to Your New Branch:**

To start working on the `quick-fix` branch, you need to *switch* to it. Use the `git checkout` command:

```bash
git checkout quick-fix
```

You'll see a message like "Switched to branch 'quick-fix'".  Now, when you make changes and commit them, they will be saved on the `quick-fix` branch, not on the `main` branch.

**Shortcut: Creating and Switching in One Step:**

You can combine the `git branch` and `git checkout` commands into a single command using `git checkout -b`:

```bash
git checkout -b quick-fix
```

This command does the same thing as creating the branch with `git branch` and then switching to it with `git checkout`.  `-b` stands for "branch".

**4. Making Changes and Committing:**

Now that you're on the `quick-fix` branch, you can start making changes to your project.  Let's add a new file:

```bash
echo "This is the new feature content" > new_feature.txt
git add new_feature.txt
git commit -m "Added new feature file"
```

**5. Verifying Your Branch:**

To confirm you're on the correct branch and your changes are saved there, use `git branch` again:

```bash
git branch
```

You should see the asterisk (*) next to `quick-fix`, indicating that you're currently on that branch.

**6. Switching Back to the Main Branch:**

When you're finished working on your feature, you'll likely want to merge it back into the `main` branch.  But first, switch back to the `main` branch:

```bash
git checkout main
```

**Important to note:**

As of Git 2.23.0, two new command were introduced `switch` and `restore`. They were introduced to give users a simpler interface to the capabilities `checkout` provides. 

**Summary of Commands:**

* `git branch`: Lists all branches in your repository, showing the current branch with an asterisk (*).
* `git branch <branch_name>`: Creates a new branch named `<branch_name>`.
* `git checkout <branch_name>`: Switches to the branch named `<branch_name>`.
* `git checkout -b <branch_name>`: Creates a new branch named `<branch_name>` and switches to it.
* `git checkout main`: Switches back to the main branch.
* `git pull origin main`: Pulls changes from the remote `main` branch to your current branch.