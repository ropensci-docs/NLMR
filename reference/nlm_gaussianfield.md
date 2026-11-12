# nlm_gaussianfield

Simulates a spatially correlated random fields (Gaussian random fields)
neutral landscape model.

## Usage

``` r
nlm_gaussianfield(
  ncol,
  nrow,
  resolution = 1,
  autocorr_range = 10,
  mag_var = 5,
  nug = 0.2,
  mean = 0.5,
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

- autocorr_range:

  \[`numerical(1)`\]  
  Maximum range (raster units) of spatial autocorrelation.

- mag_var:

  \[`numerical(1)`\]  
  Magnitude of variation over the entire landscape.

- nug:

  \[`numerical(1)`\]  
  Magnitude of variation in the scale of `autocorr_range`, smaller
  values lead to more homogeneous landscapes.

- mean:

  \[`numerical(1)`\]  
  Mean value over the field.

- user_seed:

  \[`numerical(1)`\]  
  Set random seed for the simulation

- rescale:

  \[`numeric(1)`\]  
  If `TRUE` (default), the values are rescaled between 0-1.

## Value

character(1) Temporary maintenance message.

## Details

Gaussian random fields are a collection of random numbers on a spatially
discrete set of coordinates (landscape raster). Natural sciences often
apply them with spatial autocorrelation, meaning that objects which
distant are more distinct from one another than they are to closer
objects.

## References

Kéry & Royle (2016) *Applied Hierarchical Modeling in Ecology* Chapter
20

## Examples

``` r
# simulate random gaussian field
gaussian_field <- nlm_gaussianfield(ncol = 90, nrow = 90,
                                    autocorr_range = 60,
                                    mag_var = 8,
                                    nug = 5)
#> Function nlm_fbm is currently under disabled. We are working on reimplementation of this function.

if (FALSE) { # \dontrun{
# visualize the NLM
raster::plot(gaussian_field)
} # }
```
