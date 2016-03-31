
hms [![Travis-CI Build Status](https://travis-ci.org/krlmlr/hms.svg?branch=master)](https://travis-ci.org/krlmlr/hms) [![Coverage Status](https://img.shields.io/codecov/c/github/krlmlr/hms/master.svg)](https://codecov.io/github/krlmlr/hms?branch=master) [![CRAN_Status_Badge](http://www.r-pkg.org/badges/version/hms)](https://cran.r-project.org/package=hms)
=====================================================================================================================

A simple class for storing time-of-day values

The values are stored as a numeric vector that contains the number of seconds since midnight. Supports construction from time values, coercion to and from various data types, and formatting. Can be used in a data frame.

Compared to `POSIXct`, no date is stored, although the values can exceed the 24-hour boundary.

``` r
library(hms)
hms(56, 34, 12)
#> 12:34:56
as.hms(1)
#> 00:00:00
as.hms("12:34:56")
#> 12:34:56
as.hms(Sys.time())
#> 10:35:40
as.POSIXct(hms(1))
#> [1] "1970-01-01 00:00:01 UTC"

d <- data.frame(hours = 1:3)
d$hms <- hms(hours = d$hours)
d
#>   hours      hms
#> 1     1 01:00:00
#> 2     2 02:00:00
#> 3     3 03:00:00
```

Install the package from GitHub:

``` r
# install.packages("devtools")
devtools::install_github("krlmlr/hms")
```