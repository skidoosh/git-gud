Git authenticates using ssh public key authentication. If you haven’t already done so, follow the steps below.

**Step 1: Generate an SSH Key Pair**

* Open the terminal 
* Use the following command and hit enter to begin the interactive key generation process. Again, replace the content of the quotes with your own information:

  ```bash
  ssh-keygen -t ed25519 -C "glyn.mooney@capgemini.com"
  cat ~/.ssh/id_ed25519.pub 
  ```

  The above command will generate a public, and private key with the following names:

  * Private key: id_ed25519 (keep it secret, keep it safe)
  * Public key: id_ed25519.pub

  The `cat` command will output your public key component to the terminal. We'll need this in the following steps.

**Step 2: Install your new public key into GitGub**

* While logged into GitHub, visit the following [address](https://github.com/settings/ssh/new).
*   You will be presented with a form, with the title "Add new SSH Key" with the following fields:
  *   **Title:** Enter a sensible, and sensical name for the key
  *   **Key type:** Select "Authentication Key"
  *   **Key** Copy the output of the `cat` command from above. 

      It will start with `ssh-ed25519` and end with the quoted content from the above `ssh-keygen` command. Copy and paste the whole string. 
  * Click the **Add SSH Key** button.

