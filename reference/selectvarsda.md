# Selecting variables for the SDA model

Function for selecting variables for the second dimension of spatial
association (SDA) model

## Usage

``` r
selectvarsda(y, xlist)
```

## Arguments

- y:

  A vector of a response variable

- xlist:

  A list of the SDA explanatory variables

## Value

A list of the selected the second dimension variables

## Examples

``` r
data("obs")
data("sample_vars_sda")
obs$Cr_ppm <- log(obs$Cr_ppm)
krm <- rmvoutlier(obs$Cr_ppm)
#> Remove 5 outlier(s)
y <- obs$Cr_ppm[-krm]
x <- list(sample_vars_sda[[1]][-krm, 1:11])
system.time({ # ~0.01s
  sx <- selectvarsda(y, xlist = x)
})
#>    user  system elapsed 
#>   0.015   0.000   0.016 
```
