# numerical_distributions package

A python package having classes for Gaussian and Binomial distributions. This is my first package to learn how to make packages and upload them to PyPi.

# Files

Generaldistribution.py- A parent class for different types of distributions to inherit
Gaussiandistribution.py- A class for Gaussian distribution which inherits Generaldistribution class
Binomialdistribution.py- A class for Binomial distribution which inherits Generaldistribution class

# Installation
```
pip install numerical_distributions
```

# Tests

When you're ready to test out your code, you'll want to pip install your numerical_distributions package and then run the unit tests. In the terminal, type `pip install .` into the command line. Then run the unit tests by typing `python -m unittest test`. 

Note that if you change the code in the numerical_distributions folder after pip installing the package, Python will not know about the changes. You'll need to run `pip install --upgrade .` when you make changes to the package files.