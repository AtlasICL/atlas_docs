# git

# Table of contents

- [git](#git)
    - [Installing git](#installing-git)
    - [Updating git](#updating-git)
    - [Creating a repo](#creating-a-repo)
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
Check your current version by running
```
git --version
```  
If not up to date, download the latest version from the [official website](https://git-scm.com/downloads/win). This will automatically remove the previous version of git before installing the new one.  
After installing, check you are up to date, by running `git --version` again.

---

## Creating a repo
To create a repo, go to the directory you wish to make a git repo. In the terminal, run 
```
git init
```
This will initialise a git repo in that directory.  
You can see a `.git` folder in directories managed with git.  
A .git folder will be created, which Windows does not show you by default. I recommend checking the setting "show hidden files / folders" in the Windows file explorer to be able to see .git folders. This makes it easier, when using the file explorer GUI, to tell which directories are git repos, and which are not.  
In Linux, you can view it using `ls -a`.  
You can check whether your git repo was correctly initialised by running 
```
git status
```  
If you wish to change a local directory to _not_ be a managed by git, simply delete the .git folder for that directory.

---

## Making changes
In order to save changes, you must first choose which files withing the git repo you want to save. You can select all by using 
```
git add .
```
or choose specific files to stage with
```
git add filename
```  
Once files have been "added", they are **staged**.  
Staged files can be committed by using 
```
git commit -m "commit message"
``` 
If, after staging certain files, you decide you do *not* want to commit them, you can unstage them with
```
git reset
``` 
to unstage all staged files, or 
```
git reset filename
```
to unstage specific files.  

You can commit without making any changes (to mark a specific version / milestone) if you wish, using 
```
git commit --allow-empty -m "commit message"
```
---

## Syncing with GitHub
It is useful to sync our git repos with external services such as GitHub. This is mainly for collaboration (but you can use it like I sometimes do, to 'sync' between different devices without using a cloud service).  

### Creating a GitHub repo
If you want to create a repo on GitHub, I usually create it on the GitHub website. Then, in the directory which I want to upload, I run `git init` (if not already initialised), and commit any changes if applicable. Then, 
```
git remote add origin {link to GitHub repo}
```
and finally 
```
git push -u origin master
```  
You can always view your remote origins using 
```
git remote -v
```
Remove a remote origin using
```
git remote remove origin
```

### Cloning a repo
If a repo exists on GitHub, you can clone it to your device using 
```
git clone https://github.com/username/repo_name
``` 
**Note**: if you are using ssh for authentication, the format is:
```
git clone git@github.com:username/repo_name
```
You can also clone a remote repo into a pre-existing local folder using 
```
git clone git@github.com:username/repo_name my_local_folder
```


### Uploading commits
To upload any local changes to GitHub, first commit, then 
```
git push
```

### Creating a pull request (PR)
A pull request is a request to merge changes you made to a different branch or repo. Put more simply, it is a request to push changes you made on one branch to another branch. The changes will be reviewed, and may (or may not) be merged.    
In order to create a pull request on GitHub, follow these steps:
1. Fork the repository you wish to make changes to. This will create a "copy" (fork) of that repository, owned by you.
2. Clone the fork you just created, using `git clone your_forked_repo_url`.
3. Set up a remote upstream. This will allow you to sync changes from the original repository. In the directory of the forked repo, run `git remote add upstream original_repo_url`.
4. Update your local repository.
```  
git fetch upstream
git merge upstream/main
```
5. Create and switch to a new branch, using `git checkout -b new_branch_name`.
6. Make and commit your changes.
7. Push these changes to your forked repository, using `git push origin new-branch-name`.
8. Go to your forked repository on GitHub, where you will see a prompt to create a pull request. Fill in the necessary details, and create the PR.  

### GitHub credential management
To clone / make changes to private GitHub repositories, you must be signed in. GitHub no longer supports password-based authentication, so you can use *either* a personal access token (PAT) *or* authenticate using SSH (which I recommend).  
- **PAT:** In order to create a PAT, go to the [GitHub tokens page](https://github.com/settings/tokens). Here, you can view any tokens already active for your account, or create new ones.  
Once you have a PAT, when prompted to sign in, enter your username as your username, and the PAT as your password.    
In order to avoid entering your PAT on every login prompt, use `git config --global credential.helper store`. After your first successful login, this will store your login credentials.  

- **SSH:** If you want to use SSH instead, the first step is to create an SSH key [see this section](ssh.md#generating-ssh-keys).  
Once you have an SSH key pair, go to your GitHub settings, and navigate to your SSH keys section (https://github.com/settings/keys). In this section, you can add your SSH key with the option "New SSH key". Simply add your public key, and you're good to go.  
  
Important note: when authenticating using SSH, instead of using links of the form 
```
https://github.com/username/repo
```
you should instead use
```
git@github.com:username/repo
```
This applies for git clone {url}, and anywhere else you would normally input the repo url.


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
Alternatively, you can choose to ignore everything by default, and selectively add files to track using a `!` prefix:
```
*
!main.py
!images/
!README.md
!.gitignore
```

## git config
Every commit has a name and email attached.  
- to view user name: `git config --global user.name`
- to set / change user name: `git config --global user.name "{yourName}"`
- to view user email: `git config --global user.email`
- to set / change user email: `git config --global user.email "{yourEmail}"`




