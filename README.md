# Identifying local connectivity structure

Tutorial and demonstration using spectral bipartivity to identify the local connectivity structure of a simple network. Methodological repository accompanying:

## Scale of spectral bipartivity

Spectral bipartivity can be re-purposed to identify local connectivity structure in networks using a comparison to random expectation. Specifically, we use this measure to quantify the relative over-representation of squares vs. triangles in the local connectivity structure of a network. Random networks give us the baseline for values of spectral bipartivity. Social networks have lots of triangles and so are _less_ bipartite than random expectation. Functional networks have lots of squares and so are _more_ bipartite than random expectation. Two-mode networks are bipartite and would have a value of 1. Below is a toy example of how social, random, functional, and two-mode networks with the same number of nodes and edges are arranged according to their value of spectral bipartivity. 

![A toy example of how social, random, functional, and two-mode networks with seven nodes and eleven edges show increasing spectral bipartivity.](scale.jpg?raw=true)

Developing new measures that would allow for comparison across networks substantially different in size is a promising area for future work in network science.

### Degree-preserving randomization

In less contrived scenarios, the comparison to random expectation is key to identifying local connectivity structure because spectral bipartivity is defined as a ratio and the denominator of this ratio is strongly affected by the number of edges in the network. Degree-preserving randomization serves as a way to “center” the scale such that remaining differences reflect local connectivity structure. We use a version of this called random pairwise rewiring, wherein pairs of edges are selected and an end point of each edge are swapped (see: Hanhijarvi et al., 2009, Figure 1(a)). Our implementation also guarantees that the randomized network remains simple by following through with a rewire only so long as it will not introduce self-loops or multi-edges; randomization continues until 10·m pairs of links have been rewired, where m is the number of simple edges.

### Statistical testing

The KS test is nice, but plots are usually nicest. 
