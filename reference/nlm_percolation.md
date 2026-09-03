# nlm_percolation

Generates a random percolation neutral landscape model.

## Usage

``` r
nlm_percolation(ncol, nrow, resolution = 1, prob = 0.5, user_seed = NULL)
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

- prob:

  \[`numerical(1)`\]  
  Probability value for setting a cell to 1.

- user_seed:

  \[`numerical(1)`\]  
  Set random seed for the simulation.

## Value

RasterLayer

## Details

The simulation of a random percolation map is accomplished in two steps:

- Initialization::

  Setup matrix of size (`ncol`\*`nrow`).

- Map generation::

  For each cell in the matrix a single uniformly distributed random
  number is generated and tested against a probability `prob`. If the
  random number is smaller than `prob`, the cell is set to TRUE; if it
  is higher the cell is set to FALSE.

## References

1\. Gardner RH, O'Neill R V, Turner MG, Dale VH. 1989. Quantifying
scale-dependent effects of animal movement with simple percolation
models. *Landscape Ecology* 3:217 - 227.

2\. Gustafson, E.J. & Parker, G.R. (1992) Relationships between
landcover proportion and indices of landscape spatial pattern.
*Landscape Ecology* , 7, 101 - 110.

## Examples

``` r
# simulate percolation model
percolation <- nlm_percolation(ncol = 100, nrow = 100, prob = 0.5)
if (FALSE) { # \dontrun{
# visualize the NLM
raster::plot(percolation)
} # }
```
