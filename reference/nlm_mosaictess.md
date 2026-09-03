# nlm_mosaictess

Simulate a neutral landscape model using the tesselation approach
introduced in Gaucherel (2008).

## Usage

``` r
nlm_mosaictess(
  ncol,
  nrow,
  resolution = 1,
  germs,
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

- germs:

  \[`numerical(1)`\]  
  Intensity parameter (non-negative integer).

- user_seed:

  \[`numerical(1)`\]  
  Set random seed for the simulation.

- rescale:

  \[`logical(1)`\]  
  If `TRUE` (default), the values are rescaled between 0-1.

## Value

RasterLayer

## Details

`nlm_mosaictess` offers the first option of simulating a neutral
landscape model described in Gaucherel (2008). It generates a random
point pattern (germs) with an independent distribution and uses the
Voronoi tessellation to simulate mosaic landscapes.

## References

Gaucherel, C. (2008) Neutral models for polygonal landscapes with linear
networks. *Ecological Modelling*, 219, 39 - 48.

## Examples

``` r
# simulate polygonal landscapes
mosaictess <- nlm_mosaictess(ncol = 30, nrow = 60, germs = 200)

if (FALSE) { # \dontrun{
# visualize the NLM
raster::plot(mosaictess)
} # }
```
