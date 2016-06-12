---
layout: post
title: "Almost-embarrassingly-parallel algorithms for machine learning"
description: "Some recent results on distributed machine learning" 
category: 
tags:  [statistics, machine-learning]
---

Most machine learning algorithms are optimization problems. 
If they are not, they can often be cast as such.
Optimization problems are notoriously hard to distribute. 
That is why machine learning from distributed BigData databases is so challenging.

If data is distributed along observations (and not variables), one simple algorithm is to learn your favorite model using the data on each machine, and then aggregate over machines.
If your favorite model is in a finite-dimensional parametric class, you can even aggregate by simple averaging over machines.

This averaging approach is known as _command and conquer_, _one-shot averaging_, and _embarasingly parallel learning_, among others.
It is attractive because of its low communication requirements and simplicity to implement.
Indeed, it can be implemented over any distributed abstraction layer such as Spark, Hadoop, Condor, SGE, and more. 
It can also be implemented on top of most popular distributed databases such as Amazon-Redshift and HP-Vertica. 
It also covers a wide range of learning algorithms such Ordinary Least Squares, Generalized Linear Models, and Linear SVM.

In our latest contribution, just [published in Information and Inference, a Journal of the IMA](http://imaiai.oxfordjournals.org/content/early/2016/06/09/imaiai.iaw013.abstract?keytype=ref&ijkey=TbndI5rIDAxDEzz), we perform a statistical analysis of the error of such an algorithm and compare it with a non-distributed (centralized) solution. 

Our findings can be summarized as follows:
When there are many more observations, per machine, than parameters to estimate, there is no (first order) accuracy loss in distributing the data. 
When the number of observations is not much greater than the number of parameters, then there is indeed an accuracy loss. This loss is greater for non-linear models, than linear. 

If it unclear why accuracy is lost when averaging, think of linear regression.
The (squared) risk minimizer is $$\beta^*=\Sigma^{-1} \alpha$$, where $$\Sigma= E[x x']$$ and $$\alpha=E[x y]$$.
The empirical risk minimizer, $$\hat{\beta}=(X'X)^{-1} X'y$$, is merely its empirical equivalent. 
If rows of the $$X$$ matrix are distributed over machines, which do not communicate, then instead of the full $$(X'X)^{-1}$$ we can only compute machine-wise estimates. 
It turns out, that even in this simple linear regression problem, aggregating the various machine wise $$\hat{\beta}$$, e.g., by averaging, is less accurate than computing $$\hat{\beta}$$ with the whole data. 

The statistical analysis of the split-and-average algorithm has several implications:
It informs the practitioner which algorithms can be safely computed in parallel, and which need more attention. 
Put differently- no learning algorithm is truely **embarassignly-parallel**, but some are **almost-embarasingly-parallel**. 

Equipped with guarantees on the learning error, one can apply our results to compute the required number of machines that achieves a given error. 
Since increasing the number of machine increases the error, but decreases the learning speed, our results can also be seen as a **learning accuracy-complexity curve**. 
Finally, the error decomposition for split-and-average algorithms also implies a Gaussian limit. Our results can thus be used also for inference and model selection. 


To prove our results we mostly used [Lucien Le-Cam](https://en.wikipedia.org/wiki/Lucien_Le_Cam), and [Peter Huber's](https://en.wikipedia.org/wiki/Peter_J._Huber) classical asymptotic statistics. 
We take particular pride in the use of classical statistical theory to solve cutting edge learning algorithms for BigData. 

