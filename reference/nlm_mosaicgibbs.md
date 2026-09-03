# nlm_mosaicgibbs

Simulate a neutral landscape model using the Gibbs algorithm introduced
in Gaucherel (2008).

## Usage

``` r
nlm_mosaicgibbs(
  ncol,
  nrow,
  resolution = 1,
  germs,
  R,
  patch_classes,
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

- R:

  \[`numerical(1)`\]  
  Interaction radius (non-negative integer) for the fitting of the
  spatial point pattern process - the min. distance between germs in map
  units.

- patch_classes:

  \[`numerical(1)`\]  
  Number of classes for germs.

- user_seed:

  \[`numerical(1)`\]  
  Set random seed for the simulation.

- rescale:

  \[`logical(1)`\]  
  If `TRUE` (default), the values are rescaled between 0-1.

## Value

RasterLayer

## Details

`nlm_mosaicgibbs` offers the second option of simulating a neutral
landscape model described in Gaucherel (2008). The method works in
principal like the tessellation method (`nlm_mosaictess`), but instead
of a random point pattern the algorithm fits a simulated realization of
the Strauss process. The Strauss process starts with a given number of
points and uses a minimization approach to fit a point pattern with a
given interaction parameter (0 - hardcore process; 1 - Poisson process)
and interaction radius (distance of points/germs being apart).

## References

Gaucherel, C. (2008) Neutral models for polygonal landscapes with linear
networks. *Ecological Modelling*, 219, 39 - 48.

## Examples

``` r
# simulate polygonal landscapes
mosaicgibbs <- nlm_mosaicgibbs(ncol = 40,
                              nrow = 30,
                              germs = 20,
                              R = 0.02,
                              patch_classes = 12)

if (FALSE) { # \dontrun{
# visualize the NLM
raster::plot(mosaicgibbs)
} # }
```
