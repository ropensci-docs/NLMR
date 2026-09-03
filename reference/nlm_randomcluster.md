# nlm_randomcluster

Simulates a random cluster nearest-neighbour neutral landscape.

## Usage

``` r
nlm_randomcluster(
  ncol,
  nrow,
  resolution = 1,
  p,
  ai = c(0.5, 0.5),
  neighbourhood = 4,
  user_seed = NULL,
  rescale = TRUE
)
```

## Arguments

- ncol:

  \[`integer(1)`\]  
  Number of columns forming the raster.

- nrow:

  \[`integer(1)`\]  
  Number of rows forming the raster.

- resolution:

  \[`numerical(1)`\]  
  Resolution of the raster.

- p:

  \[`numerical(1)`\]  
  Defines the proportion of elements randomly selected to form clusters.

- ai:

  Vector with the cluster type distribution (percentages of occupancy).
  This directly controls the number of types via the given length.

- neighbourhood:

  \[`numerical(1)`\]  
  Clusters are defined using a set of neighbourhood structures, 4
  (Rook's or von Neumann neighbourhood) (default), 8 (Queen's or Moore
  neighbourhood).

- user_seed:

  \[`numerical(1)`\]  
  Set random seed for the simulation.

- rescale:

  \[`logical(1)`\]  
  If `TRUE` (default), the values are rescaled between 0-1.

## Value

Raster with random values ranging from 0-1.

## Details

This is a direct implementation of steps A - D of the modified random
clusters algorithm by Saura & Martínez-Millán (2000), which creates
naturalistic patchy patterns.

## References

Saura, S. & Martínez-Millán, J. (2000) Landscape patterns simulation
with a modified random clusters method. *Landscape Ecology*, 15, 661 –
678.

## Examples

``` r
# simulate random clustering
random_cluster <- nlm_randomcluster(ncol = 30, nrow = 30,
                                    p = 0.4,
                                    ai = c(0.25, 0.25, 0.5))
if (FALSE) { # \dontrun{
# visualize the NLM
raster::plot(random_cluster)
} # }
```
