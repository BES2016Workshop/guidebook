---
title: Reproducible workflow
subtitle: Draft 
layout: post
tags: ["phd", "overview","infrastructure", "statistics", "drafts"]
---

There are many many different resources on reproducible workflows. This document collects the current resources avaliable with a strong focus on [R](https://cran.r-project.org/) and ( [RMarkdown](https://rmarkdown.rstudio.com/); [blog here](https://www.r-bloggers.com/composing-reproducible-manuscripts-using-r-markdown/)). 

I have started [this repository]() from a combination of different git repositories:

- [BES guidelines](https://github.com/BES2016Workshop/guidebook)

My workflow has a distinctly ecological feel along with the tidyverse approach of [tooling](https://style.tidyverse.org/index.html). I apologise for this in advance. 
If you are not a [R](https://cran.r-project.org/) user I would recommend modifying this workflow or finding another workflow with the same components but in your field.

# Overview

Since the development of [R](https://cran.r-project.org/) and [RStudio](https://rstudio.com/) (and a magnitude of other IT changes happening at the same time) there are now tools for working with issues to do with [reproducibility](https://www.nature.com/news/1-500-scientists-lift-the-lid-on-reproducibility-1.19970). There are many blogs from a simple web search. 
Here is a collection of the posts I have drawn inspiration from:

- [R bloggers posts](https://www.r-bloggers.com/): This is a collection of the current blogs on [R bloggers](https://www.r-bloggers.com).

- [R workflow](https://maraaverick.rbind.io/2017/09/r-workflow-fun/): Mara Averick has a post that looks better than this and has many of the same resources just published a few years ago.

- [Methods in Ecology](https://methodsblog.com/2016/10/05/reproducibility-with-r/): A good blog that goes with the reproducible guidebook (2018).

- [workflow general tips](https://csgillespie.github.io/efficientR/workflow.html)

  - **Key points**
  1. Start without writing code but with a clear mind and perhaps a pen and paper. This will ensure you keep your objectives at the forefront of your mind, without getting lost in the technology.
  2. Make a plan. The size and nature will depend on the project but time-lines, resources and ‘chunking’ the work will make you more effective when you start.
  3. Select the packages you will use for implementing the plan early. Minutes spent researching and selecting from the available options could save hours in the future.
  4. Document your work at every stage: work can only be effective if it’s communicated clearly and code can only be efficiently understood if it’s commented.
  5. Make your entire workflow as reproducible as possible. knitr can help with this in the phase of documentation. [Reference here](https://csgillespie.github.io/efficientR/workflow.html)

- [Data Science and R/Python](https://community.rstudio.com/t/data-science-project-template-for-r/3230)

- [Truely reproducible](https://timogrossenbacher.ch/2017/07/a-truly-reproducible-r-workflow/)

- [EEB313H1](https://uoftcoders.github.io/rcourse/lec16-rmarkdown.html)

- [Good enough practices for Scientific Computing](https://swcarpentry.github.io/good-enough-practices-in-scientific-computing/)

- [Pitfalls to non-reproducible research](https://www.r-bloggers.com/reproducible-research-when-your-results-cant-be-reproduced/): This is a nice simple post on the three danger zones: R session context; OS context; Data versioning.
  
- [What is it?](https://www.r-bloggers.com/what-is-reproducible-research/): From Rbloggers. 

- [Truely reproducible web](https://www.r-bloggers.com/stencila-an-office-suite-for-reproducible-research/)

- [PeerJ stats help](https://peerj.com/collections/50-practicaldatascistats/)

- [Implmentation guide](http://blog.jom.link/implementation_basic_reproductible_workflow.html): Great post. I have used much of this for my workflow.

- [A list of sites I haven't sorted yet](https://www.one-tab.com/page/HngnpHOKRpuiqeQEB7_B7A)

#### Databases for reproducible packages

- [rOpenSci](https://ropensci.org/about/) is a non-profit initiative founded in 2011 by Karthik Ram, Scott Chamberlain, and Carl Boettiger to make scientific data retrieval reproducible. Over the past seven years we have developed an ecosystem of open source tools, we run annual conferences, and review community developed software.

- [The Reproducible Research CRAN Task View](https://cran.r-project.org/web/views/ReproducibleResearch.html)

Both of these pages are doing a great job at producing searchable interface for reproducible packages in R with documentation. 

# Journals

##### PLOS

- [Best practices for Scientific Computing](http://journals.plos.org/plosbiology/article?id=10.1371/journal.pbio.1001745)

- [10 simple rules for reproducible computational research](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003285)

- [A quick guide to organizing computational biology projects](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1000424)

- [Ten Simple Rules for Digital Data Storage](http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005097)

#### Ecology

##### [@cassey2006]


### [@nakagawa2015] 


### [@zotero-6387]



## Coding groups

- [Uni of Toronto Coders](https://github.com/UofTCoders)
  -[R course](https://github.com/UofTCoders/rcourse)
  
- [UBC statistics course](http://stat545.com/Classroom/)

With all the resources above I have created a evolving "workflow" for my research.

- [Distributed Workflows](https://cyberhelp.sesync.org/basic-git-lesson/2016/08/25/): This is a class on reproducible workflows in RStudio. Ian Carroll says:

*A single collaboration model – the centralized workflow – dominates collaborative research. There is a central hub, and everyone synchronizes their work to it. A number of researchers are nodes – consumers of that hub – and synchronize to that one place.*
