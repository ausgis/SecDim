# Removing outliers.

Function for removing outliers.

## Usage

``` r
rmvoutlier(x, coef = 2.5)
```

## Arguments

- x:

  A vector of a variable

- coef:

  A number of the times of standard deviation. The default value is 2.5.

## Value

Location of outliers in the vector

## Examples

``` r
data("obs")
obs$Cr_ppm <- log(obs$Cr_ppm)
krm <- rmvoutlier(obs$Cr_ppm)
#> Remove 5 outlier(s)
krm
#> [1]  14  20 185 187 523
```
