sprtt
================

<!-- badges: start -->

[![CRAN\_Status\_Badge](http://www.r-pkg.org/badges/version/sprtt?color=green)](https://cran.r-project.org/package=sprtt)
[![codecov](https://codecov.io/gh/MeikeSteinhilber/sprtt/branch/main/graph/badge.svg?token=IQHTDTRBAW)](https://codecov.io/gh/MeikeSteinhilber/sprtt)
[![lint](https://github.com/MeikeSteinhilber/sprtt/actions/workflows/lint.yaml/badge.svg)](https://github.com/MeikeSteinhilber/sprtt/actions/workflows/lint.yaml)

[![R-CMD-check-windows-macOs](https://github.com/MeikeSteinhilber/sprtt/workflows/R-CMD-check-windows-macOs/badge.svg)](https://github.com/MeikeSteinhilber/sprtt/actions)
[![R-CMD-check-ubuntu20.04](https://github.com/MeikeSteinhilber/sprtt/workflows/R-CMD-check-ubuntu20.04/badge.svg)](https://github.com/MeikeSteinhilber/sprtt/actions)
[![R-CMD-check-ubuntu16.04](https://github.com/MeikeSteinhilber/sprtt/workflows/R-CMD-check-ubuntu16.04/badge.svg)](https://github.com/MeikeSteinhilber/sprtt/actions)

<!-- badges: end -->

## Overview

**sprtt** provides Sequential Probability Ratio Tests (SPRT) using the
associated t-statistic:

-   `seq_ttest()` calculates the sequential test statistic.
-   `print_seq_ttest()` visualizes the test statistic.

## Installation

``` r
# Code for installation
```

### Development version

To get a bug fix or to use a feature from the development version, you
can install the development version of **sprtt** from GitHub.

``` r
# install.packages("devtools")
devtools::install_github("MeikeSteinhilber/sprtt")
```

## Usage

``` r
#load libraries
library(stats)
library(sprtt)

# one sample: numeric input
x <- rnorm(20, mean = 0, sd = 1)
seq_ttest(x, mu = 1, d = 0.8)

# one sample: formula input
x <- rnorm(20, mean = 0, sd = 1)
seq_ttest(x ~ 1, mu = 1, d = 0.8)

# two sample: numeric input
x <- rnorm(20, mean = 0, sd = 1)
y <- rnorm(20, mean = 1, sd = 1)
seq_ttest(x, y, d = 0.8)

# two sample: formula input
x <- rnorm(20, mean = 0, sd = 1)
y <- as.factor(c(rep(1, 10), rep(2, 10)))
seq_ttest(x ~ y, d = 0.8)

# NA in the data
x <- c(NA, rnorm(20, mean = 0, sd = 2), NA)
y <- as.factor(c(rep(1, 11), rep(2, 11)))
seq_ttest(x ~ y, d = 0.8, na.rm = TRUE)

# work with dataset (df_income is in the package included)
seq_ttest(monthly_income ~ sex, data = df_income, d = 0.8)
```
