# Design document

<!-- README.md is generated from README.qmd. Please edit that file -->

# anndataR

<!-- badges: start -->

[![Lifecycle:
experimental](https://img.shields.io/badge/lifecycle-experimental-orange.svg)](https://lifecycle.r-lib.org/articles/stages.html#experimental)
[![CRAN
status](https://www.r-pkg.org/badges/version/anndataR.png)](https://CRAN.R-project.org/package=anndataR)
<!-- badges: end -->

`{anndataR}` is an R package that brings the power and flexibility of
AnnData to the R ecosystem, allowing you to effortlessly manipulate and
analyze your single-cell data. `{anndataR}` lets you work with backed
h5ad and zarr files, directly access various slots (e.g. X, obs, var,
obsm, obsp), or convert the data into SingleCellExperiment and Seurat
objects.

## Features

- Seamless Integration: `{anndataR}` bridges the gap between Python’s
  AnnData and popular R single-cell analysis tools like
  SingleCellExperiment and Seurat.
- Efficient Data Handling: The package supports backed h5ad and zarr
  file formats, allowing you to work with large datasets efficiently.
- Flexible Data Access: Access obs, var, obsp, and other slots directly,
  giving you the freedom to manipulate your data as needed.

## Design docs

- [Design document](doc/design.md): interface, OO-framework, approach
- [Challenges in reading h5ad files in R](doc/challenges.md)

## Installation

You can install the development version of `{anndataR}` like so:

``` r
devtools::install_github("scverse/anndataR")
```

## Example

Here’s a quick example of how to use `{anndataR}`:

``` r
library(anndataR)

download.file("https://github.com/chanzuckerberg/cellxgene/raw/main/example-dataset/pbmc3k.h5ad", "pbmc3k.h5ad")

# Read an h5ad file
adata <- read_h5ad("pbmc3k.h5ad")

# Access the obs DataFrame
adata_obs <- adata$obs

# Convert the AnnData object to a SingleCellExperiment object
sce <- adata$to_sce()
```
