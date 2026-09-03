# nlm_curds

Simulates a random curd neutral landscape model with optional wheys.

## Usage

``` r
nlm_curds(
  curds,
  recursion_steps,
  wheyes = NULL,
  resolution = 1,
  user_seed = NULL
)
```

## Arguments

- curds:

  \[`numerical(x)`\]  
  Vector with percentage/s to fill with curds (fill with habitat (value
  == TRUE)).

- recursion_steps:

  \[`numerical(x)`\]  
  Vector of successive cutting steps for the blocks (split 1 block into
  `x` blocks).

- wheyes:

  \[`numerical(x)`\]  
  Vector with percentage/s to fill with wheys, which fill matrix in an
  additional step with habitat.

- resolution:

  \[`numerical(1)`\]  
  Resolution of the resulting raster.

- user_seed:

  \[`numerical(1)`\]  
  Set random seed for the simulation.

## Value

raster

## Details

Random curdling recursively subdivides the plane into blocks. At each
level of the recursion, a fraction of the blocks are declared as habitat
(value == TRUE) while the remaining blocks continue to be defined as
matrix (value == FALSE) and enter the next recursive cycle.

The optional argument (`wheyes`) allows wheys to be added, in which a
set proportion of cells that were declared matrix (value == FALSE)
during recursion, are now set as habitat cells (value == TRUE).

If \$\$curds\_{1} = curds\_{2} = recursion_steps\_{2} = ... = curds\_{n}
= recursion_steps\_{n}\$\$ the models resembles a binary random map.

Note that you can not set ncol and nrow with this landscape algorithm.
The amount of cells and hence dimension of the raster is given by the
vector product of the recursive steps.

## References

Keitt TH. 2000. Spectral representation of neutral landscapes.
*Landscape Ecology* 15:479-493.

Szaro, Robert C., and David W. Johnston, eds. Biodiversity in managed
landscapes: theory and practice. *Oxford University Press*, USA, 1996.

## Examples

``` r

# simulate random curdling
(random_curdling <- nlm_curds(curds = c(0.5, 0.3, 0.6),
                              recursion_steps = c(32, 6, 2)))
#> class      : RasterLayer 
#> dimensions : 384, 384, 147456  (nrow, ncol, ncell)
#> resolution : 1, 1  (x, y)
#> extent     : 0, 384, 0, 384  (xmin, xmax, ymin, ymax)
#> crs        : NA 
#> source     : memory
#> names      : layer 
#> values     : 0, 1  (min, max)
#> 

# simulate wheyed curdling
(wheyed_curdling <- nlm_curds(curds = c(0.5, 0.3, 0.6),
                              recursion_steps = c(32, 6, 2),
                              wheyes = c(0.1, 0.05, 0.2)))
#> class      : RasterLayer 
#> dimensions : 384, 384, 147456  (nrow, ncol, ncell)
#> resolution : 1, 1  (x, y)
#> extent     : 0, 384, 0, 384  (xmin, xmax, ymin, ymax)
#> crs        : NA 
#> source     : memory
#> names      : layer 
#> values     : 0, 1  (min, max)
#> 
if (FALSE) { # \dontrun{
# Visualize the NLMs
raster::plot(random_curdling)
raster::plot(wheyed_curdling)
} # }
```
