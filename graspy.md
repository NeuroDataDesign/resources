# GraSPy

## Background 
 - See the papers listed [here](https://neurodata.io/graspy/)
 - [Connectal Coding](https://www.sciencedirect.com/science/article/pii/S0959438818301430)
 
## Current issues
These range from small to large projects
 - [Issues page](https://github.com/neurodata/graspy/issues)
 - [Good first issues](https://github.com/neurodata/graspy/issues?q=is%3Aopen+is%3Aissue+label%3A%22good+first+issue%22)
 
## Algorithms we need
These would require more significant engineering work and testing, but all would be quite useful to have a high-quality implementation of in Python. If you are interested, talk to Pedigo! Any help with these would be very much appreciated.
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

## Other project ideas 
 - Create NetworkX-compatible versions of many of our algorithms and PR them into NetworkX
 - Benchmark some of our community detection and model fitting algorithms against graph-tool 
 - Compare spectral methods to local graph clustering methods in a variety of simulation settings 
