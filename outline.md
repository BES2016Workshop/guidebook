

## What's a reproducible report?

For the purposes of this guide, a report is a scientific document that contains not only the text that makes up the manuscript, but it also contains the code that generates the figures and the statistics that are reported in your manuscript. Ideally, the report is part of a self-contained project that may contain your data, your initial exploratory analyses, and the final product.

This manuscript can be a scientific article, a conference presentation, a technical report, or a document to share your progress with your collaborators. The end product may not show any code and therefore it may not look like it was generated no differently from other documents.

Typically a report contains code for data manipulation, data analysis, and figure generation alongside the text that constitutes the heart of the report. Because of this hybrid nature, if left unchecked, this mix can lead to a big mess that is difficult to maintain and debug. In this guide, we will provide you with some advice on how to keep your report manageable.


---

Box ##: What is the difference between repeatability and reproducibility?

**Repeatability** describes how close are the results of an experiment conducted under the same conditions (same instruments, same operators, etc.). **Reproducibility** describes how close are the results of an experiment conducted under similar but different conditions. Repeatability ensures that you would obtain similar results when running your code on your own laptop at different times; while reproducibility ensures that giving your code to someone else would allow them to obtain the same results as yours.

---



## Why a reproducible report?

Did you ever have to redo an analysis 6 months later, and it was difficult. You forgot which one of the 15 files with "final" in their names was really the one you should have used? Have you ever spent several hours assembling an intricate figure with your favorite drawing program, just to realize that your collaborators had forgotten to send you the latest batch of data? Writing a reproducible report alleviates some of these hurdles. By automating how the figures and the statistics in your report are generated, you are leaving a code trail that you, your collaborators, or your readers can take and lead to your original data. This path to the raw data increases the transparency of your science. However, in order for the six-month-in-the-future you, your collaborators, and your readers, to be able to take this path, it is important that you organize your code and your data files consistently.

Not only writing a reproducible report increases the transparency of your science, it reduces the mistakes that result from copying and pasting across software. Keeping the content of your manuscript in sync with the output of your statistical program is challenging. By specifying directly the output of your model in your text, it is easier to make sure you are referring to the correct model with the correct parameters. To be the devil's advocate, one could argue that the additional code that will need to be written to integrate the results within the text could also lead to mistake. However, these coding mistakes are possible to detect (contrary to mistakes done by copying and pasting the correct numbers), and its consequences can be assessed by re-running the generation of the mansucript after fixing it.

Writing a reproducible report allows you to tell a much richer story than the narrative in the report by itself does. The text in your report tells does not usually show the different approaches and analyses you have tried before coming up with the final results. With a reproducible report, you can provide readers who want to know more about how you obtain the results in your paper about the approaches you tried and the their results. These can be included as supplementary material or tagged in the history of your version control system.

To make your report reproducible, your code will need to be self-contained. As a consequence, you will be able to re-use the code you wrote for one project in another one. Therefore, if initially it might slow you down to make your code reproducible, it is an investment in the future as you will be able to re-use and build up on it in the future. Additionally, others might be able to also re-use your code, and apply it for their own data. Your efforts may speed up the overall scientific process (you or your colleagues won't need to re-invent the wheel for each project), and you could get more citations on your papers.

It can feel daunting to get started with writing a reproducible report because of the technical skills and knowledge required. However, a partially reproducible report is better than a non-reproducible one. So each step you take towards reproducibility is worth taking, and sets you up to take the next one for the next project.


## How to do a report?

* There is no single right way of doing this.

* Because other researchers are doing this in the "open", their code is
  avaialble for you to study. You can learn from their examples how they
  organize their analyses.

* Planning is helpful. Figuring out the steps you'll need to take to go from raw
  data to final figures, will allow you to structure your code better. And even
  if you need to revise your plan as your project evolves, this initial planning
  will save you time when you'll need to re-organize your code.

* Good: clear documentation of which script does what, and how the results were assembled from them
* Better: take advantage of Rmarkdown
* Best: fully automated and contained example

* Use version control

* Learn how to write functions
* It's best if you make use of functions to isolate the various aspects of your
  code. Writing functions make the code more modular, and usually it reduces the
  chances of introducing bugs. By having, small functions that only do 1 thing,
  you can have a better control. You can then build on complexity by putting
  this functions together. If you give them explicit names, then you build in
  complexity, you are stringing together these small modular pieces.

* Just like when you are writing code for your analysis, the code that allows
  you to generate your manuscript should also be well documented.

* Take advantage of variables to

* Hard-code as little as possible

Historically, the software and tools have been developed to deal with either the text from a manuscript or the computer code. However, because reports mix the two, and is still a fairly recent concept, the software to write and manage this type of content is still being developed.

### In the R world

* What are the tools?
* Rmarkdown the markup language vs. **`rmarkdown`** the package
* knitr and pandoc

#### Anatomy of a Rmarkdown document

* the YAML header
*
* How to deal with figures?
* How to deal with tables?
* How to deal with citations?


### In the python world



## What to include in the report?

* Exploratory/research phase
* Final products

## How to work with collaborators?

## How to get started?

# Dependency management

* Reproducibility is also about making sure someone else can re-use your code to
  obtain the same results as yours. Understanding why this might not be the case
  can be useful to determine how careful you need to be in documenting your
  setup.

* For someone else to be able to reproduce the results from your code, you'd
  need more than just the code. You'd also need to specify the exact packages
  you used, the version of the software, and potentially your operating system.

* R itself is very stable, but there are still default that changes. R packages
  are much less stable, and it's not good practice, but it happen often that the
  behavior of functions change completely.

* Dependencies as a way to document the setup you used to produce your results,
  vs. to help others recreate your analysis.

## How to make your code self contained?

* Do not use `setwd()`, instead use Rproj (but not needed)
* Use relative paths
* Document where the data is coming from, how it is formatted, what are the
  units

## How to document your dependencies?

* Good: report the output of your `session_info`
* Better: use packrat or other package managers (drat, miniCRAN, checkpoint...)



---

Resources:
* Best practices for Scientific Computing (http://journals.plos.org/plosbiology/article?id=10.1371/journal.pbio.1001745)
* Good enough practices for Scientific Computing (https://swcarpentry.github.io/good-enough-practices-in-scientific-computing/)
* 10 simples rules for reproducible computational research: http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1003285
* A quick guide to organizing computational biology projects: http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1000424
* Ten Simple Rules for Digital Data Storage (http://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005097)
