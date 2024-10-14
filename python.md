# Python

# Table of contents

- [Python](#python)
    - [Installing python](#installing-python)  
    - [Using pip](#using-pip)
        - [Libraries I use](#libraries-i-use)
        - [Updating pip packages](#updating-pip-packages)
        - [Check installed packages and versions](#check-installed-packages-and-versions)
    - [Virtual environments](#virtual-environments-venv)
        - [Creating a venv](#creating-a-venv)
        - [Activating a venv](#activating-a-venv)
        - [Deactivating a venv](#deactivating-a-venv)
    - [Updating python](#updating-python)


## Installing python
TODO: write section

## Using pip
pip is a package manager for python. We can use it to install packages we need to use. It is a good idea to read [the section on virtual environments](#virtual-environments-venv) before installing packages using pip.

### Libraries I use
Note: you should probably not be installing these globally, but using a virtual environment. (see previous note)
- numpy
    - install: `python -m pip install numpy`.
- pandas
    - install: `python -m pip install pandas`.
- sklearn
    - install: `python -m pip install scikit-learn`.
- matplotlib
    - install: `python -m pip install matplotlib`.


### Updating pip packages

To update libraries installed using pip, use: `pip install --upgrade {package_name}`.

### Check installed packages and versions

To check the installed packages in your current environment, as well as their versions, use `python -m pip freeze`.

### Check a specific package
To check whether a specific package is installed (and its version), use `pip show {package_name}`.

## Virtual environments (venv)
Virtual environments, typically shortened to venvs, are an extremely useful tool in python. They allow you to install packages for one specific project without having them installed globally. They also create a recreatable and shareable environment for running your code.

### Creating a venv
In order to create a virtual environment, navigate to the directory in which you would like to have the venv, then run `python -m venv venv`. **Note:** once a venv has been created, it must be activated.

### Activating a venv
In order to activate a venv, we must run the activate script, located in the Scripts folder.  
Since I use PowerShell on Windows, I run the Activate.ps1 script with `./venv/Scripts/Activate.ps1`.  
On PowerShell, it is common to run into the error "... execution policy". In that instance, simply run `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`.

### Deactivating a venv
You can deactivate a venv with `deactivate`.

## Updating python
TODO: write section
