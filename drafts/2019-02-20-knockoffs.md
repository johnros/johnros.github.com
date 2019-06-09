---
layout: post
title: "Knockoffs- A comment on Sesia et al. (2019)"
description: "Our comment on the Knockoff framework"
category: 
tags:  [statistics, machine-learning]
---

It was a great honor when [Biometrika](https://academic.oup.com/biomet) decide to inaugurate an invited-comments section, and asked us to comment on the Knockoff variable selection framework of Sesia, Sabatti, and Candes [1].

The Knockoff framework is an innovative framework for variable selection by testing the __conditional__ independence of each variable ($x_j$) to the outcome ($y$). 
I relies on generating new variables ($\tilde x_j$), Knockoffs, which have the same dependence to other predictors as the original $x_j$, only that the knockoff is conditionally independent of the outcome. 
With Knockoffs at hand, one has an idea of the null distribution of any test statistic, and may thus compare the observable statistic, to a value from its null. 
This stage is termed in [2] a _Knockoff Filter_.

Some important features of this framework is that:

- Nothing is assumed on the relation $y|x$. 
- It may apply to many test statistics. 
- It provides FDR control on the selected variable w.r.t. conditional nulls, and random-design.
- It assumes knowledge of the joint distribution of predictors ($F_x$). 

Here is high-level summary of our view, detailed in [3], and re-discussed in a rejoinder [4].

1.  The setup is very-useful for variable screening in genetics: it provides random design guarantees, without parametric assumptions on $y|x$. 
While clearly a minority in the statistical genetics literature, we have difficulty with the conditional null hypothesis. For instance: if two SNPs are co-linear, and both correlated with the phenotype, do we want to pass them for a followup knockout study? If yes, as we believe, then a marginal null is more appropriate than a conditional null.

1. While quite unorthodox, we are comfortable with the assumption of knowledge of $F_x$. International consortium provide a lot of unlabeled genetic information to estimate $F_x$, which is also the case in many semi-supervised learning problems. Preliminary results also show that the knockoff framework is quite robust to errors in $F_x$.

1. The knockoff framework seems similar to the _Pseudovariables_ of Wu, Dennis Boos and Stefanski [5]. In their rejoinder, Sesia et al. clarify that while the idea may read similar, it is quite different operationally. 

1. We find that the knockoff re sampling may be seen as an instance of Goeman and Solari's _null-invariant transformations_ [6] in the augmented space of variables and knockoffs. This view may suggest future ways of resampling knockoffs. 

1. When $F_x$ satisfies the Hidden Markov assumption, Sesia et al. [1] propose a knockoff resampling algorithm. We wondered if this algorithm may be simplified, but according to the authors, our simplification will take a toll on power [4]. 

1. We proposed an adversarial example where due to strong correlations in $F_x$, the knockoff framework is expected to have less power than a simple lasso variable selection. In their rejoinder, Sesia et al. demonstrate via simulation that this is not the case [4].
We admit we are puzzled by this result, and will probably revisit this in the future. 

All and all, the knockoff framework is a fresh view of the variable selection problem.
It has great potential, and importantly for us statisticians, generates many questions for future research.


----

[1] Sesia, M., C. Sabatti, and E. J. Candes. "Gene Hunting with Hidden Markov Model Knockoffs." Biometrika 106, no. 1 (March 1, 2019): 1–18. 

[2] Barber, Rina Foygel, and Emmanuel J. Candes. "Controlling the False Discovery Rate via Knockoffs." The Annals of Statistics 43, no. 5 (October 2015): 2055–85.

[3] Rosenblatt, Jonathan D., Ya’acov Ritov, and Jelle J. Goeman. "Discussion of ‘Gene Hunting with Hidden Markov Model Knockoffs.’" Biometrika 106, no. 1 (March 1, 2019): 29–33.

[4] Sesia, M., C. Sabatti, and E. J. Candes. "Rejoinder: ‘Gene Hunting with Hidden Markov Model Knockoffs.’" Biometrika 106, no. 1 (March 1, 2019): 35–45.

[5] Wu, Yujun, Dennis D Boos, and Leonard A Stefanski. "Controlling Variable Selection by the Addition of Pseudovariables." Journal of the American Statistical Association 102, no. 477 (March 1, 2007): 235–43. 

[6] Goeman, Jelle J., and Aldo Solari. "The Sequential Rejection Principle of Familywise Error Control." The Annals of Statistics 38, no. 6 (December 2010): 3782–3810.
