Git
===

This is a compilation of the things that I learnt while using Git in my projects.

Git Commands & Uses
-------------------------------

**Working with Git:**

 - To initialize a local Git repo in the laptop, `cd` to the desired directory and type `git init`. This will create a **.git** directory in your current directory which will host the history of all your changes.
 - To create a new branch, type `git branch <new-branch-name>`.
 - To switch from your current branch to another branch, type `git checkout <target-branch>`.
 - To stage (include in subsequent commits) newly created files & folders, type `git add <file-or-folder-name>`. If a folder is added, then all the files and folders within the added folder are added recursively. If you make changes after git add-ing your files, those new changes will not reflect in the commit automatically. You'll have to git add again before committing to including the new changes in the commit.
 - Commit the changes and new files & folders: `git commit -m "<commit-message>".`
 - Let's assume that you have a remote repository in GitHub. In order to link your newly created local repo to an existing remote repo, type `git remote add origin git@github.com:username/reponame.git`. This will link your remote repo in GitHub with your local repo. Your commits will not be available in the remote yet. You have to push your commits for that.
 - If you have a remote repo, and want to bring it down to your local machine, type `git clone <remote-repo-url> <local-repo-directory>`. All your files and folders from your remote repo with all the history will be pulled down to your local repo.
 - Push your changes to remote repo: `git push origin <branch>`. 
 - Set Upstream: You don't have type `origin` and `branch` every time you push; just set `origin` as  upstream for your `branch` with the command `git push --set-upstream origin <branch>`. Once you have set `origin` as upstream for a branch, you can simply type `git push` and your changes in the `branch` will pushed to remote repo.

**Configuring Git:**

 - To set your git user name: `git config user.name "Your Name"`. This will set the user name for the current directory's repo. In order to make this setting a global one i.e., across all git repos in your machine, use `git config --global user.name "Your Name"`.
 - To set your git user email: `git config user.email "your@email.com"`. This will set the user email for the current directory's repo. In order to make this setting a global one i.e., across all git repos in your machine, use `git config --global user.email "your@email.com"`.

**Using SSH keys to push:**

You can use your remote repo user account's user name and password to push your changes from local to remote repo. But there is another way to do it by usig *SSH key*.

 - First, you need to generate a new SSH key. Open *Git Bash* (I'm assuming that you are using Windows OS; Mac and Linux users need lookup how to generate SSH key from their OS).
 - In Git Bash, navigate to `~/.ssh/` directory and type `ssh-keygen -t rsa -b 4096 -C "<your-git-repo-email> -f "<filename>"`. You will prompted for a password - provide a password and **remember it** (you will be using this password everytime you push your changes to remote repo). This will generate private and public keys which will be saved in files with the `filename` that you mentioned in the command.
 - Now, you have to add your public key to your remote repo account. Login to GitHub, go to `Settings -> SSH and GPG keys` and copy paste your public key from the file.

> **NOTE:** When you generated the keys, two files would have been created. One file will contian your *private key* and the other will contain your *public key*. Add only your *public key* to GitHub. **Do not add your *private key* to remote repo account**.


