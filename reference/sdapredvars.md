# Preparing explanatory variables data for SDA-based prediction

Function for preparing explanatory variables data for SDA-based
prediction or the testing data for cross validation

## Usage

``` r
sdapredvars(xlist)
```

## Arguments

- xlist:

  A list of the SDA explanatory variables

## Value

A data.frame of variables for prediction or validation

## Examples

``` r
data("obs")
data("sample_vars_sda")
obs$Cr_ppm <- log(obs$Cr_ppm)
krm <- rmvoutlier(obs$Cr_ppm)
#> Remove 5 outlier(s)
y <- obs$Cr_ppm[-krm]
x <- list(sample_vars_sda[[1]][-krm, 1:11])
kvalidate <- sample(length(y), 0.3*length(y), replace = FALSE)
yv <- y[kvalidate]
xv <- lapply(x, function(x) x[kvalidate,])
sdaxv <- sdapredvars(xv)
sdayxv <- cbind(yv, sdaxv)
```
