# Unsupervised randomer forest

## Methods ideas
 - How to do dimensionality reduction on the output of U-SPORF?
 - How to do clustering on the output of U-SPORF?
 - What distance metrics on the trees to use to create the overall distance matrix output?
 - How to use U-SPORF for outlier detection? 
 - How to use U-SPORF on graphs (hard, I care about this but it would be very open ended)?
 - More generally, figure out how to apply U-SPORF to more general _structured_ data? Structured 
 simply means that the index of the data in its matrix representation matters, e.g. graphs, images, 
 timeseries.
 - Plug in U-SPORF as a kernel in [this](https://github.com/KrishnaswamyLab/PHATE) manifold learning
 algorithm.
 
## Application ideas 
 - Use U-SPORF to process genetic datasets (like single-cell RNAseq) 
 - Collaborate with other teams... in theory, U-SPORF is great for _high dimensional noise_
 - Use U-SPORF to cluster 3D neuron morphologies (haven't thought about this much) 
 - Try to replicate and extend findings from 
 [this paper](https://www.biorxiv.org/content/biorxiv/early/2019/08/15/736520.full.pdf). This 
 is more supervised SPORF but there is already code for this, I think it could be fun to try 
 and extend their analysis since it involves both genetics and connectomes. 
 
