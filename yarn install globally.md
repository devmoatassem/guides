### Setup EC2 Instance

```bash
sudo apt update
sudo apt upgrade
```

# Yarn install globally

Here's how you can do it:

Ensure you have Node.js installed:

### To install Yarn, you can use the Yarn package manager's installation script:

```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list
sudo apt update
sudo apt install yarn
```

### Ensure Yarn's global bin is in your PATH:

Add Yarn's global binary directory to your PATH. You can add the following line to your ~/.bashrc or ~/.zshrc file, depending on your shell:

```
export PATH="$PATH:`yarn global bin`"
```

After adding this line, reload your shell configuration:

```
source ~/.bashrc

# or

source ~/.zshrc
```
## PATH change permanent
To make the PATH change permanent, you need to add the export command to your shell's configuration file. This way, the PATH is updated every time you open a new terminal session. Here's how to do it:

### For Bash Shell

Open your .bashrc file in a text editor:

    nano ~/.bashrc

Add the following line at the end of the file:

    export PATH="$PATH:$(yarn global bin)"

Save the file and exit the text editor (in nano, press CTRL + X, then Y, then Enter).

Reload the .bashrc file to apply the changes immediately:

    source ~/.bashrc

### For Zsh Shell

If you are using zsh, you need to modify the .zshrc file instead:

Open your .zshrc file in a text editor:

    nano ~/.zshrc

Add the following line at the end of the file:

    export PATH="$PATH:$(yarn global bin)"

Save the file and exit the text editor (in nano, press CTRL + X, then Y, then Enter).

Reload the .zshrc file to apply the changes immediately:

    source ~/.zshrc

#### For Other Shells

If you are using a different shell, modify the appropriate configuration file (e.g., .profile, .bash_profile, etc.).
Verifying the Change

After making these changes, you can verify that the PATH has been updated by opening a new terminal window and running:

    echo $PATH

This should include the path returned by yarn global bin.