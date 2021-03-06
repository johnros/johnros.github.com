---
layout: post
title: "Multivariate difference between male and female brain"
description: "In reply to 'Sex Beyond the Genitalia', contradicting the authors' findings." 
category: 
tags:  [statistics, brain]
---

In their recent, high-impact, [PNAS publications](http://www.pnas.org/content/112/50/15468.abstract), a Tel Aviv University research group led by [Prof. Daphna Joel](http://people.socsci.tau.ac.il/mu/daphnajoel/) claims that no difference exists between male and female brain. 
This was a very high profile study as can be seen by the mentions in 
[The New Scientists](https://www.newscientist.com/article/dn28582-scans-prove-theres-no-such-thing-as-a-male-or-female-brain/), 
[TheGuardian](https://www.theguardian.com/science/2015/dec/01/brain-sex-many-ways-to-be-male-and-female),
[MedicalPress](http://medicalxpress.com/news/2015-11-male-female-brain-valid-distinction.html),
[IsraelScienceInfo](http://www.israelscienceinfo.com/en/medecine/femmes-et-sciences-pour-luniversite-de-tel-aviv-les-cerveaux-feminins-et-masculins-sont-un-patchwork-de-caracteristiques/),
[DailyMail](http://www.dailymail.co.uk/sciencetech/article-3340123/Male-vs-female-brain-Not-valid-distinction-study-says.html), 
[TheJerusalemPost](http://www.jpost.com/Business-and-Innovation/Health-and-Science/TAU-neuroscientists-Brains-are-not-gendered-435882), 
[CBCNews](http://www.cbc.ca/news/technology/brain-sex-differences-1.3344954), and many more. 


This publication contradicts much of the corpus of knowledge on brains and gender, and thus took the scientific community by surprise. How can this be?

In short and as put by Carl Sagan: 
"__Absence of evidence is not evidence of absence__". 

Indeed, by performing many univariate analyses, the authors show that males and females do not show any particular pattern in the brains' structure, as least as recorded by MRI scans.
It is, however, quite possible for two multivariate data sets to be nicely separated, but not so in any of the "raw" univariate measurements. 
The following figure is a toy example of a dataset which cannot be separated by any single (raw) variable, but certainly can when considering two variables simultaneously. 

 ![Multivariate seperability](../images/overlap.png) 
 
 I suspect this is what happened in the case of "Sex Beyond the Genitalia". When I [reanalyzed the same data](http://www.pnas.org/content/early/2016/03/15/1523961113.full?sid=71a90a9a-ec35-45a3-a11a-63d0fc116fa9) the __multivariate__ brain structures of males and females was different enough, so that the gender could be inferred from the MRI data alone, with $$~ 80\%$$ accuracy(!). 

It also seems I was not the only one troubled by Joel et al.'s findings. Here is 
[Del Giudice et al.'s](http://www.pnas.org/content/early/2016/03/15/1525534113.full?sid=71a90a9a-ec35-45a3-a11a-63d0fc116fa9) comment, 
[Chekroud et al.'s](http://www.pnas.org/content/early/2016/03/15/1523888113.full),
[Marek Glazerman's](http://www.pnas.org/content/early/2016/03/07/1524418113.extract), 
[David Schmidt's](https://www.psychologytoday.com/blog/sexual-personalities/201512/statistical-abracadabra-making-sex-differences-disappear).

In [Joel's reply to the critics](http://www.pnas.org/content/early/2016/03/15/1600792113.full?sid=71a90a9a-ec35-45a3-a11a-63d0fc116fa9#ref-8) they no longer insist that 
"_human brains do not belong to one of two distinct categories: male brain/female brain_", but rather soften their claims:
"_it is unclear what the biological meaning of the new space is and in what sense brains that seem close in this space are more similar than brains that seem distant_".

I agree. For the purposes of __intepreting__ the dimensions in which male and female differ, some feature selection can be introduced. 
I will leave that for future neuroimaing research. 



__Edit__(19.3.2016):
Here is the code that generated the above figure:

```r
library(mvtnorm)
library(magrittr)
library(MASS)
library(ggplot2)
library(gridExtra)


n <- 1e3
set.seed(999)
X <- rmvnorm(n = n, mean = c(0,0))
beta <- 10*c(1,1)
y <- rbinom(n=n, size = 1, prob=plogis(X %*% beta)) %>% as.factor
xy <- data.frame(x.1=X[,1], x.2=X[,2], y=y)


empty <- ggplot() + geom_point(aes(1, 1), colour = "white") + theme(plot.background = element_blank(), 
    panel.grid.major = element_blank(), panel.grid.minor = element_blank(), 
    panel.border = element_blank(), panel.background = element_blank(), axis.title.x = element_blank(), 
    axis.title.y = element_blank(), axis.text.x = element_blank(), axis.text.y = element_blank(), 
    axis.ticks = element_blank())

# scatterplot of x and y variables
scatter <- ggplot(xy, aes(x.1, x.2)) + geom_point(aes(color = y)) + scale_color_manual(values = c("orange", 
    "purple")) + theme(legend.position = c(1, 1), legend.justification = c(1, 
    1))

# marginal density of x - plot on top
plot_top <- ggplot(xy, aes(x.1, fill = y)) + geom_density(alpha = 0.5) + 
    scale_fill_manual(values = c("orange", "purple")) + theme(legend.position = "none")

# marginal density of y - plot on the right
plot_right <- ggplot(xy, aes(x.2, fill = y)) + geom_density(alpha = 0.5) + 
    coord_flip() + scale_fill_manual(values = c("orange", "purple")) + theme(legend.position = "none")

grid.arrange(plot_top, empty, scatter, plot_right, ncol = 2, nrow = 2, widths = c(4, 
    1), heights = c(1, 4))

```
