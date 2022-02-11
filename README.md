# reproducible-guidebook

This repository is my attempt at combining the current information on reproducible research into a comprehensive database of resources in the hope of somehow creating a more uniform understanding of the `reproducibility theorem` (cite?).

## Reproducible Guide

There are many many different resources on reproducible workflows. This document collects the current resources avaliable with a strong focus on R and (RMarkdown; blog here).

I have started this repository from a combination of different git repositories:

## BES guidelines

My workflow has a distinctly ecological feel along with the tidyverse approach of tooling. I apologise for this in advance. If you are not a R user I would recommend modifying this workflow or finding another workflow with the same components but in your field.

Overview
Since the development of R and RStudio (and a magnitude of other IT changes happening at the same time) there are now tools for working with issues to do with reproducibility. There are many blogs from a simple web search. Here is a collection of the posts I have drawn inspiration from:

R bloggers posts: This is a collection of the current blogs on R bloggers.

R workflow: Mara Averick has a post that looks better than this and has many of the same resources just published a few years ago.

Methods in Ecology: A good blog that goes with the reproducible guidebook (2018).

## workflow general tips: Key points

Start without writing code but with a clear mind and perhaps a pen and paper. This will ensure you keep your objectives at the forefront of your mind, without getting lost in the technology.

1. Make a plan: The size and nature will depend on the project but time-lines, resources and ‘chunking’ the work will make you more effective when you start.

2. Select the packages you will use for implementing the plan early. Minutes spent researching and selecting from the available options could save hours in the future.

3. Document your work at every stage: work can only be effective if it’s communicated clearly and code can only be efficiently understood if it’s commented.

4. Make your entire workflow as reproducible as possible. knitr can help with this in the phase of documentation. Reference here

## Draft only currently

A combination of blogs, research articles and guides for reproducible research

### To DO

- literature review
    - reproducible
    - reference all reproduce guides?
    - reproducibility in IT
    - reproducibility in data science
    - Combine .md post info into this `repo`

- file structure (anthony - in drafts)

- definitions (From nature/science and PNAS) - draft not pushed yet

- workflows
    - R
    - Python

- reproducibility guides
    - for genomics

## Status

Currently the main info is in `_drafts` and `resources.md` file.


### Posts

... coming

## References

```
@misc{repro-guide,
title={{Reproducibility in Science: A Guide to enhancing reproducibility in scientific results and writing}},
howpublished="\url{http://ropensci.github.io/reproducibility-guide/}"
}
```

### From Karl Broman guidebook

It is important to refer to these resources for supporting information. Feel free to develop and "correct" these resources where appropriate.

[![Project Status: Abandoned – Initial development has started, but there has not yet been a stable, usable release; the project has been abandoned and the author(s) do not intend on continuing development.](https://www.repostatus.org/badges/latest/abandoned.svg)](https://www.repostatus.org/#abandoned)

This is the project page for creating a guide to reproducible research.  The purpose is to be a quick references for best practices in making scientific research accessible and reproducible.  

Ideas for the guide came  [https://github.com/ropensci/hackathon/issues/22](https://github.com/ropensci/hackathon/issues/22) and [https://github.com/mozillascience/code-research-object/issues/2](https://github.com/mozillascience/code-research-object/issues/2).

The guide will be presented as a website, prototype is housed here: [http://ropensci.github.io/reproducibility-guide/](http://ropensci.github.io/reproducibility-guide/).  

If you think you can help in anyway, awesome.  Feel free to create issues with your ideas. Feedback is welcome and appreciated. 

**rOpenSci Hackathon**

Slack Channel: #reproducibility-guide

I have drawn on this simple guide a lot in developing this guide as it is a simple starting point along with the [BES guidelines 2018](/_assets/pdfs/BES_guide.pdf).

#### Initial steps toward reproducible research

"A minimal standard for data analysis and other scientific computations is
that they be _reproducible_: that the code and data are assembled in a
way so that another group can re-create all of the results (e.g., the
figures in a paper)." View Karl's tutorial [here](https://kbroman.org/steps2rr).

### Meta-analysis

This is used for the lit. review and extended this into a reproducible document.

Data Science and R/Python

Truely reproducible

EEB313H1

Good enough practices for Scientific Computing

Pitfalls to non-reproducible research: This is a nice simple post on the three danger zones: R session context; OS context; Data versioning.

What is it?: From Rbloggers.

Truely reproducible web

PeerJ stats help

Implmentation guide: Great post. I have used much of this for my workflow.

A list of sites I haven’t sorted yet

Databases for reproducible packages
rOpenSci is a non-profit initiative founded in 2011 by Karthik Ram, Scott Chamberlain, and Carl Boettiger to make scientific data retrieval reproducible. Over the past seven years we have developed an ecosystem of open source tools, we run annual conferences, and review community developed software.

The Reproducible Research CRAN Task View

Both of these pages are doing a great job at producing searchable interface for reproducible packages in R with documentation.

Journals
PLOS
Best practices for Scientific Computing

10 simple rules for reproducible computational research

A quick guide to organizing computational biology projects

Ten Simple Rules for Digital Data Storage

Ecology
[@cassey2006]
[@nakagawa2015]
[@zotero-6387]
Coding groups
Uni of Toronto Coders -R course

UBC statistics course

With all the resources above I have created a evolving “workflow” for my research.

Distributed Workflows: This is a class on reproducible workflows in RStudio. Ian Carroll says:
A single collaboration model – the centralized workflow – dominates collaborative research. There is a central hub, and everyone synchronizes their work to it. A number of researchers are nodes – consumers of that hub – and synchronize to that one place.