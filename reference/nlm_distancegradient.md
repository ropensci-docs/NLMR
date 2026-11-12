# nlm_distancegradient

Simulates a distance-gradient neutral landscape model.

## Usage

``` r
nlm_distancegradient(ncol, nrow, resolution = 1, origin, rescale = TRUE)
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

- origin:

  \[`numerical(4)`\]  
  Rectangular origin as 1-based cell indices:
  `c(first_column, last_column, first_row, last_row)`.

- rescale:

  \[`logical(1)`\]  
  If `TRUE` (default), the values are rescaled between 0-1. Otherwise,
  the distance in raster units is calculated.

## Value

SpatRaster

## Details

`origin` uses inclusive, 1-based cell indices; rows are numbered from
top to bottom. Cells inside the selected rectangle have distance zero.
With `rescale = FALSE`, distances are multiplied by `resolution`.

## See also

[`nlm_edgegradient`](https://docs.ropensci.org/NLMR/reference/nlm_edgegradient.md),
[`nlm_planargradient`](https://docs.ropensci.org/NLMR/reference/nlm_planargradient.md)

## Examples

``` r

# simulate a distance gradient
distance_gradient <- nlm_distancegradient(ncol = 100, nrow = 100,
                                           origin = c(20, 30, 10, 15))
if (FALSE) { # \dontrun{
# visualize the NLM
terra::plot(distance_gradient)
} # }
```
