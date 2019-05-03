---
title: My workflow
subtitle: Draft 
layout: post
tags: ["phd", "overview","infrastructure", "statistics", "drafts"]
---

# My Workflow

So with a magnitude of grey literauture and a selective group of research guides I have thought about this problem in stages. The first stage is the research inforstructure. I think of this as the building blocks of all research projects (reports, manuscripts, etc). There are then choices between the types of software, packages and other tools I use within this inforstructure. The workflow is the timeline that links these components into a cronolocigical order. 

- Inforstructure

- Software

- Tools

- Packages


- [Packaging data publication](https://peerj.com/preprints/3192/)

- [Tidytools package]()

# Inforstructure

# Software

The key software and packages I use for my workflow are:

## File building

Im not sure what this is actually meant to represent but I see these options as packages making [packages](https://wlandau.github.io/2016/06/14/workflow/)

### Project oriented workflow

[Post](https://www.r-bloggers.com/%F0%9F%93%81-project-oriented-workflow/): Detailed and long.

### packrat

In mid-August of 2016, Eric Nantz of the R-Podcast converted me to packrat (by Kevin Ushey and others at RStudio), a package that lengthens the shelf life of R projects. [Packrat](https://rstudio.github.io/packrat/) maintains local snapshots of dependencies so that your project won't break when external packages are updated. Just be sure your current working directory is the root directory of your project when you run remake::make() or the Makefile. Also, if you use a shell.sh with your Makefile, be sure to modify module load R so that it points to the version of R corresponding to your 'packrat' library. You can learn more about packrat with the hands-on walk-through.

### ProjectTemplate

- [ProjectTemplate](https://cran.r-project.org/web/packages/ProjectTemplate/ProjectTemplate.pdf) and the webpage is [here](http://projecttemplate.net/).
- A workshop using this [package](https://github.com/jeromyanglim/leuven2016rworkshop)
- [A blog post](https://www.r-bloggers.com/in-praise-of-projecttemplate-for-reproducible-research/): Shows very complex file structure. Could it be easier?

## Packages

**FrOM R4DS book:** One day you will need to quit R, go do something else and return to your analysis the next day. One day you will be working on multiple analyses simultaneously that all use R and you want to keep them separate. One day you will need to bring data from the outside world into R and send numerical results and figures from R back out into the world. To handle these real life situations, you need to make two decisions:

1.  What about your analysis is "real", i.e. what will you save as your 
    lasting record of what happened?

1.  Where does your analysis "live"?

The project file in RStudio helps with this hugely. THis is how that file deals with the problem.

### Rstudio .Rproj

As a beginning R user, it's OK to consider your environment (i.e. the objects listed in the environment pane) "real". However, in the long run, you'll be much better off if you consider your R scripts as "real". 

With your R scripts (and your data files), you can recreate the environment. It's much harder to recreate your R scripts from your environment! You'll either have to retype a lot of code from memory (making mistakes all the way) or you'll have to carefully mine your R history.

To foster this behaviour, I highly recommend that you instruct RStudio not to preserve your workspace between sessions:

```{r, echo = FALSE, out.width = "75%"}
knitr::include_graphics("screenshots/rstudio-workspace.png")
```

This will cause you some short-term pain, because now when you restart RStudio it will not remember the results of the code that you ran last time. But this short-term pain will save you long-term agony because it forces you to capture all important interactions in your code. There's nothing worse than discovering three months after the fact that you've only stored the results of an important calculation in your workspace, not the calculation itself in your code. 

There is a great pair of keyboard shortcuts that will work together to make sure you've captured the important parts of your code in the editor:

1. Press Cmd/Ctrl + Shift + F10 to restart RStudio.
2. Press Cmd/Ctrl + Shift + S to rerun the current script.

I use this pattern hundreds of times a week.

## Where does your analysis live?

R has a powerful notion of the __working directory__. This is where R looks for files that you ask it to load, and where it will put any files that you ask it to save. RStudio shows your current working directory at the top of the console:

```{r, echo = FALSE, out.width = "50%"}
knitr::include_graphics("screenshots/rstudio-wd.png")
```

And you can print this out in R code by running `getwd()`:

```{r eval = FALSE}
getwd()
#> [1] "/Users/hadley/Documents/r4ds/r4ds"
```

As a beginning R user, it's OK to let your home directory, documents directory, or any other weird directory on your computer be R's working directory. But you're six chapters into this book, and you're no longer a rank beginner. Very soon now you should evolve to organising your analytical projects into directories and, when working on a project, setting R's working directory to the associated directory.

__I do not recommend it__, but you can also set the working directory from within R:

```{r eval = FALSE}
setwd("/path/to/my/CoolProject")
```

But you should never do this because there's a better way; a way that also puts you on the path to managing your R work like an expert.

R experts keep all the files associated with a project together --- input data, R scripts, analytical results, figures. This is such a wise and common practice that RStudio has built-in support for this via __projects__.

Let's make a project for you to use while you're working through the rest of this book. Click File > New Project, then:

```{r, echo = FALSE, out.width = "50%"}
knitr::include_graphics("screenshots/rstudio-project-1.png")
knitr::include_graphics("screenshots/rstudio-project-2.png")
knitr::include_graphics("screenshots/rstudio-project-3.png")
```

Call your project `r4ds` and think carefully about which _subdirectory_ you put the project in. If you don't store it somewhere sensible, it will be hard to find it in the future!

Once this process is complete, you'll get a new RStudio project just for this book. Check that the "home" directory of your project is the current working directory:

```{r eval = FALSE}
getwd()
#> [1] /Users/hadley/Documents/r4ds/r4ds
```

Whenever you refer to a file with a relative path it will look for it here. 

Now enter the following commands in the script editor, and save the file, calling it "diamonds.R". Next, run the complete script which will save a PDF and CSV file into your project directory. Don't worry about the details, you'll learn them later in the book.

```{r toy-line, eval = FALSE}
library(tidyverse)

ggplot(diamonds, aes(carat, price)) + 
  geom_hex()
ggsave("diamonds.pdf")

write_csv(diamonds, "diamonds.csv")
```

Quit RStudio. Inspect the folder associated with your project --- notice the `.Rproj` file. Double-click that file to re-open the project. Notice you get back to where you left off: it's the same working directory and command history, and all the files you were working on are still open. Because you followed my instructions above, you will, however, have a completely fresh environment, guaranteeing that you're starting with a clean slate.

In your favorite OS-specific way, search your computer for `diamonds.pdf` and you will find the PDF (no surprise) but _also the script that created it_ (`diamonds.R`). This is huge win! One day you will want to remake a figure or just understand where it came from. If you rigorously save figures to files __with R code__ and never with the mouse or the clipboard, you will be able to reproduce old work with ease!

## Paths and directories

Paths and directories are a little complicated because there are two basic styles of paths: Mac/Linux and Windows. There are three chief ways in which they differ:

1.  The most important difference is how you separate the components of the
    path. Mac and Linux uses slashes (e.g. `plots/diamonds.pdf`) and Windows
    uses backslashes (e.g. `plots\diamonds.pdf`). R can work with either type
    (no matter what platform you're currently using), but unfortunately, 
    backslashes mean something special to R, and to get a single backslash 
    in the path, you need to type two backslashes! That makes life frustrating, 
    so I recommend always using the Linux/Mac style with forward slashes.

1.  Absolute paths (i.e. paths that point to the same place regardless of 
    your working directory) look different. In Windows they start with a drive
    letter (e.g. `C:`) or two backslashes (e.g. `\\servername`) and in
    Mac/Linux they start with a slash "/" (e.g. `/users/hadley`). You should
    __never__ use absolute paths in your scripts, because they hinder sharing: 
    no one else will have exactly the same directory configuration as you.

1.  The last minor difference is the place that `~` points to. `~` is a
    convenient shortcut to your home directory. Windows doesn't really have 
    the notion of a home directory, so it instead points to your documents
    directory.

## Summary

In summary, RStudio projects give you a solid workflow that will serve you well in the future:

* Create an RStudio project for each data analysis project. 

* Keep data files there; we'll talk about loading them into R in 
  [data import].

* Keep scripts there; edit them, run them in bits or as a whole.

* Save your outputs (plots and cleaned data) there.

* Only ever use relative paths, not absolute paths.

Everything you need is in one place, and cleanly separated from all the other projects that you are working on.

Hadley wickham book on [R Packages](http://r-pkgs.had.co.nz/).

### R Package vignettes

- [rrtools](https://github.com/benmarwick/rrtools)

## Version control

## Markdown

# Additional resources for reference

## What's a reproducible report?

For the purposes of this guide, a report is a scientific document that contains not only the text that makes up the manuscript, but also the code that generates the figures and the statistics that are reported in your manuscript. Ideally, the report is part of a self-contained project that may contain your data, your initial exploratory analyses, the final product, and the code needed to generate them.

This manuscript can be a scientific article, a conference presentation, a technical report, or a document to share your progress with your collaborators. The end product may not show any code and therefore it may not look like it was generated differently from other documents.

Typically a report contains code for data manipulation, data analysis, and figure generation alongside the text that constitutes the heart of the report. Because of this hybrid nature, if left unchecked, this mix can lead to a big mess that can be difficult to maintain and debug. In this guide, we will provide you with some advice on how to keep your report manageable.

---
Box xx: What is the difference between repeatability and reproducibility?

**Repeatability** describes how close are the results of an experiment conducted under the same conditions (same instruments, same operators, etc.). **Reproducibility** describes how close are the results of an experiment conducted under similar but different conditions. Repeatability ensures that you would obtain similar results when running your code on your own laptop at different times; while reproducibility ensures that giving your code to someone else would allow them to obtain the same results as yours.
---

## Why a reproducible report?

Did you ever have to redo an analysis 6 months later, and it was difficult. You forgot which one of the 15 files with "final" in their names was really the one you should have used? Have you ever spent several hours assembling an intricate figure with your favorite drawing program, just to realize that your collaborators had forgotten to send you the latest batch of data? Writing a reproducible report alleviates some of these hurdles. By automating how the figures and the statistics in your report are generated, you are leaving a code trail that you, your collaborators, or your readers can take, and that leads to your original data. This path to the raw data increases the transparency of your science. However, in order for the six-month-in-the-future you, your collaborators, and your readers, to be able to take this path, it is important that you organize your code and your data files consistently.

Not only does writing a reproducible report increase the transparency of your science, it reduces the mistakes that result from copying and pasting across software. Keeping the content of your manuscript in sync with the output of your statistical program is challenging. By specifying directly the output of your model in your text, it is easier to make sure you are referring to the correct model with the correct parameters. To be the devil's advocate, one could argue that the additional code that will need to be written to integrate the results within the text could lead to additional errors. However, these bugs are possible to detect (contrary to mistakes done by copying and pasting the correct numbers), and their consequences can be assessed by re-running the code generating the manuscript after fixing them.

Writing a reproducible report allows you to tell a much richer story than the narrative in the report by itself does. The text in your report does not usually show the different approaches and analyses you have tried before coming up with the final results. With a reproducible report, you can provide readers who want to know more about how you obtained the results in your paper, the approaches you tried and the their results. These can be included as supplementary material or tagged in the history of your version control system.

To make your report reproducible, your code will need to be self-contained. As a consequence, you will be able to re-use the code you wrote for one project in another one. Therefore, if initially it might slow you down to make your code reproducible, it is an investment in the future as you will be able to re-use and build upon it in the future. Additionally, others might be able to also re-use your code, and apply it for their own data. Your efforts may speed up the overall scientific process (you or your colleagues won't need to re-invent the wheel for each project), and you could get more citations on your papers.

It can feel daunting to get started with writing a reproducible report because of the technical skills and knowledge required. However, a partially reproducible report is better than a non-reproducible one. So each step you take towards reproducibility is worth taking, and sets you up to take the next one for the next project.


## How to do a report using RMarkdown?

Programming languages typically used by scientistics for data analysis have libraries or packages that can be used to generate reproducible reports. The most popular ones are Jupyter Notebooks for scientists who primarily use python and RMarkdown for those who use R. While they both share many commonalities, their implementation and everyday applications differ. Here, we focus on RMarkdown.

RMarkdown is a file format (typically saved with the `Rmd` extension) that can contain: a YAML header (see next section), text, code chunks, and inline code. The `rmarkdown` package converts this file into a report most commonly into HTML or PDF.

The `rmarkdown` package automates a multi-step process (Fig. xx). Under the hood, it calls the `knitr` package that converts the Rmd file into a markdown file. In the process, `knitr` takes all the code chunks and the inline code, run them through R (or other programs), capture their output, and incorporates them in the report. Afterwards, `rmarkdown` calls the pandoc program (it is an external program that is not related to R) that can take the markdown file and converts to a variety of formats. For pandoc to generate PDF files, you will need a functional [installation of LaTeX](https://www.latex-project.org/get/) that you will need to install separately.

The `bookdown` package comes in to take care of numbering the figures and tables, as well as dealing with citations. As its name suggests, this package can be used to author books, but it is also well-suited to help generating reports.

![Relations between the different R packages and tools used to generate reports from RMarkdown files](rmarkdown-pieces.png)


### the YAML header

The YAML header is at the top of your file, it is delineated by three dashes (`---`) at the top and at the bottom of it. It is optional, but can be used to specify:

* the characteristics of your document: the title, authors, date of creation.
* the arguments to pass to pandoc to control the format of the output as
  well as additional information such as the bibliography file and the
  formatting of the list of references.
* parameters for your report: for instance, you can specify a parameter such that your report will only use a subset of your data so the final product will be generated quickly when you are developing the code for your project. Once your code is working, you can switch to the full dataset.


### Code chunks

Code chunks are	interspersed within the text of the report. They are delineated by three backticks (` ``` `) at the top and at the bottom of it. The top backticks are followed by a curly bracket that specify: (1) the language in which the code chunk is written, (2) the name of the chunk (optional but good practice), (3) `knitr` options that control whether and how the code, the output, or the figure are interpreted and displayed. Everything that comes after the name of the chunk has to be a valid R expression: the strings need be quoted, the arguments are separated by commas, and logical values (`TRUE`/`FALSE`) need to be capitalized.


### How to deal with figures?

The `knitr` package provides many options to finely control how your figures are going to be generated. Some of `knitr`'s options can be set individually for each chunk or be set globally. For a reproducible report, it is common practice to have chunk at the beginning of the report that sets default options for the figures. It is also usually a good place to load all the packages you will need for your analysis. For instance the following chunk will do the following:

- all the figures generated by the report will be placed in the `figures/` sub-directory
- all the figures will be 6.5 x 4 inches and centered in the text.


````r
```{r figure-setup, echo=FALSE, include=FALSE}
knitr::opts_chunk$set(fig.path="figures/", fig.width=6.5,
                      fig.height=4, fig.align="center")
library(tidyverse)
```
````

Additionally, this chunk will be named `figure-setup`, and we use the `echo=FALSE` option so the code for the chunk will not be displayed in the report, and use the `include=FALSE` option so no output produced by this chunk will be included in the report.

For our figures, we can now do

````r
```{r sepal-width-length, fig.cap='Relation between sepal width and length in three species of _Iris_.'}
iris %>%
    ggplot(aes(x = Sepal.Width, y = Sepal.Length, color = Species)) +
    geom_point()
```
````

When this file will be processed, it will create an image file (`figures/sepal-width-length.png`) with the default dimension and the caption specified by the value of the `fig.cap` argument. You can use markdown formatting within the captions of your figures. This figure will have the label `fig:sepal-width-length` that we will be able to use for cross referencing (see below).

If you wish to incorporate a figure that is not generated by code (a photo of your field site or study organism), using the function `knitr::include_graphics()` takes care of many details for you, and generates labels and captions as if it was generated by code.

````r
```{r iris-picture}
knitr::include_graphics("figures/iris.jpg")
```
````

### How to deal with tables?

To generate tables, `knitr` comes with the function `kable` that might be sufficient to make simple tables to represent data frames within your report. However, there are many packages that provide more sophisticated approaches to display and format tabular data within your reports. This [page](https://hughjonesd.github.io/huxtable/design-principles.html) provides an overview of the capabilities of the different packages.

````r
```{r iris-table}
iris %>%
    group_by(Species) %>%
    summarize(sepal_length = mean(Sepal.Length),
              sepal_width = mean(Sepal.Width)) %>%
    knitr::kable(caption = "Mean sepal width and length for three species of _Iris_.")
```
````

Similarly to figures, when this is processed by knitr, the table will have the `tab:iris-table` label that can be used for cross-referencing.


### How to deal with cross-references?

Use the `\@ref(label)` syntax. For instance

```
On average _setosa_ has wider and shorter sepals than the other species
(Fig. \@ref(fig:sepal-width-length), Table \@ref(tab:iris-table)).
```

### How to deal with citations?

You need two things: a BibTeX file that contains all the citations you use in your manuscript and a CSL (Citation Style Language) file that specifies the format of your citation. Software citation managers such as Zotero or Mendeley provide options to generate BibTeX files for your citations. CSL files exist for most journals, and can be downloaded from: https://www.zotero.org/styles. This is a convenient search interface provided by Zotero but you do not need to use Zotero to download or use these files.

## Where can I find more information?

* The RStudio Markdown website: http://rmarkdown.rstudio.com/
* The bookdown website: https://bookdown.org/yihui/bookdown/



# Documenting and managing dependencies

Reproducibility is also about making sure someone else can re-use your code to obtain the same results as yours. Understanding why your analysis may not lead to the same results on a different computer can be useful to determine how careful you need to be in documenting your setup.

For someone else to be able to reproduce the results included in your report, you need to provide more than the code and the data. You also need to document the exact versions of all the packages, libraries, and software you used, and potentially your operating system as well as your hardware.

R itself is very stable, and the core team of developer takes backward compatibility (that old code works with recent version of R) very seriously. However, default values in some functions have changed, and new functions get introduced regularly. If you wrote your code on a recent version of R and give it to someone who hasn't upgraded recently, they may not be able to run your code. If R itself is stable, the packages are generally much less stable. New functionalities get introduced with each versions, some functions get deprecated, and defaults options change. Code written for one version of a package may produce very different results with a more recent version.

Documenting and managing the dependencies of your project correctly can be a complicated. However, even simple documentation that helps others understand the setup you used can have a big impact. Here we present three levels of complexity to document the dependencies for your projects.


## Show the packages you used

With R, the simplest (but useful and important) approach to document your dependencies is to report the output of `sessionInfo()` (or `devtools::session_info()`). Among other information, this will show all the packages (and their versions) that are loaded in the session you used to run your analysis. If someone wants to recreate your analysis, they will know which packages they will need to install.


## Use packages that help recreate your setup

The `checkpoint` package provides a way to download all the packages at a given date from CRAN. Thus, from the output provided by `sessionInfo()`, they could recreate your setup. It however makes two important assumptions: all your packages were up-to-date with CRAN at the time of your analysis; you were not using packages that are not available from CRAN (e.g. the development version of a package directly from a git repository).

Another approach is to use the `packrat` package. This package creates a library (a collection of packages) directly within your analysis directory. It increases the size of your project as all the source code for the packages is included, but it ensures that someone can recreate more reliably the same environment as the one you used for your analysis. It also makes it easier because the installation of these packages is fully automated for the person wanting to have the same setup.

## Use containers to share your setup

A step further in complexity is to use Docker. With Docker you recreate an entire operating system with all the software, data, and packages needed for your analysis. It is more technical to set up but it allows you to distribute the exact same environment as the one you used. If you want others to be able reproduce your results, and your analysis depends on software that can be difficult to install, it is an option that might be worth exploring.
