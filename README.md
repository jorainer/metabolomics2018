- *2019-09-29*: More updates and expansion of descriptions.
- *2019-06-20*: Updated to match `xcms` functionality available with
Bioconductor version 3.9.

# LC-MS data pre-processing with `xcms`

This workshop provides an overview of recent developments in Bioconductor to
work with mass spectrometry ([MSnbase](https://github.com/lgatto/MSnbase)) and
specifically LC-MS data ([xcms](https://github.com/sneumann/xcms)) and walks
through the preprocessing of a toy data set emphasizing on selection of
data-dependent settings for the individual pre-processing steps. The present
workshop represents an updated version of the workshop given at the Metabolomics
Society conference 2018 in Seattle (http://metabolomics2018.org).

Covered topics are:
- Data import and representation.
- Accessing, subsetting and visualizing data.
- Centroiding of profile MS data.
- Chromatographic peak detection.
- Empirically determine appropriate settings for the analyzed data set.
- Evaluation of identified peaks.
- Alignment (retention time correction).
- Correspondence (grouping of chromatographic peaks across samples).

The full R code of all examples along with comprehensive descriptions is
provided in the [xcms-preprocessing.Rmd](./xcms-preprocessing.Rmd) file. This
file can be opened with e.g. RStudio which allows execution of the individual R
commands (see section below for additionally required R packages). The R command
`rmarkdown::render("xcms-preprocessing.Rmd")` would generate the html file
[xcms-preprocessing.html](https://jorainer.github.io/metabolomics2018/xcms-preprocessing.html).

For those that can not attend the workshop: you can have a look at the
presentation online [xcms-preprocessing-ioslides.html](https://jorainer.github.io/metabolomics2018/xcms-preprocessing-ioslides.html).


## Prerequisites

The analysis in this document requires an R version >= 3.6.0 and recent versions
of the `MSnbase` and `xcms` (version >= 3.3.1 is needed) packages. The code
below installs all packages for the analysis.

```r
install("BiocManager")
BiocManager::install(c("xcms",
                       "MSnbase",
                       "msdata",
                       "magrittr",
                       "devtools",
                       "BiocParallel"))
```


## Files

- [xcms-preprocessing.Rmd](./xcms-preprocessing.Rmd): file containing the
  complete R code and expanded description. Can be converted to a html file with
  `rmarkdown::render("xcms-preprocessing.Rmd")`.

- [xcms-preprocessing-ioslides.Rmd](./xcms-preprocessing-ioslides.Rmd): R
  markdown file that is rendered (with
  `rmarkdown::render("xcms-preprocessing-ioslides.Rmd")` into the html
  (ioslides-based) presentation for the conference. This file contains most of
  the R commands from `xcms-preprocessing.Rmd` but only few descriptions. (outdated!)

- [xcms-preprocessing-bullets.Rmd](./xcms-preprocessing-bullets.Rmd): file with
  complete R code but strongly reduced descriptive content (in form of bullet
  points). This file is thought to be used for an interactive presentation with
  RStudio (i.e. live execution of commands). (outdated!)
  
