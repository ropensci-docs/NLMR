# nlm_mpd

Simulates a midpoint displacement neutral landscape model.

## Usage

``` r
nlm_mpd(
  ncol,
  nrow,
  resolution = 1,
  roughness = 0.5,
  rand_dev = 1,
  user_seed = NULL,
  torus = FALSE,
  rescale = TRUE,
  verbose = TRUE
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

- roughness:

  \[`numerical(1)`\]  
  Controls the level of spatial autocorrelation (!= Hurst exponent)

- rand_dev:

  \[`numerical(1)`\]  
  Initial standard deviation for the displacement step (default == 1),
  sets the scale of the overall variance in the resulting landscape.

- user_seed:

  \[`numerical(1)`\]  
  Set random seed for the simulation.

- torus:

  \[`logical(1)`\]  
  Logical value indicating wether the algorithm should be simulated on a
  torus (default FALSE)

- rescale:

  \[`logical(1)`\]  
  If `TRUE` (default), the values are rescaled between 0-1.

- verbose:

  \[`logical(1)`\]  
  If `TRUE` (default), the user gets a warning that the functions
  changes the dimensions to an appropriate one for the algorithm.

## Value

RasterLayer

## Details

The algorithm is a direct implementation of the midpoint displacement
algorithm. It performs the following steps:

- Initialization::

  Determine the smallest fit of `max(ncol, nrow)` in *n^2 + 1* and
  assign value to n. Setup matrix of size (n^2 + 1)\*(n^2 + 1).
  Afterwards, assign a random value to the four corners of the matrix.

- Square Step::

  For each square in the matrix, assign the average of the four corner
  points plus a random value to the midpoint of that square.

- Diamond Step::

  For each diamond in the matrix, assign the average of the four corner
  points plus a random value to the midpoint of that diamond.

At each iteration the roughness, an approximation to common Hurst
exponent, is reduced.

## References

<https://en.wikipedia.org/wiki/Diamond-square_algorithm>

## Examples

``` r

# simulate midpoint displacement
midpoint_displacememt <- nlm_mpd(ncol = 100,
                                 nrow = 100,
                                 roughness = 0.3)
#> Warning: nlm_mpd changes the dimensions of the RasterLayer if even ncols/nrows are choosen.
if (FALSE) { # \dontrun{
# visualize the NLM
raster::plot(midpoint_displacememt)
} # }
```
