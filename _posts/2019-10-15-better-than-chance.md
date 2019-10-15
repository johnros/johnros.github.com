---
layout: post
title: "Better-Than-Chance Classification for Signal Detection"
description: "Biostatistics paper"
category: 
tags:  [statistics, machine-learning, brain]
---

In 2012 my friend [Roee Gilron](https://scholar.google.co.il/citations?user=6TFj2D8AAAAJ&hl=en) told me about a popular workflow for detecting activation in the brain: fit a classifier, then use a permutation test to check if its cross-validated accuracy is better than chance level.
"That can't be right" I said. "So much power is left on the table!"
"Can you show it to me?" Roee replied. 
Well, I did. And 7 years later, our results have been published by [Biostatistics](https://academic.oup.com/biostatistics/advance-article/doi/10.1093/biostatistics/kxz035/5587128?searchresult=1). 

Roee's question led to a mass of simulations, which led to new questions, which led to new simulations.
This question also attracted the interest of my other colleagues: [Roy Mukamel](https://en-social-sciences.tau.ac.il/profile/rmukamel), [Jelle Goeman](https://www.universiteitleiden.nl/en/staffmembers/jelle-goeman), and [Yuval Benjamini](https://en.stat.huji.ac.il/people/yuval-binyamini). 

The core of the work is the comparison of power, of two main approaches: 
(1) Detecting signal using a supervised-classifier, as described above. 
(2) Detecting signal using multivariate hypothesis testing, such as Hotelling's $$T^2$$ test. 
We call the former an _accuracy test_, and the latter a _two-group_. 
We studied the _high-dimension-small-sample setup_, where the dimension of each measurement, is comparable to the number of measurements. 
This setup is consistent with applications in brain-imaging and genetics. 

Here is a VERY short summary of our conclusions. 

- Accuracy tests are underpowerd compared to two-group tests. 
- In high-dimension covariance regularization is crucial. The statistical literature has many two-group tests designed for high-dimension.
- The optimal regularization for testing, and for prediction are different. 
- The interplay between the direction of the signal and the principal components of the noise has a considerable effect on power. 
- Two-group tests do not require cross-validation. They are thus considerably faster to compute. 
- If insisting on accuracy-tests instead of two-group tests, then resampling with-replacement has more power than without-replacement.  In particular, the _leave-one-out Bootstrap_ is better than _cross-validation_.

The intuiton for our main findings is the following:

1. Estimating accuracies adds a discretization stage which reduces power and is needless for testing.
1. In in high-dim, there is barely enough data to estimate the covariances in the original space, let alone in augmented feature spaces. Kernel tricks, and deep-nets may work fine in low-dim, but are hopeless in high-dim. 

Given these findings, the tremendous popularity of accuracy tests is quite puzzling. 
We dare conjecture that it is partially due to the growing popularity of machine-learning, and the reversal of the inference cascade:
Researchers fit a classifier, and then check if there is any difference between populations?
Were researchers to start by testing for any difference between populations, and  only then fit a classifier, then a two-group test would be natural starting point. 

The full details can be found in [1].


[1] Jonathan D Rosenblatt, Yuval Benjamini, Roee Gilron, Roy Mukamel, Jelle J Goeman, Better-than-chance classification for signal detection, Biostatistics, 
https://doi.org/10.1093/biostatistics/kxz035

