# nlm_neigh

Create a neutral landscape model with categories and clustering based on
neighborhood characteristics.

## Usage

``` r
nlm_neigh(
  ncol,
  nrow,
  resolution = 1,
  p_neigh,
  p_empty,
  categories = 3,
  neighbourhood = 4,
  proportions = NA,
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

- p_neigh:

  \[`numerical(1)`\]  
  Probability of a cell will turning into a value if there is any
  neighbor with the same or a higher value.

- p_empty:

  \[`numerical(1)`\]  
  Probability a cell receives a value if all neighbors have no value
  (i.e. zero).

- categories:

  \[`numerical(1)`\]  
  Number of categories used.

- neighbourhood:

  \[`numerical(1)`\]  
  The neighbourhood used to determined adjacent cells: \`8 ("Moore")\`
  takes the eight surrounding cells, while \`4 ("Von-Neumann")\` takes
  the four adjacent cells (i.e. left, right, upper and lower cells).

- proportions:

  \[`vector(1)`\]  
  The algorithm uses uniform proportions for each category by default. A
  vector with as many proportions as categories and that sums up to 1
  can be used for other distributions.

- user_seed:

  \[`numerical(1)`\]  
  Set random seed for the simulation.

- rescale:

  \[`logical(1)`\]  
  If `TRUE` (default), the values are rescaled between 0-1.

## Value

RasterLayer

## Details

The algorithm draws a random cell and turns it into a given category
based on the probabilities `p_neigh` and `p_empty`, respectively. The
decision is based on the probability `p_neigh`, if there is any cell in
the Moore- (8 cells) or Von-Neumann-neighborhood (4 cells), otherwise it
is based on `p_empty`. To create clustered neutral landscape models,
`p_empty` should be (significantly) smaller than `p_neigh`. By default,
the Von-Neumann-neighborhood is used to check adjacent cells. The
algorithm starts with the highest categorical value. If the proportion
of cells with this value is reached, the categorical value is reduced
by 1. By default, a uniform distribution of the categories is applied.

## References

Scherer, Cédric, et al. "Merging trait-based and individual-based
modelling: An animal functional type approach to explore the responses
of birds to climatic and land use changes in semi-arid African
savannas." *Ecological Modelling* 326 (2016): 75-89.

## Examples

``` r
# simulate neighborhood model
neigh_raster <- nlm_neigh(ncol = 50, nrow = 50, p_neigh = 0.7, p_empty = 0.1,
                    categories = 5, neighbourhood = 4)

if (FALSE) { # \dontrun{
# visualize the NLM
raster::plot(neigh_raster)
} # }
```
