# nlm_fbm

Creates a two-dimensional fractional Brownian motion neutral landscape
model.

## Usage

``` r
nlm_fbm(
  ncol,
  nrow,
  resolution = 1,
  fract_dim = 1,
  user_seed = NULL,
  rescale = TRUE,
  ...
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

- fract_dim:

  \[`numerical(1)`\]  
  The fractal dimension of the process (0,2)

- user_seed:

  \[`numerical(1)`\]  
  Set random seed for the simulation

- rescale:

  \[`numeric(1)`\]  
  If `TRUE` (default), the values are rescaled between 0-1.

- ...:

  Unused

## Value

character(1) Temporary maintenance message.

## Details

Neutral landscapes are generated using fractional Brownian motion, an
extension of Brownian motion in which the amount of correlation between
steps is controlled by `frac_dim`. A high value of `frac_dim` produces a
relatively smooth, correlated surface while a low value produces a
rough, uncorrelated one.

## References

Travis, J.M.J. & Dytham, C. (2004). A method for simulating patterns of
habitat availability at static and dynamic range margins. *Oikos* , 104,
410–416.

Martin Schlather, Alexander Malinowski, Peter J. Menck, Marco Oesting,
Kirstin Strokorb (2015). nlm_fBm. *Journal of Statistical Software*,
63(8), 1-25. URL http://www.jstatsoft.org/v63/i08/.

## Examples

``` r
# simulate fractional brownian motion
fbm_raster <- nlm_fbm(ncol = 20, nrow = 30, fract_dim = 0.8)
#> Function nlm_fbm is currently under disabled. We are working on reimplementation of this function.

if (FALSE) { # \dontrun{

# visualize the NLM
raster::plot(fbm_raster)

} # }
```
