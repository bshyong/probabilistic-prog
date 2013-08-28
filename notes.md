For multivariable problems, rather than creating a Python array of stochastic variables, addressing the size keyword in the call to a Stochastic variable creates multivariate array of (independent) stochastic variables. The array behaves like a Numpy array when used like one, and references to its value attribute return Numpy arrays.
The size argument also solves the annoying case where you may have many variables βi,i=1,...,N you wish to model. Instead of creating arbitrary names and variables for each one, like:
'''
beta_1 = mc.Uniform("beta_1", 0, 1)
beta_2 = mc.Uniform("beta_2", 0, 1)
...
```
we can instead wrap them into a single variable:
    betas = mc.Uniform("betas", 0, 1, size=N)


