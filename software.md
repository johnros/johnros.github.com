---
layout: page
title: Computing
permalink: /software/
categories: [static_page]
---

## Software I wrote

- __RRHO R package__:
Implements the [Rank-Rank Hypergeometric Overlap Test](http://nar.oxfordjournals.org/content/38/17/e169.abstract). 
Download from [Bioconductor](http://www.bioconductor.org/packages/devel/bioc/html/RRHO.html) or [Github](https://github.com/johnros/RRHO). 

- __chords R Package__:
Estimate population size and degree distribution in respondent driven samples, presented in [our paper](http://arxiv.org/abs/1304.3505). [Download](https://CRAN.R-project.org/package=chords) from CRAN

- __SimpleLearner__:
Implements an easy to tune polynomial deep learning network.
[Download](https://github.com/johnros/SimpleLearner) from GitHub.

- __Scraping ArXiv__:
Script for scraping ArXiv meta data and doing some exploratory statistics of manuscript ArXiving.
[Download](https://github.com/johnros/scaping_arxiv) from github.

- __SelectiveCI R package__:
Implements post-selection confidence intervals, presented in [our paper](http://www.ncbi.nlm.nih.gov/pubmed/25153699). 
[Download](https://github.com/johnros/selectiveCI) from github.

- __FPF R Package__:
Finds the prevalence of activation in fMRI group studies, presented in [our paper](http://www.sciencedirect.com/science/article/pii/S1053811913008859). 
    - [Download](https://r-forge.r-project.org/projects/rosenblatt1/) from R-Forge.
    - [Link](https://docs.google.com/document/d/1YtipQq5NdpLr9TY74eIcTreaXjbHTwOfx0Ee6QRODdc/edit) to tutorial.

## Software I use

- [Ubuntu](http://www.ubuntu.com/)- a friendly Linux distribution with Hebrew support.
- Data:
    - [R](http://www.r-project.org/)- for programming with data. I also maintain the [Israeli R user group](http://groups.google.com/group/israel-r-user-group).
    - [RStudio Server](http://www.rstudio.com/ide/docs/server/getting_started) running in the [AWS](http://aws.amazon.com/) cloud for data analysis (see my [blogpost](http://www.r-statistics.com/2013/07/analyzing-your-data-on-the-aws-cloud-with-r/)).
- Typesetting:
    - [TexStudio](http://texstudio.sourceforge.net/) for LaTeX editing. 
    - [bookdown](https://www.rstudio.com/resources/webinars/introducing-bookdown/) for authoring articles, books, and reports.
- Version control: [git](http://git-scm.com/) with [github](https://github.com/) for code, manuscripts, etc.
- [Scribus](http://www.scribus.net/canvas/Scribus)- for scientific posters. 
- [Zotero](http://www.zotero.org/)- for managing references (I like [Mendeley](http://www.mendeley.com/), and [PaperPile](https://paperpile.com/app) but I am already addicted). 
- [Calibre](http://calibre-ebook.com/) for managing my (e)book library.
- [Reeder](http://reederapp.com/)- by far my favorite RSS reader (since GoogleReader closed).
- [Pocket](http://getpocket.com/)- For all the "I want to read this later" sites.
- [Jekyll](http://jekyllrb.com/) with GitHub: for blogging.


## Software I want to try but didn't have the time yet:

- [Mendeley](http://www.mendeley.com/) or [Paperpile](https://paperpile.com/) for reference management. 
- [Julia](http://julialang.org/).
- [Python](https://www.python.org/).


## Hardware I use

- __Server__- Lenovo x3850-X6: 
Just because I find that the batch cluster computing paradigm (e.g. [Condor](https://en.wikipedia.org/wiki/HTCondor), [SGE](https://en.wikipedia.org/wiki/Oracle_Grid_Engine), etc.) is not suited for modern interactive data analysis. I found that you can get much more done with a single, massive, multiple core, RAM rich, server (running RStudio Server obviously).

- __Laptop__- Lenovo [T460s](http://shop.lenovo.com/il/en/laptops/thinkpad/t-series/t460s/): The size of the X1 with the power of the T series. 

- __Cloud__- [AWS](http://aws.amazon.com/): 
For any ad-hoc hardware needs (which is quite often for me), I [just start](http://www.r-statistics.com/2013/07/analyzing-your-data-on-the-aws-cloud-with-r/) an EC2 instance.