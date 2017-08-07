---
layout: post
title: "A surprising result on the power of the t-test"
description: ""
category: 
tags:  [statistics]
---

In our recent contribution [1], just published in [The American Statistician](http://amstat.tandfonline.com/doi/full/10.1080/00031305.2017.1360795) we revisit the power analysis of the t-test. 

The fundamental observation is that the t-test has been proposed, and studied, as a detector of _shift alternatives_. 
By shift alternatives, a statistician means that if two populations differ, then they differ by their mean. 
Put differently, it is assumed the factor of interest has the effect of _shifting_ a distribution.
For many phenomena, however, we would not expect an effect of shift-type.
Consider a clinical trial: if we expect a drug to affect only part of the population, we are no longer looking for a shift alternative, but rather, a _mixture alternative_. 

We show, that for mixture alternative, much of the folklore on the t-test no longer holds (nor should it). 
We show that Wilcoxon's signed-rank test may be more powerful than a t-test under a Gaussian null. 
This is bacause Wilcoxon's signed-rank test may capture the assymetry in the mixture, before the t-test captures the changed mean.

This has interesting implications.
A practitioner may be willing to pay with some power, and opt for Wilcoxon's test because they will not assume Gaussianity.
Our results show that it is possible that this practitioner did not lose any power, but in fact, has gained some. 
Not because the null is non-Gaussian, but rather, because the alternative is of mixture-type. 

After so much as been said on the t-test, I am rather proud that we can still inovate on the matter.


[1] Rosenblatt, Jonathan D., and Yoav Benjamini. "On Mixture Alternatives and Wilcoxon’s Signed-Rank Test." The American Statistician, August 1, 2017. doi:10.1080/00031305.2017.1360795.
