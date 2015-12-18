---
layout: page
title: Translator
permalink: /translator/
categories: [static_page]
---

Here is a machine learning to statistics translator I try to maintain. 
Most concepts are not really identical, so "translations" should be considered approximate.
Based on the same idea in "_All Of Statistics_" by Larry Wasserman [p.15].
Many thanks to [Ohad Shamir](http://www.wisdom.weizmann.ac.il/~shamiro/), and [Saharon Rosset](http://www.tau.ac.il/~saharon/) for helping populate the table. 
Despite my best efforts, it proably still contains errors. Drop me a note if you find any.



|  __Concept__    |  __Statistics__   |__Machine Learning__|  __Remarks__  |   
|-----------------|-------------------|-------------------|-----------|
|  assumed model  |  parameter space  | hypothesis class  |           |
|                 |             model | hypothesis        |           |
|                 | misspecified model| agnostic learning |           |
|                 |deterministic outcome|realizable learning|         |
|                 |sampling distribution|generative model |           |
|output range     |                   |improper learning  |estimator allowed to be outside the parameter space|
|model types      | CART              |decision tree, axis parallel rectangles||
|                 |piecewise constant function|decision list|     |
|                 |--                 |Boolean circuit    |           |
|                 |--                 |kCNF               |           |
|                 |--                 |kDNF               |           |
|                 |--                 |k-clause CNF       |           |
|                 |--                 |k-term DNF         |           |
|                 |--                 |CNF                |           |
|                 |--                 |DNF                |           |
|                 |--                 |Boolean formula    |           |
|                 |--                 |Boolean threshold function|    |
|                 |--                 |Boolean circuit    |           |
|                 |--                 |threshold circuit  |           |
|                 |--                 |acyclic finite automata|       |
|                 |Bayes net          |directed acyclic graph (of conditional probabilities)||
|                 |latent variable model|model based collaborative filtering||
|                 |beighbourhood methods|memory based collaborative filtering||
|                 |multivariate distribution|graphical model|         |
|tasks / problem setup|estimation     |learning           |           |
|                 |classification     |supervised Learning|I follow Wasserman, but this is a rather controversial interpretation.|
|                 |clustering         |unsupervised learning|I follow Wasserman, but this is a rather controversial interpretation.|
|                 |--         |transductive learning      |active semi supervised learning. User can be queried for labels on select examples.|
|                 |frequentist inference  |--             |             |
|                 |--                     |semi supervised learning||
|                 |support estimation     |manifold learning|           |
|                 |hypothesis             |--               |           |
|                 |fixed design           |conditional model, discriminative model||
|                 |random design          |generative model |           |
|                 |adaptive design of experiments|active learning|      |
|                 |MANOVA, vector Regression|structured Learning|       |
|                 |basis augmentation     |feature creation|            |
|                 |missing data imputation|collaborative filtering|     |
|                 |statistical process control|semi supervised novelty detection||
|data             |data, sample, observations|examples, training sample, instances||
|                 |--                     |validation sample|           |
|                 |--                     |test sample      |           |
|                 |covariates, design, $X$-matrix|features, attributes|      |
|methods          |M-estimation             |empirical risk minimization|           |
|                 |R-estimation             |--                         |           |
|                 |L-Estimation             |--                         |           |
|                 |moment matching          |--                         |           |
|                 |quantile matching        |--                         |           |
|                 |U-estimation, V-estimation|generative unsupervised RKHS learning|estimating by averaging some (kernel) function over all choices of r sets of observations.|
|                 |K-estimation             |--                         |           |
|                 |Fisher's LDA (assuming independence)|Gaussian Naive Bayes|       |
|interval methods |confidence intervals     |PAC learnable              |           |
|                 |credible interval        |PAC Bayes learnable        |           |
|                 |fiducial interval        |--                         |           |
|                 |prediction interval      |--                         |           |
|error decomposition|misspecification error|approximation error         |when the hypothesis does not belong to the assume model space.|
|                 |risk                     |estimation error, expected prediction error, test Error            |           |
|                 |--                       |optimization Error         |           
|                 |optimism                 |test error-training Error  |           |
|                 |RSS                      |empirical risk, training error         |           |
|                 |Jackknife                |hypothesis stability       |change in estimator under removal of an observation|
|                 |model selection          |structural risk minimization|          |
|problem complexity measures|generalized degrees of freedom|Rademacher complexity   |                 |                 |sample size              |sample complexity          |           |



