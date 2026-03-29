# Generating second-dimension variables for a spatial variable

Generating second-dimension variables for a spatial variable

## Usage

``` r
gsdvar(
  pointlocation,
  gridlocation,
  gridvar,
  distbuf = seq(1, 10, 1),
  quantileprob = seq(0, 1, 0.1)
)
```

## Arguments

- pointlocation:

  A matrix or data frame of point locations

- gridlocation:

  A matrix or data frame of grid locations

- gridvar:

  A matrix or data frame of grid variables

- distbuf:

  A vector of distance buffer values

- quantileprob:

  A vector of quantile probability values

## Value

A data frame containing the selected variables for the second dimension

## Examples

``` r
data(obs)
data(grids)
pointlocation <- obs[sample(nrow(obs), 20), c("Lon", "Lat")]
gridlocation <- grids[, c("Lon", "Lat")]
gridvar <- grids$Elevation
system.time({
sdavars <- gsdvar(pointlocation, gridlocation, gridvar,
                  distbuf = c(1, 2, 3), quantileprob = c(0, 0.5, 1))
})
#>    user  system elapsed 
#>   0.397   0.042   0.438 
```
