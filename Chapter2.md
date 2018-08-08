Chapter 2 Overview of Supervised Learning
================

### 2.1 Introduction

1.  Termonologies for X and Y:

    -   X: inputs, predictors, independent variables, features;
    -   Y: outputs, reponses, dependent variables.

### 2.2 Variable Types and Terminology

1.  The distinction in output type has led to a naming convention for the prediction tasks:

    -   regression: when we predict quantitative outputs;
    -   classification: when we predict qualitative outputs.

2.  Variable types include: quantitative, qualitative and ordered categorical.

3.  The most useful and commonly used coding for *qualitative* variables are **dummy variables**. K-level qualitative variable is represented by a vector of K binary variables or bits, only one of which is “on” at a time.

4.  Naming Convention:

-   Inputs: X;
-   Quantitative ouputs: Y;
-   Qualitative outputs: G
-   Use uppercase letters such as X, Y or G when referring to the generic aspects of a variable. Observed values are written in lowercase; hence the *i*th observed value of X is written as *x*<sub>*i*</sub> (where *x*<sub>*i*</sub> is again a scalar or vector).
-   Matrices are represented by bold uppercase letters; for example, a set of N input p-vectors *x*<sub>*i*</sub>, *i* = 1, ..., *N* would be represented by the *N* × *p* matrix X.
-   The *i*th row of **X** is *x*<sub>*i*</sub><sup>*T*</sup>, the vector transpose of *x*<sub>*i*</sub>, because we assume all vectors are column vectors.

### 2.3 Two Simple Approaches to Prediction: Least Squares and Nearest Neighbors

#### 2.3.1 Linear Models and Least Square

1.  The linear model is:

where *X*<sup>*T*</sup> = (1, *X*<sub>1</sub>, *X*<sub>2</sub>, ..., *X*<sub>*p*</sub>), *X* is a *N* × *p* matrix.

1.  Using Least Squares for finding unknown coefficients and the goal is to minimize the residual sum of squares:

where *X* is an *N* × *p* matrix with each row an input vector, and **y** is an *N*-vector of the ouputs in the training set.

*R**S**S*(*β*) is a quadratic function of the parameters, and hence its minimum always exists, but may not be unique.

Differentiating w.r.t. *β* we get the normal equations:
If *X*<sup>*T*</sup>*X* is nonsingular, then the unique solution is given by
1.  Using linear model for classification:

    First code all classes as a binary variable, and then fit by linear regression. The decision boundary can be $x^T \\hat{\\beta} = 0.5$.

2.  Two possible scenarios regarding to Linear Regression Classification performance:

    <span style="color:blue">Scenario 1:</span> The training data in each class were generated from bivariate Gaussian distributions with uncorrelated components and different means.

    <span style="color:blue">Scenario 2:</span> The training data in each class came from a mixture of 10 low-variance Gaussian distributions, with individual means themselves distributed as Gaussian.
