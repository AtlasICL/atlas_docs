# Python

# Table of contents

- [Python](#python)
    - [Installing python](#installing-python)
    - [Updating python](#updating-python)
    - [Using pip](#using-pip)
        - [Libraries I use](#libraries-i-use)
        - [Updating pip packages](#updating-pip-packages)
        - [Check installed packages and versions](#check-installed-packages-and-versions)
    - [Virtual environments venv](#virtual-environments-venv)


## Installing python

## Virtual environments (venv)

## Updating python

## Using pip

pip is a package manager for python (hello c++). We can use it to install packages we need to use. It is a good idea to read [the section on virtual environments](#virtual-environments-venv) before installing packages using pip.

### Libraries I use
Note: you should probably not be installing these globally, but using a virtual environment.
- numpy
    - install: `pip install numpy`.
- pandas
    - install: `pip install pandas`.
- sklearn
    - install: `pip install -U scikit-learn`

### Updating pip packages

To update libraries installed using pip, use: `pip install --upgrade {package_name}`.

### Check installed packages and versions

To check the installed packages in your current environment, as well as their versions, use `python -m pip freeze`.
