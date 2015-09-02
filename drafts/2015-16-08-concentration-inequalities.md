---
layout: post
title: "Concentration Inequalities and Expected Suprema"
description: ""
category: 
tags:  [statistics; machine-learning]
output:
  html_document:
    toc: true 
---

A cheatsheet of some measure concentration results. Taken from:

- [Philippe Rigollet's](http://www-math.mit.edu/~rigollet/) High-Dimensional Statistics class notes.
- [Gabor Lugosi's](http://www.econ.upf.edu/~bozovic) Concentration of Measure Inequalities class notes.
- [Vladimir Koltchinskii](http://www.stat.washington.edu/jaw/COURSES/EPWG/PAPERS-11/sflour_book.pdf) Oracle Inequalities in Empirical Risk Minimization and Sparse Recovery Problems, letcture notes. 
- [Larry Wasserman's](http://www.stat.cmu.edu/~larry/=sml/Concentration-of-Measure.pdf) Concentration of Measure class notes. 
- Shalev-Shwartz, Shai, and Shai Ben-David. Understanding Machine Learning: From Theory to Algorithms. New York, NY: Cambridge University Press, 2014.


# Preliminaries

## Classes of Distributions
SubGaussian
SubExponential


## Complexity Measures in Function Spaces

### Linear Dimension

### VC dimension

### Uniform Covering Numbers

### Random Covering Numbers

### Shattering Numbers

### Bracketing Numbers 

### Bracketing Entropy

### Generic Chaining Complexities




# Conecntration Inequalities

## Of a Single Random Variable

## Of Sums of Random Variables

## Of Suprema of Stochastic Processes



### Markov's Inequality
Polynomial decay ($t^{-1}$) of tail probability w.r.t. the expectation.

### Chebyshev's inequality
Polynomial decay $t^{-2}$ of tail probability w.r.t. the variance. 

### Generalized Chernoff bound
subExponenitial decay of tail probability of __sums__.

### Sums of subGaussian are subGaussian

### Gaussian Tail Inequality
Bounds the tail of a Gaussian w.r.t. its density (thus, a subGaussian inequality).

### Square of subGaussian
The __square__ of a subGaussian (e.g. Chisq) is subExponential with related scale parameter.

### Hoffeding
subGaussian decay of tail probability of sums of __bounded support__ random variables (garanteeing subGaussian tails).

### McDiarmid's Inequality
A __bounded difference__ function is subGaussian concentrated.

### Shawe-Taylor and Cristianini
Bound on the __sum of a bounded function__ of some random variables.

### Bennet's Inequality
Tighter than subGaussian decay of tails of sums.

### Sum of subExp is subExp

### Bernstein's Inequality
subExp or subGausian tails for __sums__ of subExponenital variables. 

### Talagrand's Inequality
A uniform version of Bernstein's Inequality.

### Gine and Guillou Inequality



### Efron-Stein Inqeuality
A.k.a. _Influence Inequality_, _MG Bound on Variance_
Bound on the __variance__ of an arbitrary function of random variables, w.r.t. the sum of the coordinate independent contributions.
Very powerful when compounding with Che

### Slud's Inequality
A subGaussian __deconcentration__ inequality for the Binomial distribution. 
Put differently, the Binomial converges to a Gaussian, but has __heavier tails__ all along the way.

### Maximal Inequality
- Over finite set
- Over convex polytope
- Over l_2 ball.



# Moment Bounds
The following bound the expectation, and not the tail probabilities.

## Non Negative subGaussian
The expectation of a non-negative subGaussian decays like $n^{-1/2}$.

## Expected Maximum over a Finite Set
The expectation of the max of subGaussians decays like $\sqrt{\log n}$.

## Expected Maximum with Covering Number
The expectation of the max of subGaussians decays like the integrated log of the covering number.




