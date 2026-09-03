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
  Edge coordinates of the origin (raster::extent with xmin, xmax, ymin,
  ymax) of the distance measurement.

- rescale:

  \[`logical(1)`\]  
  If `TRUE` (default), the values are rescaled between 0-1. Otherwise,
  the distance in raster units is calculated.

## Value

RasterLayer

## Details

The function takes the number of columns and rows as input and creates a
`RasterLayer` with the same extent. `Origin` is a numeric vector of
xmin, xmax, ymin, ymax for a rectangle inside the raster from which the
distance is measured.

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
raster::plot(distance_gradient)
} # }
```
