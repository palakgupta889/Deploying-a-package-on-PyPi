# How to upload code on PyPi

## Setting up and installing the requirements
```
python3 setup.py sdist bdist_wheel
pip install twine
```
The first command will output a folder called dist having a .tar.gz file and a .whl file. The .tar.gz file is called a *source archive* whereas the .whl file is a *built distribution*.
If you use `python setup.py sdist`, you will get only .tar.gz file in dist folder.
The .whl file is a newer type of installation file for Python packages. When you pip install a package, pip will first look for a whl file (wheel file) and if there isn't one, will then look for the tar.gz file.

A tar.gz file, ie an sdist, contains the files needed to compile and install a Python package. A whl file, ie. a *built distribution*, only needs to be copied to the proper place for installation. Behind the scenes, pip installing a whl file has fewer steps than a tar.gz file.

## Commands to upload to the pypi test repository
```
twine upload --repository-url https://test.pypi.org/legacy/ dist/*
pip install --index-url https://test.pypi.org/simple/ numerical_distributions
```

## Commands to upload to the pypi repository
```
twine upload dist/*
pip install numerical_distributions
```

## PyPi vs. Test PyPi
Note that pypi.org and test.pypi.org are two different websites. You'll need to register separately at each website. If you only register at pypi.org, you will not be able to upload to the test.pypi.org repository.

Also, remember that your package name must be unique. If you use a package name that is already taken, you will get an error when trying to upload the package.

# Tests

When you're ready to test out your code, you'll want to pip install your numerical_distributions package and then run the unit tests. In the terminal, type `pip install .` into the command line. Then run the unit tests by typing `python -m unittest test`. 

Note that if you change the code in the numerical_distributions folder after pip installing the package, Python will not know about the changes. You'll need to run `pip install --upgrade .` when you make changes to the package files.