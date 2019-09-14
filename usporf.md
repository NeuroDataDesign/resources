# Unsupervised SPORF

## Methods ideas
 - How to do dimensionality reduction on the output of U-SPORF?
    - [Figure S3 in this paper](https://www.biorxiv.org/content/biorxiv/early/2019/04/04/120378.full.pdf) has some simulated examples of dimensionality reduction.
    - [Sklearn](https://scikit-learn.org/stable/modules/manifold.html) also has a few examples here 
    - The geodesic learning paper has several simulated examples as well
    - Could add high-dimensional noise to those simulations
    - Compare U-SPORF followed by many of these methods to those methods alone. Main ones to try after U-SPORF are MDS and Spectral Embedding, I think. 
    - One metric to evaluate is preservation of nearest neighbors/local distances on the true manifold to the output embedding that you get from random forest followed by an embedding step.
    - Another is just to evaluate based on some supervised or unsupervised task (clustering, supervised learning). 
 - How to do clustering on the output of U-SPORF?
    - [Here](https://scikit-learn.org/stable/modules/clustering.html) are some clustering method comparisons in sklearn
    - One idea is to add high-dimensional noise to the above simulations, and then see how the different clustering methods compare on these tasks (and other simulated data settings that you could come up with).
    - For some of the above, being able to do this will depend on a dimensionality reduction step, so you may have to work closely with the person doing that. Some of the clustering methods can operate directly on a dissimilarity.
 - What distance metrics on the trees to use to create the overall distance matrix output?
 - How to use U-SPORF for outlier detection?
    - R's version of random forest already has some kind of outlier detection method.
    - I would do a literature search on this to get ideas, I think the general concept is just that outliers will pop out as very far from everything in the dissimilarity matrix.
 - Figure out how to apply U-SPORF to more general _structured_ data? Structured simply means that the index of the data in its matrix representation matters, e.g. graphs, images, timeseries.
    - The current implementation of supervised SPORF already has functionality for structured data, that is, the random feature selection matrix that you sample from at each node is no longer truly random, but respects something about the feature's relationship to each other.
    - Example: in images, nearby pixels may be more likely to share information than far away pixels. So, rather than sampling random features (pixels), sample pixels that are nearby in space. 
    - Look into how much work it would be to extend this idea to unsupervised SPORF. I'd start with looking at the SPORF code.
 
## Application ideas 
 - Use U-SPORF to process genetic datasets (like single-cell RNAseq) 
 - Collaborate with other teams... in theory, U-SPORF is great for _high dimensional noise_
 - Use U-SPORF to cluster 3D neuron morphologies (haven't thought about this much) 
 - Try to replicate and extend findings from 
 [this paper](https://www.biorxiv.org/content/biorxiv/early/2019/08/15/736520.full.pdf). This 
 is more supervised SPORF but there is already code for this, I think it could be fun to try 
 and extend their analysis since it involves both genetics and connectomes. 
 
