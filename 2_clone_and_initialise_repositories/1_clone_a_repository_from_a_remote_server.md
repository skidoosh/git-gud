Now that we're setup, configured and redy to authenticate we can clone out first repository from a remote server. This one, to be precise.

**1. Find the Repository on GitHub:**

*   Open a web browser 
*   Navigate to [https://github.com/skidoosh/git-gud](https://github.com/skidoosh/git-gud)

**2. Locate the "Code" Button:**

*   On the repository's main page (the one you just navigated to), look for a green button labeled **"Code"**.

**3. Copy the Repository URL:**

*   Click on the **"Code"** button.
*   A dropdown menu will appear.  You'll see options for "HTTPS", "SSH", and potentially a "GitHub CLI" option.
*   Choose SSH, and copy the URI

**4. Navigate to Your Desired Directory:**

*   Open the terminal (terminal openings will continue, until morale improves)
*   Use the `cd` command (change directory) to navigate to the folder on your computer where you want to store the cloned repository.  

    For example, I like to store repositories in ~/projects. For this example, we will create and navidate to the directory.

    Use the following command to create the directory:

    ```bash
    mkdir ~/projects
    ```

    And the following command to navigate to it:

    ```bash
    cd ~/projects
    ```

**5. Clone the Repository:**

*   Now, use the `git clone` command followed by the URL you copied in step 3:

    ```bash
    git clone git@github.com:skidoosh/git-gud.git
    ```

*   Press Enter. Git will start downloading the repository's files and history to your computer. You'll see progress messages in the terminal as it downloads.

**6. Done!**

*   Once the cloning process is complete, you'll see a message indicating that the repository has been cloned successfully. A new folder with the same name as the repository will have been created in your chosen directory, containing all the files and history.