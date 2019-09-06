# GraSPy

## Background 
 - See the papers listed [here](https://neurodata.io/graspy/)
 - [Connectal Coding](https://www.sciencedirect.com/science/article/pii/S0959438818301430)
 
## Current issues
 - [Issues page](https://github.com/neurodata/graspy/issues)
 - [Good first issues](https://github.com/neurodata/graspy/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22)
 
## Algorithms we need
 - Hierarchical SBM
    - This model describes multilevel community structure in networks, as well as identifies repeated patterns in the network
    - [Paper](https://arxiv.org/pdf/1503.02115.pdf)
    - [Code](https://github.com/neurodata/graspy/blob/18c34bc224b15b93d1d6b809515ac3f8e5733aa5/graspy/models/sbm.py#L497) for my rough implementation
    - [R implementation](http://www.cis.jhu.edu/~parky/HSBM/)
 - Graph independence testing 
    - This algorithm tests whether two graphs are statistically independent of one another 
    - [Paper](https://arxiv.org/abs/1906.03661)
    - [Code](https://github.com/junhaobearxiong/graph_independence_test) for a rough Python implementation
 - Matched graph filters
    - This algorithm finds a template graph (the matched filter) in a much larger graph efficiently
    - [Paper](https://arxiv.org/pdf/1803.02423.pdf)
    - [R implementation](https://github.com/dpmcsuss/iGraphMatch/tree/dev) (same as the above, this algorithm specifically is buried somewhere in there)
 - Seeded graph matching
    - [R implementation](https://github.com/dpmcsuss/iGraphMatch/tree/dev)

