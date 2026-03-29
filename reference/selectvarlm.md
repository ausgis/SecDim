# Selecting variables using linear regression

Function for selecting variables using linear regression

## Usage

``` r
selectvarlm(y, x, ctr.vif = 10)
```

## Arguments

- y:

  A vector of a response variable

- x:

  A data.frame of explanatory variables

- ctr.vif:

  A number of VIF threshold

## Value

A data.frame of selected variables

## Examples

``` r
data("obs")
data("sample_vars_sda")
obs$Cr_ppm <- log(obs$Cr_ppm)
krm <- rmvoutlier(obs$Cr_ppm)
#> Remove 5 outlier(s)
y <- obs$Cr_ppm[-krm]
x <- sample_vars_sda$Elevation[-krm, 1:11]
sx <- selectvarlm(y, x)
```
