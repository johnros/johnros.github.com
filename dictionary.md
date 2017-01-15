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



|__Concept__      |__Statistics__     |__Machine Learning__|  
|-----------------|-------------------|-------------------|
|  assumed model  |parameter space    |hypothesis class   |           
|                 |model              |hypothesis         |           
|                 |misspecified model |agnostic learning  |           
|                 |deterministic outcome|realizable learning|         
|                 |sampling distribution|generative model |           
|output range     |--                 |improper learning  |           
|model types      | CART              |decision tree, axis parallel rectangles|
|                 |piecewise constant function|decision list|     
|                 |Bayes net          |directed acyclic graph (of conditional probabilities)|
|                 |latent variable model|model based collaborative filtering|
|                 |beighbourhood methods|memory based collaborative filtering|
|                 |multivariate distribution|graphical model|         
|                 |--                 |Boolean circuit    |           
|                 |--                 |kCNF               |           
|                 |--                 |kDNF               |           
|                 |--                 |k-clause CNF       |           
|                 |--                 |k-term DNF         |           
|                 |--                 |CNF                |           
|                 |--                 |DNF                |           
|                 |--                 |Boolean formula    |           
|                 |--                 |Boolean threshold function|    
|                 |--                 |Boolean circuit    |           
|                 |--                 |threshold circuit  |           
|                 |--                 |acyclic finite automata|       
|tasks / problem setup|estimation     |learning           |           
|                 |classification     |supervised learning|           
|                 |clustering         |unsupervised learning|         
|                 |--         |transductive learning      |             
|                 |frequentist inference  |--             |             
|                 |--                     |semi supervised learning|    
|                 |support estimation     |manifold learning|           
|                 |hypothesis             |--               |           
|                 |fixed design           |conditional model, discriminative model|
|                 |random design          |generative model |           
|                 |adaptive design of experiments|active learning|      
|                 |MANOVA, vector regression|structured learning|       
|                 |basis augmentation     |feature creation|            
|                 |missing data imputation|collaborative filtering|     
|                 |statistical process control|semi supervised novelty detection|
|data             |data, sample, observations|examples, training sample, instances|
|                 |--                     |validation sample|           
|                 |--                     |test sample      |           
|                 |covariates, design, $$X$$-matrix|features, attributes|      
|methods          |M-estimation             |empirical risk minimization|           
|                 |R-estimation             |--                         |           
|                 |L-Estimation             |--                         |           
|                 |moment matching          |--                         |           
|                 |quantile matching        |--                         |           
|                 |U-estimation, V-estimation|generative unsupervised RKHS learning|
|                 |K-estimation             |--                         |           
|                 |Fisher's LDA (assuming independence)|Gaussian naive bayes|       
|interval methods |confidence intervals     |PAC learnable              |           
|                 |credible interval        |PAC Bayes learnable        |           
|                 |fiducial interval        |--                         |           
|                 |prediction interval      |--                         |           
|error decomposition|misspecification error|approximation error         |           
|                 |risk                     |estimation error, expected prediction error, test Error|
|                 |--                       |optimization Error         |           
|                 |optimism                 |test error-training Error  |           
|                 |RSS                      |empirical risk, training error|        
|                 |Jackknife                |hypothesis stability       |           
|                 |model selection          |structural learning        |          
|problem complexity measures|generalized degrees of freedom|Rademacher complexity|  
|                 |sample size              |sample complexity          |           



