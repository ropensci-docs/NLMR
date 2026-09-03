# nlm_planargradient

Simulates a planar gradient neutral landscape model.

## Usage

``` r
nlm_planargradient(
  ncol,
  nrow,
  resolution = 1,
  direction = NA,
  user_seed = NULL,
  rescale = TRUE
)
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

- direction:

  \[`numerical(1)`\]  
  Direction of the gradient in degrees, if unspecified the direction is
  randomly determined.

- user_seed:

  \[`numerical(1)`\]  
  Set random seed for the simulation.

- rescale:

  \[`logical(1)`\]  
  If `TRUE` (default), the values are rescaled between 0-1.

## Value

RasterLayer

## Details

Simulates a linear gradient sloping in a specified or random direction.

## References

Palmer, M.W. (1992) The coexistence of species in fractal landscapes.
*The American Naturalist*, 139, 375 - 397.

## See also

[`nlm_distancegradient`](https://docs.ropensci.org/NLMR/reference/nlm_distancegradient.md),
[`nlm_edgegradient`](https://docs.ropensci.org/NLMR/reference/nlm_edgegradient.md)

## Examples

``` r
# simulate planar gradient
planar_gradient <- nlm_planargradient(ncol = 200, nrow = 200)

if (FALSE) { # \dontrun{
# visualize the NLM
raster::plot(planar_gradient)
} # }
```
