# nlm_randomrectangularcluster

Simulates a random rectangular clusters neutral landscape model with
values ranging 0-1.

## Usage

``` r
nlm_randomrectangularcluster(
  ncol,
  nrow,
  resolution = 1,
  minl,
  maxl,
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

- minl:

  \[`numerical(1)`\]  
  The minimum possible width and height for each random rectangular
  cluster.

- maxl:

  \[`numerical(1)`\]  
  The maximum possible width and height for each random rectangular
  cluster.

- user_seed:

  \[`numerical(1)`\]  
  Set random seed for the simulation.

- rescale:

  \[`logical(1)`\]  
  If `TRUE` (default), the values are rescaled between 0-1.

## Value

RasterLayer

## Details

The random rectangular cluster algorithm starts to fill a raster
randomly with rectangles defined by `minl` and `maxl` until the surface
of the landscape is completely covered. This is one type of realisation
of a "falling/dead leaves" algorithm, for more details see Galerne &
Gousseau (2012).

## References

Gustafson, E.J. & Parker, G.R. (1992). Relationships between landcover
proportion and indices of landscape spatial pattern. *Landscape
ecology*, 7, 101–110. Galerne B. & Gousseau Y. (2012). The Transparent
Dead Leaves Model. Advances in Applied Probability, *Applied Probability
Trust*, 44, 1–20.

## Examples

``` r
# simulate random rectangular cluster
randomrectangular_cluster <- nlm_randomrectangularcluster(ncol = 50,
                                                          nrow = 30,
                                                          minl = 5,
                                                          maxl = 10)
if (FALSE) { # \dontrun{
# visualize the NLM
raster::plot(randomrectangular_cluster)
} # }
```
