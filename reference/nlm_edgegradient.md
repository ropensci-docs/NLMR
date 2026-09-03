# nlm_edgegradient

Simulates an edge-gradient neutral landscape model.

## Usage

``` r
nlm_edgegradient(
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
  Direction of the gradient (between 0 and 360 degrees), if unspecified
  the direction is randomly determined.

- user_seed:

  \[`numerical(1)`\]  
  Set random seed for the simulation.

- rescale:

  \[`logical(1)`\]  
  If `TRUE` (default), the values are rescaled between 0-1.

## Value

RasterLayer

## Details

Simulates a linear gradient orientated on a specified or random
direction that has a central peak running perpendicular to the gradient
direction.

## References

Travis, J.M.J. & Dytham, C. (2004) A method for simulating patterns of
habitat availability at static and dynamic range margins. *Oikos*, 104,
410–416.

## See also

[`nlm_distancegradient`](https://docs.ropensci.org/NLMR/reference/nlm_distancegradient.md),
[`nlm_planargradient`](https://docs.ropensci.org/NLMR/reference/nlm_planargradient.md)

## Examples

``` r

# simulate random curdling
edge_gradient <- nlm_edgegradient(ncol = 100, nrow = 100, direction = 80)

if (FALSE) { # \dontrun{
# visualize the NLM
raster::plot(edge_gradient)
} # }
```
