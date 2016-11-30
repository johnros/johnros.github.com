---
layout: post
title: "What is a pattern? MVPA cast as a hypothesis test"
category: 
tags:  [statistics, machine-learning, brain]
---


In our recent contribution [1], just published in [Neuroimage](http://www.sciencedirect.com/science/article/pii/S1053811916306401) we cast the popular Multi-Voxel Pattern Analysis framework (MVPA) in terms of hypothesis testing. 
We do so because MVPA is typically used for signal localization, i.e., the detection of "information encoding" regions. 

Our major conclusion is that __group MVPA tests a qualitatively different hypothesis than that tested in univariate analysis__. 
We show that in regions detected with MVPA subjects may have actually responded very differently.  
In particular, an "information encoding" region may be one where some subjects show an __increase__ in blood oxygenation (BOLD), while other a __decrease__. 

This is a surprising result since it means that the shift from the analysis of one voxel at-a-time to several-voxels at a time, also entailed a re-definition of "what is an activation?".
In particular, the MVPA definition of activation is such that it is much harder to interpret biologically. 

Clearly, the choice of the null and alternative, i.e., the definition of signal, is case dependent, and should be left to the neuroscientist's best judgement. 
It is our hope, that our observation will facilitate such an informed choice. 

En passant, we observe that recurring patterns between subjects imply that activation patterns are __asymmetrically distributed__ about the null. 
Following this observation, we call upon the statistical literature to offer several measures of multivariate symmetry.
These allow the researcher to quantify the degree of multivariate "agreement" between subjects, instead of committing a-priori to a particular notion of "agreement" to be tested. 




[1] Gilron, Roee, Jonathan Rosenblatt, Oluwasanmi Koyejo, Russell A. Poldrack, and Roy Mukamel. "What’s in a Pattern? Examining the Type of Signal Multivariate Analysis Uncovers at the Group Level." NeuroImage 146 (February 1, 2017): 113–20.
