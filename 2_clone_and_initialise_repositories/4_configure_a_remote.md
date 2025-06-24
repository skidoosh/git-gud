In order to collaborate with your team, or simply make your code accessible to another service like a CI/CD pipeline we must first store it in a place accessible over the network. In this section we will learn the basics of configuring your local repository to store changes to a remote location.

**Understanding Remote Origins**

* **What is a remote?** In Git, a "remote" is essentially a pointer to another repository.  It's how you connect your local Git repository to an online (or network accessible) repository.
* **What is `origin`?**  `origin` is a *convention* like calling your primary branch `main` or `master`. It's the most common name given to the primary remote repository you're working with.  You *could* name it something else (like `upstream` or `myremote`), but using `origin` is highly recommended for clarity and compatibility with tools.
* **Why set the remote origin?**  Setting the remote origin allows you to:
    * **Push:** Send your local commits to the online repository.
    * **Pull:** Download changes from the online repository into your local copy.
    * **Clone:**  If you're starting a new project, cloning automatically sets the origin.

**Setting the Remote Origin**

Here's how to set the remote origin to point to your newly created GitHub repository:

**Scenario 1: Existing local Git repository, but no remote set**

A common scenario. When you've begun to create something, you may decide to share it with your team, or make it accessible to services over the network.

1. **Open your terminal:** Navigate to the root directory of your local Git repository using the `cd` command:

   ```bash
   cd ~/projects/my_first_repository
   ```

2. **Add the remote origin:**  Use the `git remote add` command:

   ```bash
   git remote add origin git@github.com:yourusername/my_first_repository.git
   ```

   * `git remote add`:  This is the command to add a new remote.
   * `origin`: This is the name you're giving to the remote (as explained above).
   * `git@github.com:yourusername/my_first_repository.git`: This is the URL of your GitHub repository.  **Remember to change `yourusername` to your GitHub username.**

3. **Verify the remote:**  Confirm that the remote has been added correctly:

   ```bash
   git remote -v
   ```

   You should see output similar to the following:

   ```
   origin  git@github.com:yourusername/my_first_repository.git (fetch)
   origin  git@github.com:yourusername/my_first_repository.git (push)
   ```

   The `(fetch)` and `(push)` indicate that you can both download (fetch) and upload (push) changes to this remote.

**Scenario 2: You have an existing local Git repository *with* a remote, but you want to change it.**

* **Why set a new remote origin?**  Setting the remote origin allows you to:
    * **Migration:** You're moving to a new Git provider e.g. GitHub to BitBucket
    * **Disaster Recovery:** Your provider has been wiped off the face of the earth, and you need to migrate!
    * **Renaming:** You're renaming an existing project, and you want the repository to be consistent with the new name.
    

1. **Open your terminal** Navigate to the root directory of your local Git repository.

   ```bash
   cd ~/projects/my_first_repository
   ```

2. **Remove the existing remote:**  Use `git remote remove`:

   ```bash
   git remote remove origin
   ```

3. **Add the new remote:**  Follow step 2 from Scenario 1:

   ```bash
   git remote add origin git@github.com:yourusername/my_second_repository.git
   ```

4. **Verify:** Use `git remote -v` to confirm the change.

**Scenario 3: You're starting a new project and want to connect it directly to GitHub.**

This is the easiest scenario.  You'll use `git clone` with the correct repository URL.

1. **Open your terminal/command prompt.**

2. **Clone the repository:**  Use `git clone`:

   ```bash
   git clone git@github.com:yourusername/my_third_repository.git
   ```

   This will download the entire repository to your local machine and automatically set `origin` to point to `git@github.com:yourusername/my_third_repository.git`.

**After Setting the Remote Origin:**

Once you've successfully set the remote origin, you can start pushing and pulling changes:

* **Push your local commits to GitHub:** `git push origin main` (or whatever branch you're working on, like `master`).
* **Pull changes from GitHub:** `git pull origin main`
