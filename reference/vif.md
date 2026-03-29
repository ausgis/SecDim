# Fast calculation of the variance inflation factor (VIF)

Function for fast calculation of the variance inflation factor (VIF)

## Usage

``` r
vif(x)
```

## Arguments

- x:

  A data.frame of explanatory variables

## Value

Variance inflation factor (VIF) values of variables

## Examples

``` r
data("sample_vars_sda")
x <- sample_vars_sda$Elevation[, sample(55, 10)]
vif(x)
#>  [1] 163.142198 396.453187 154.933169 164.531259  46.833438  40.144002
#>  [7] 224.756892  85.034859 186.270639   3.189894
```
