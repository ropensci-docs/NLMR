# nlm_random

Simulates a spatially random neutral landscape model with values drawn a
uniform distribution.

## Usage

``` r
nlm_random(ncol, nrow, resolution = 1, user_seed = NULL, rescale = TRUE)
```

## Arguments

- ncol:

  \[`numerical(1)`\]  
  Number of columns forming the raster.

- nrow:

  \[`numerical(1)`\]  
  Number of rows forming the raster.

- resolution:

  \[`numerical(1)`\]  
  Resolution of the raster.

- user_seed:

  \[`numerical(1)`\]  
  Set random seed for the simulation.

- rescale:

  \[`logical(1)`\]  
  If `TRUE` (default), the values are rescaled between 0-1.

## Value

RasterLayer

## Details

The function takes the number of columns and rows as input and creates a
RasterLayer with the same extent. Each raster cell is randomly assigned
a value between 0 and 1 drawn from an uniform distribution
(`runif(1,0,1)`).

## Examples

``` r
# simulate spatially random model
random <- nlm_random(ncol = 200, nrow = 100)

if (FALSE) { # \dontrun{
# visualize the NLM
raster::plot(random)
} # }
```
