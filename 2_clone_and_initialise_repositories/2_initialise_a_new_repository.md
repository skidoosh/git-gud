In addition to cloning an existing repository, it is important that you know how to create your own from scratch. 
Let's Git to it!

**Stage 1: Basic Repository Initialisation & Status Check**

*   **Create a Project Directory:**
    *   Create an empty directory in the `~/projects` directory using the following commands:

    ```bash
    mkdir ~/projects/my_first_repository
    ```

    Then navigate to it using the following command:

    ```bash
    cd ~/projects/my_first_repository
    ```

*   **Initialise the Repository:**
    *   Type `git init` and press enter.  This creates a hidden `.git` directory within your project folder, 
        which is where Git stores its metadata and history.
    *   You should see a message like "Initialised empty Git repository in `~/projects/my_first_repository/.git/`"

*   **Check the Status:**
    *   Type `git status` and press enter.  You'll see a message indicating that the repository is clean, but it's 
        untracked.  This means Git isn't monitoring any files yet.
        ```bash
        On branch main

        No commits yet

        nothing to commit (create/copy files and use "git add" to track)
        ```

*   **Create a File:**
    *   Create a simple text file called `README.md` in your project directory using the following command:
        ```bash
        echo "Hello, Git\!" > README.md
        ```

*   **Check Status Again:**
    *   Run `git status` again.  You should now see that `README.md` is untracked.
        ```bash
        On branch main

        No commits yet

        Untracked files:
          (use "git add <file>..." to include in what will be committed)
	        README.md

        nothing added to commit but untracked files present (use "git add" to track)
        ```
  *   **Stage The Change:**
      *   To begin tracking the file in Git, execute the following command in the terminal:

          ```bash
          git add README.md
          ```

      *   Run the `git status` command again to see that the file is now being tracked and is ready to be commited.
          ```bash
              On branch main

              No commits yet

              Changes to be committed:
                (use "git rm --cached <file>..." to unstage)
                      new file:   README.md
          ```
