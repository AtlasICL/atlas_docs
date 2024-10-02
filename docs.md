# Atlas docs

## Table of contents

- [Using git](#using-git)
    - [Installing git](#installing-git)
    - [Updating git](#updating-git)
    - [Creating a repo](#updating-git)
    - [Making changes](#making-changes)
    - [Syncing with GitHub](#syncing-with-github)
    - [gitignore](#gitignore)
    - [git config]()

- [Python](#python)
    - [Installing python](#installing-python)
    - [Updating python](#updating-python)
    - [Using pip](#using-pip)
    - [Virtual environments venv](#virtual-environments-venv)


## Using git

### Installing git
Download and install git from the [official website](https://git-scm.com/downloads/win).

### Updating git
Check your current version by running `git --version`.
If not up to date, download the latest version from the [official website](https://git-scm.com/downloads/win).
After installing, check you are up to date, by again running `git --version`.

### Creating a repo
To create a repo, go to the directory you wish to make a git repo. In the terminal, run `git init`. This will initialise a git repo.  
A .git folder will be created, which Windows does not show you by default. I recommend checking the setting "show hidden files / folders" in the Windows file explorer to be able to see .git folders. This makes it easier, when using the file explorer GUI, to tell which directories are git repos, and which are not.  
You can check whether your git repo was correctly initialised by running `git status`.

### Making changes
In order to save changes, you must first choose which files withing the git repo you want to save. You can select all by using `git add .`, or choose specific files with `git add {filename}`.  
Once files have been "added", they are staged. Staged files can be committed by using `git commit -m "{commit message}"`. Alternatively, this can be done through the GUI on the VS Code git extension, but I prefer using the terminal.  
If after staging certain files, you decide you do not want to commit them, you can remove all staged files with `git reset`, or remove a specific file using `git reset <{filename}>`.

### Syncing with GitHub
We can sync our git repos with external services such as GitHub.
- if a repo exists on GitHub, you can clone it to your device using `git clone`. This will create a new directory, whose title is the same as the title of the repo you cloned.
- once a repo has been cloned, you can use `git status` to check your status, and you should always `git pull` to make sure any changes in the remote repo are reflected on your machine.
- if you want to create a repo on GitHub, I usually create it on the GitHub website. Then, the directory which I want to upload, I use 

### gitignore


## Python

### Installing python

### Updating python

### Using pip

### Virtual environments venv

## C++

## Markdown

## LaTeX

