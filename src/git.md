# git

# Table of contents

- [git](#git)
    - [Installing git](#installing-git)
    - [Updating git](#updating-git)
    - [Creating a repo](#updating-git)
    - [Making changes](#making-changes)
    - [Syncing with GitHub](#syncing-with-github)
        - [Creating a GitHub repo](#creating-a-github-repo)
        - [Cloning a repo](#cloning-a-repo)
        - [Uploading commits](#uploading-commits)
        - [Creating a pull request (PR)](#creating-a-pull-request-pr)
        - [GitHub credential management](#github-credential-management)
    - [gitignore](#gitignore)
    - [git config](#git-config)
    
---

## Installing git
Download and install git from the [official website](https://git-scm.com/downloads/win).

---

## Updating git
Check your current version by running `git --version`.
If not up to date, download the latest version from the [official website](https://git-scm.com/downloads/win). This will automatically remove the previous version of git before installing the new one.  
After installing, check you are up to date, by again running `git --version`.

---

## Creating a repo
To create a repo, go to the directory you wish to make a git repo. In the terminal, run `git init`. This will initialise a git repo.  
A .git folder will be created, which Windows does not show you by default. I recommend checking the setting "show hidden files / folders" in the Windows file explorer to be able to see .git folders. This makes it easier, when using the file explorer GUI, to tell which directories are git repos, and which are not.  
You can check whether your git repo was correctly initialised by running `git status`.  
If you wish to change a local directory to _not_ be a managed by git, simply delete the .git folder for that directory.

---

## Making changes
In order to save changes, you must first choose which files withing the git repo you want to save. You can select all by using `git add .`, or choose specific files with `git add {filename}`.  
Once files have been "added", they are staged. Staged files can be committed by using `git commit -m "{commit message}"`. Alternatively, this can be done through the GUI on the VS Code git extension, but I prefer using the terminal.  
If after staging certain files, you decide you do not want to commit them, you can remove all staged files with `git reset`, or remove a specific file using `git reset <{filename}>`.

---

## Syncing with GitHub
It is useful to sync our git repos with external services such as GitHub. This is mainly for collaboration (but you can use it like I sometimes do, to 'sync' between different devices without using a cloud service).  

### Creating a GitHub repo
If you want to create a repo on GitHub, I usually create it on the GitHub website. Then, in the directory which I want to upload, I run `git init` (if not already initialised), and commit any changes if applicable. Then, `git remote add origin {link to GitHub repo}`, and finally `git push -u origin master`.  

### Cloning a repo
If a repo exists on GitHub, you can clone it to your device using `git clone`. This will create a new directory, whose title is the same as the title of the repo you cloned.  
Once a repo has been cloned, you can use `git status` to check your status, and you should always `git pull` to make sure any changes in the remote repo are reflected on your machine.

### Uploading commits
To upload any local changes to GitHub, first commit, then `git push`.

### Creating a pull request (PR)
A pull request is a request to merge changes you made to a different branch or repo. Put more simply, it is a request to push changes you made locally to the "main" branch.  
In order to create a pull request on GitHub, follow these steps:
1. Fork the repository you wish to make changes to. This will create a "copy" (fork) of that repository, owned by you.
2. Clone the fork you just created, using `git clone {your_forked_repo_url}`.
3. Set up a remote upstream. This will allow you to sync changes from the original repository. In the directory of the forked repo, run `git remote add upstream {original_repo_url}`.
4. Update your local repository.
```  
    git fetch upstream
    git merge upstream/main
```
5. Create and switch to a new branch, using `git checkout -b {new_branch_name}`.
6. Make and commit your changes.
7. Push these changes to your forked repository, using `git push origin {new-branch-name}`.
8. Go to your forked repository on GitHub, where you will see a prompt to create a pull request. Fill in the necessary details, and create the PR.  

### GitHub credential management
To clone / make changes to private GitHub repositories, you must be signed in. GitHub no longer supports password-based authentication, so you must use a personal access token, or PAT.  
In order to create a PAT, go to the [GitHub tokens page](https://github.com/settings/tokens). Here, you can view any tokens already active for your account, or create new ones.  
Once you have a PAT, when prompted to sign in, enter your username as your username, and the PAT as your password.  
In order to avoid entering your PAT on every login prompt, use `git config --global credential.helper store`. After your first successful login, this will store your login credentials.

 



## gitignore
We don't always want to upload everything to GitHub, whether that's because we have some sensitive files (API keys for instance), or because we have a bunch of .exe or .vscode files.  
We can specify which particular files, or which types of files do not get managed by git in the .gitignore file.  
Here is an example .gitignore file:
``` 
    .exe
    .vscode
    testing/
    someAPIkey.txt
```

## git config
Every commit has a name and email attached.  
- to view user name: `git config --global user.name`
- to set / change user name: `git config --global user.name "{yourName}"`
- to view user email: `git config --global user.email`
- to set / change user email: `git config --global user.email "{yourEmail}"`



