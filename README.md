# Exploring and analyzing LC-MS data with *Spectra* and *xcms*

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3909299.svg)](https://doi.org/10.5281/zenodo.3909299)

- *2023-05-25*: update and restructure whole document for *xcms* versio 4 that
  uses the [Spectra](https://github.com/RforMassSpectrometry/Spectra) and
  [MsExperiment](https://github.com/RforMassSpectrometry/MsExperiment) packages
  for data representation.
- *2021-03-25*: provide a description on the *good practice* to define a
  phenodata/data files table containing also the names of the raw data files
  along with all sample information.
- *2020-06-15*: use new more data-driven gap-filling approach: `fillChromPeaks`
  with `ChromPeakAreaParam`.
- *2020-02-04*: add `refineChromPeaks` to allow *refinement* of peak detection
  results. Also, add the `quantify` method to extract the preprocessing results
  as `SummarizedExperiment`. Both required `xcms` version >= 2.9.2.
- *2019-09-29*: More updates and expansion of descriptions.
- *2019-06-20*: Updated to match `xcms` functionality available with
Bioconductor version 3.9.

This workshop provides an overview of recent developments in Bioconductor to
work with mass spectrometry
([MsExperiment](https://github.com/RforMassSpectrometry/MsExperiment),
[Spectra](https://github.com/RforMassSpectrometry/Spectra)) and specifically
LC-MS data ([xcms](https://github.com/sneumann/xcms)) and walks through the
preprocessing of a small data set emphasizing on selection of data-dependent
settings for the individual pre-processing steps. The present workshop
represents an updated version of the workshop given at the Metabolomics Society
conference 2018 in Seattle (http://metabolomics2018.org).

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


## Prerequisites

The analysis in this document requires an R version >= 4.3.0 and recent versions
of the `MsExperiment`, `Spectra` and in particular the `xcms` (version >= 3.99.0
is needed) packages. The code below installs all packages for the analysis.

```r
#' Install the Bioconductor package manager
install.packages("BiocManager")

#' Install the required packages
BiocManager::install(c("msdata",
                       "Spectra",
                       "MsExperiment",
                       "MetaboCoreUtils",
                       "MsCoreUtils",
                       "png"))
BiocManager::install("sneumann/xcms")
```


## Files

- [xcms-preprocessing.Rmd](./xcms-preprocessing.Rmd): file containing the
  complete R code and expanded description. Can be converted to a html file with
  `rmarkdown::render("xcms-preprocessing.Rmd")`.

- [xcms-preprocessing-ioslides.Rmd](./xcms-preprocessing-ioslides.Rmd): R
  markdown file that is rendered (with
  `rmarkdown::render("xcms-preprocessing-ioslides.Rmd")` into the html
  (ioslides-based) presentation for the conference. This file contains most of
  the R commands from `xcms-preprocessing.Rmd` but only few
  descriptions. (outdated!)

- [xcms-preprocessing-bullets.Rmd](./xcms-preprocessing-bullets.Rmd): file with
  complete R code but strongly reduced descriptive content (in form of bullet
  points). This file is thought to be used for an interactive presentation with
  RStudio (i.e. live execution of commands). (outdated!)
  
