## How to put code on PyPi

# Setting up and installing the requirements
```
python3 setup.py sdist bdist_wheel
pip install twine
```
The first command will output a folder called dist having a .tar.gz file and a .whl file. The .tar.gz file is called a *source archive* whereas the .whl file is a *built distribution*.
If you use `python setup.py sdist`, you will get only .tar.gz file in dist folder.
The .whl file is a newer type of installation file for Python packages. When you pip install a package, pip will first look for a whl file (wheel file) and if there isn't one, will then look for the tar.gz file.

A tar.gz file, ie an sdist, contains the files needed to compile and install a Python package. A whl file, ie. a *built distribution*, only needs to be copied to the proper place for installation. Behind the scenes, pip installing a whl file has fewer steps than a tar.gz file.

# commands to upload to the pypi test repository
```
twine upload --repository-url https://test.pypi.org/legacy/ dist/*
pip install --index-url https://test.pypi.org/simple/ numerical_distributions
```

# command to upload to the pypi repository
```
twine upload dist/*
pip install numerical_distributions
```