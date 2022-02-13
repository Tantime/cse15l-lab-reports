# Lab Report 3 - Setup GitHub Access from ieng6
*Author: Matthew Tan*

<br>

## Using a preexisting public key
First things first, check to see if you have a preexisting public SSH key. You can do this by entering `ls -al ~/.ssh` into the terminal.

> $ ls -al ~/.ssh 

This will list the files in your .ssh directory, if they exist. Check to see if a public SSH key currently exists. They will be under the names by default:
- id_rsa.pub
- id_ecdsa.pub
- id_ed25519.pub

Identify which public key you want to use and save for the next steps.

<br>

## Using a new SSH key
If you're like me and you don't already have a preexisting public key or you want to use a new one, you can create a new pair of public/private keys by opening the terminal and typing (with your GitHub email address in place of the example email):

> $ ssh-keygen -t ed25519 -C "your_email@example.com"

This generates a new public/private SSH key pair. Next, you will be prompted with:

> \> Enter a file in which to save the key(/Users/*you*/.ssh/*algorithm*): [*Press enter*]

You can either press enter to save the key to the default file location or customize the path to your liking. Then when prompted, assign a passphrase (leave blank for no passphrase) and press enter. 

> \> Enter a passphrase (empty for no passphrase): [*Type a passphrase*]

You will be asked to enter it once more for confirmation.

> \> Enter same passphrase again: [*Type passphrase again*]

This is what it looked like in my terminal:

(insert ss here)

<br>

## Adding your SSH key to the ssh-agent
Now that you have your public key ready, you can now add it to the ssh-agent. First, activate the ssh-agent in the background.

> \$ eval "$(ssh-agent -s)" <br>
\> Agent pid 59566 (replaced with your pid)

Depending on the terminal, you may need to use a different command. Common examples are needing to use `sudo -s -H` before starting the ssh-agent or using `exec ssh-agent bash` or `exec ssh-agent zsh` to run the ssh-agent.

First, check to see if your `~/.ssh/config` file exists in the default location.

> $ open ~/.ssh/config <br>
\> The file /Users/*you*/.ssh/config does not exist.

If the file doesn't exist, create the file.

> $ touch ~/.ssh/config

Open your `~/.ssh/config` file, then modify the file to contain the following lines. If your SSH key file has a different name or path than the example code, modify the filename or path to match your current setup.

> Host * <br>
&nbsp;&nbsp;&nbsp;&nbsp; AddKeysToAgent yes <br>
&nbsp;&nbsp;&nbsp;&nbsp; UseKeychain yes <br>
&nbsp;&nbsp;&nbsp;&nbsp; IdentityFile ~/.ssh/id_ed25519

If you're using macOS Sierra 10.12.2 or later, you will need to modify your ~/.ssh/config file to automatically load keys into the ssh-agent and store passphrases in your keychain. I had to do this, so refer to my screenshot below:

(insert both ss here)

Add your SSH private key to the ssh-agent and store your passphrase in the keychain. If you created your key with a different name, or if you are adding an existing key that has a different name, replace *id_ed25519* in the command with the name of your private key file.

> $ ssh-add -K ~/.ssh/id_ed25519

While this method does still work, I received a warning telling me that the -K flag is deprecated and has been replaced by the --apple-use-keychain command, so using that updated command will also work. Refer to the screenshot below:

(insert ss here)

<br>

## Adding SSH key to your GitHub account
In order to use your new/preexisting SSH key, you'll need to add the key to your GitHub.com account. Firstly, copy your SSH public key to your clipboard.

> $ pbcopy < ~/.ssh/id_ed25519.pub <br>
\# Copies the contents of the id_ed25519.pub file to your clipboard

Secondly, navigate to the settings of your GitHub.com account. In the `Access` section of the sidebar, click SSH and GPG keys.

Thirdly, click **New SSH key** or **Add SSH key**. In the `Title` field, add a descriptive label for the new key. For example, if you're using a personal Mac, you might call this key "Personal MacBook Air".

Finally, paste your key into the `Key` field and click **Add SSH key**. If prompted, confirm your GitHub password. After these steps, you should have successfully added your SSH key to your GitHub account!


<br>

<br>

##### Source: <a href="https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-key-and-adding-it-to-the-ssh-agent" target="_blank">GitHub Docs - Generating a new SSH key and adding it to the ssh-agent</a>