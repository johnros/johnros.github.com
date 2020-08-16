---
layout: post
title: "Domain Adaptation for Environmental Monitoring"
description: ""
category: 
tags:  [statistics, machine-learning]
---

Environmental monitoring from satellite imagery essentially means that instead of directly measuring pollution (for instance), you predict it from satellite imagery.
When an epidemiologist controls for ambient temperature, you can be pretty sure that such an indirect measurement of pollution is involved. 

Predicting pollution is typically addressed as a supervised learning problem: use the pollution measured in ground stations as labels, and predict it wherever ground stations are not available. 
But what if some pollution monitoring stations are far away from the residences of the subjects involved in the epidemiological study? Would we not want to down-weight those stations in the learning?

The idea of weighted learning is not a new one. 
In the Machine Learning literature, it has been recently popularized in the context of "Domain Adaptation", and in particular "Covariate Shift": where the distributions of the covariates in the train set differ from those of the test set. 
This is exactly the case in environmental monitoring. 

In our latest contribution [1], we call upon recent idea from the domain adaptation literature to estimate the quality of predicted temperatures in France. 
We show that naive performance estimates are biased, even if cross-validated. 
We then plug our performance estimators in the Empirical Risk Minimization framework, in order to learn better predictors. 
En passant- we discuss the matter of h-blocking, and other data splitting schemes designed for unbiased performance estimation (briefly: don't).




[1] R. Sarafian, I. Kloog, E. Sarafian, I. Hough and J. D. Rosenblatt, "A Domain Adaptation Approach for Performance Estimation of Spatial Predictions," in IEEE Transactions on Geoscience and Remote Sensing, doi: 10.1109/TGRS.2020.3012575.
