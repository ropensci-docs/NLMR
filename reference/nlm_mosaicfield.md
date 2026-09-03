# nlm_mosaicfield

Simulates a mosaic random field neutral landscape model.

## Usage

``` r
nlm_mosaicfield(
  ncol,
  nrow,
  resolution = 1,
  n = 20,
  mosaic_mean = 0.5,
  mosaic_sd = 0.5,
  user_seed = NULL,
  collect = FALSE,
  infinit = FALSE,
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

- n:

  \[`numerical(1)`\]  
  Number of steps over which the mosaic random field algorithm is run

- mosaic_mean:

  \[`numerical(1)`\]  
  Mean value of the mosaic displacement distribution

- mosaic_sd:

  \[`numerical(1)`\]  
  Standard deviation of the mosaic displacement distribution

- user_seed:

  \[`numerical(1)`\]  
  Set random seed for the simulation.

- collect:

  \[`logical(1)`\]  
  return `RasterBrick` of all steps 1:`n`

- infinit:

  \[`logical(1)`\]  
  return raster of the random mosaic field algorithm with infinite steps

- rescale:

  \[`logical(1)`\]  
  If `TRUE` (default), the values are rescaled between 0-1.

## Value

RasterLayer or List with RasterLayer/s and/or RasterBrick

## References

Schwab, Dimitri, Martin Schlather, and Jürgen Potthoff. "A general class
of mosaic random fields." arXiv preprint arXiv:1709.01441 (2017).  
Baddeley, Adrian, Ege Rubak, and Rolf Turner. Spatial point patterns:
methodology and applications with R. CRC Press, 2015.

## Examples

``` r
# simulate mosaic random field
mosaic_field <- nlm_mosaicfield(ncol = 100,
                                nrow = 200,
                                n = NA,
                                infinit = TRUE,
                                collect = FALSE)
if (FALSE) { # \dontrun{
# visualize the NLM
raster::plot(mosaic_field)
} # }
```
