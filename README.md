
<!-- README.md is generated from README.Rmd. Please edit that file -->

# chronos

<!-- badges: start -->

[![R-CMD-check](https://github.com/tesselle/chronos/workflows/R-CMD-check/badge.svg)](https://github.com/tesselle/chronos/actions)
[![codecov](https://codecov.io/gh/tesselle/chronos/branch/main/graph/badge.svg?token=UgoOXsZW86)](https://codecov.io/gh/tesselle/chronos)
[![CodeFactor](https://www.codefactor.io/repository/github/tesselle/chronos/badge/main)](https://www.codefactor.io/repository/github/tesselle/chronos/overview/main)

<a href="https://tesselle.r-universe.dev" class="pkgdown-devel"><img
src="https://tesselle.r-universe.dev/badges/chronos"
alt="r-universe" /></a>

[![Project Status: WIP – Initial development is in progress, but there
has not yet been a stable, usable release suitable for the
public.](https://www.repostatus.org/badges/latest/wip.svg)](https://www.repostatus.org/#wip)
<!-- badges: end -->

## Overview

A toolkit for temporal reasoning. **chronos** provides functions for
radiocarbon calibration and chronological analysis. It also includes
tools to describe and analyze finite time intervals.

## Installation

You can install the released version of **chronos** from
[CRAN](https://CRAN.R-project.org) with:

``` r
install.packages("chronos")
```

And the development version from [GitHub](https://github.com/) with:

``` r
# install.packages("remotes")
remotes::install_github("tesselle/chronos")
```

## Usage

``` r
## Load packages
library(chronos)
```

``` r
## Data from Bosch et al. 2015
data("ksarakil")

## Calibrate multiple dates
cal <- c14_calibrate(
  ages = ksarakil$date,
  errors = ksarakil$error,
  names = ksarakil$code,
  curves = "marine13",
  reservoir_offsets = 53,
  reservoir_errors = 43,
  from = 50000, to = 0
)

## Plot
plot(cal, panel.first = graphics::grid())
```

![](man/figures/README-calibration-1.png)<!-- -->

## Contributing

Please note that the **chronos** project is released with a [Contributor
Code of Conduct](https://www.tesselle.org/conduct.html). By contributing
to this project, you agree to abide by its terms.
