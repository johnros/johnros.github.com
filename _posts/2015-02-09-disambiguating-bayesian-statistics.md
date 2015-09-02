---
layout: post
title: "Disambiguating 'Bayesian Statistics'"
description: ""
category: 
tags:  [statistics; machine-learning]
output:
  html_document
---


The term "Bayesian Statistics" is mentioned in any introductory course to statistics and appears in countless papers and in books, in many contexts and with many meanings.
Since it carries different meaning to different authors, I will try to suggest several different interpretations I have encountered.

First, I will classify several possible generative models according to the $4$ following qualities:

1. Is there a probability on the parameter space (a "prior")?
1. Is the prior subjective or objective?
1. Is the prior parametric or non-parametric?
1. Is the prior simple or composite?

We consider these qualities on the most common modelling approaches:

- Neymann-Pearson frequentist inference has no prior on the parameter space.
Example: MLE for the mean of a normal population.
- A pure/subjective/DeFinetti Bayesian has a simple, subjective prior. It may be parametric or not. 
__Example__: [MAP](https://en.wikipedia.org/wiki/Maximum_a_posteriori_estimation) estimate of the mean of a normal population.
- A Semi-Bayesian (a.k.a. pseudo-Bayesian, semi-Empirical-Bayesian) is essentially a frequentist with a composite, parametric, objective prior. 
Sometimes referred to as Empirical-Bayesian [1] albeit not in it's original historical sense [2].
__Example__: Type-II Maximum Likelihood or Restricted-Maximum-Likelihood estimation of the variance components in a mixed effects model.
- Empirical Bayesian in it's original historical sense has an objective, non-parametric prior, specified up to it's two first moments [2]. 
It differs from the (original) Pseudo-Bayesian, in that the prior is non-parametric.
__Example__: Sample coverage estimation- "What is the probability that the next sample will be of an unseen species?" [3].
- A parametric, composite, subjective prior is something interesting. 
It is hard to interpret since it implies that "my beliefs are exact, but I don't know what they are". It is typically encountered as a mathematical regularization device.
__Example__: Ridge regression; the Gaussian prior on the coefficients can hardly be interpreted as a limiting frequency, thus it is subjective. The variance of the prior is unspecified, usually estimated using cross-validation, thus a composite prior.


# Critique

Q: Epistemic probability? Is there really such a thing as epistemic probability? Is it not just the limiting frequency of events in our accumulative experience? 

A: If it were epistemic and universal (objective), then the distinction might be only a matter for philosophers. That fact that it is personal (subjective), is of real practical implications.

***

Q: Objective probabilities?!? Except for non-parametric, I am always assuming the distribution of the population. Isn't this subjective? Am I not subjectively assuming the differentiability of the CDF for density estimation? We are thus, all subjective Bayesians. Yes, even Fisher!

A: I would say one cannot approach data completely assumption free, so saying we are all subjective Bayesians, might be true, but non-informative. I feel different "philosophies", are useful to convey what kind of argument are we making with the data. Namely, the answer to the 4 above questions. Is my answer true, but non informative as well? :-)

***

Q: If we acknowledge that "Empirical Bayes" has caught a new meaning since it's initial introduction, why bother with history? Why not use the composite epistemic meaning only? 

A: Because it seems there no agreed upon "new meaning". Some will use it for composite-epistemic priors, but some will use it for physical ones. The smallest common denominator, is the fact that the prior is composite and not simple (whether it be parametric or not).

# References

[1] E.L. Lehmann and George Casella, Theory of Point Estimation, 2nd ed. (Springer, 1998).  
[2] I. J. Good, "Introduction to Robbins (1955) An empirical Bayes approach to statistics," Breakthroughs in Statistics: Foundations and basic theory (1992): 379.  
[3] Bradley Efron and Ronald Thisted, "Estimating the Number of Unseen Species: How Many Words Did Shakespeare Know?," Biometrika 63, no. 3 (December 1976): 435-447.  
[4] Fienberg, Stephen E. "When Did Bayesian Inference Become 'Bayesian'?" Bayesian Analysis 1, no. 1 (March 2006): 1-40. doi:10.1214/06-BA101.

