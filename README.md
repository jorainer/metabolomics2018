# metabolomics2018

Workshop material for the xcms (version >= 3) workshop at the Metabolomics
Society conference 2018 in Seattle (http://metabolomics2018.org). The workshop
provides an overview of recent developments in Bioconductor to work with mass
spectrometry ([MSnbase](https://github.com/lgatto/MSnbase)) and specifically
LC-MS data ([xcms](https://github.com/sneumann/xcms)) and walks through the
preprocessing of a toy data set emphasizing on selection of data-dependent
settings for the individual pre-processing steps.

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
[xcms-preprocessing.html](https://jotsetung.github.io/metabolomics2018/xcms-preprocessing.html).


## Prerequisites

The analysis in this document requires an R version >= 3.5.0 and recent versions
of the `MSnbase` and `xcms` (version >= 3.3.1 is needed) packages. The code
below installs all packages for the analysis.

```
source("https://bioconductor.org/biocLite.R")
biocLite(c("xcms", "MSnbase", "doParallel", "msdata", "magrittr", "devtools"))
## Need xcms version > 3.3.1
if (packageVersion("xcms") < "3.3.1")
    devtools::install_github("sneumann/xcms", ref = "master") 
```


## Files

- [xcms-preprocessing.Rmd](./xcms-preprocessing.Rmd): file containing the
  complete R code and expanded description. Can be converted to a html file with
  `rmarkdown::render("xcms-preprocessing.Rmd")`.

- [xcms-preprocessing-ioslides.Rmd](./xcms-preprocessing-ioslides.Rmd): R
  markdown file that is rendered (with
  `rmarkdown::render("xcms-preprocessing-ioslides.Rmd")` into the html
  (ioslides-based) presentation for the conference. This file contains most of
  the R commands from `xcms-preprocessing.Rmd` but only few descriptions.

- [xcms-preprocessing-bullets.Rmd](./xcms-preprocessing-bullets.Rmd): file with
  complete R code but strongly reduced descriptive content (in form of bullet
  points). This file is thought to be used for an interactive presentation with
  RStudio (i.e. live execution of commands).
  
