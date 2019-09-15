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
    - Semester 1 DoD: Usable and presentable code (or adaptation of code) to generate data on nonlinear manifolds in high-dimensional spaces, with the ability to plot 2D manifolds in 3D. A report comparing the ability of U-SPORF to either find the intrinsic dimensionality of the data versus other approaches, and the performance of downstream tasks using/not using U-SPORF. At least 5-10 toy simulations showing the effects of large n, large dimension, "task difficulty",  linear and nonlinear settings, on tasks such as classification, hypothesis testing, and clustering (see below).  
 - How to do clustering on the output of U-SPORF?
    - [Here](https://scikit-learn.org/stable/modules/clustering.html) are some clustering method comparisons in sklearn
    - One idea is to add high-dimensional noise to the above simulations, and then see how the different clustering methods compare on these tasks (and other simulated data settings that you could come up with).
    - For some of the above, being able to do this will depend on a dimensionality reduction step, so you may have to work closely with the person doing that. Some of the clustering methods can operate directly on a dissimilarity.
    - Semester 1 DoD: Usable and presentable code (or adaptation of code) to generate data on nonlinear manifolds in high-dimensional spaces, with the ability to plot 2D manifolds in 3D. A report comparing the ability of U-SPORF to find the known clusters. At least 5-10 toy simulations showing the effects of large n, large dimension, "task difficulty", linear and nonlinear settings. 
 - How to use U-SPORF for outlier detection?
    - R's version of random forest already has some kind of outlier detection method.
    - I would do a literature search on this to get ideas
    - [Here](https://towardsdatascience.com/outlier-detection-with-isolation-forest-3d190448d45e) is one idea
    - [Sklearn](https://scikit-learn.org/stable/modules/outlier_detection.html) has some nice explanation, can also consider the novelty task which is slightly different. Also, these would be good methods to compare to! Although I think some require you to be in the supervised case.
    - Semester 1 DoD: Similar to the previous two points, but with a method extension. Usually, anomaly detection is done by estimating a GMM on the data, where outliers are considered "low probability" data. You might want to use this approach, you might not. 5-10 simulations where you impute outlier data and compare the probability of detecting it.
 - Figure out how to apply U-SPORF to more general _structured_ data? Structured simply means that the index of the data in its matrix representation matters, e.g. graphs, images, timeseries.
    - The current implementation of supervised SPORF already has functionality for structured data, that is, the random feature selection matrix that you sample from at each node is no longer truly random, but respects something about the feature's relationship to each other.
    - Example: in images, nearby pixels may be more likely to share information than far away pixels. So, rather than sampling random features (pixels), sample pixels that are nearby in space. 
    - Look into how much work it would be to extend this idea to unsupervised SPORF. I'd start with looking at the SPORF code.
    - Semester 1 DoD: MGCPy already has time series simulation and GraSPy has graph simulation. You can probability find real images to work on. For your methods extensions, compare to using U-SPORF and other methods agnostic to the structure, as well as using the structure. The performance measures are the same - instrinsic dimensionality and cluster detection probability.
 - Implement sklearn-mergable USPORF
    - I believe this would accelerate everyone's progress with USPORF in the future if we had a nice version that was truly pip installable, could go into sklearn someday but doesn't have to. 
    - This would mostly be an engineering task 
    - Would work closely with Jesse (engineering in the lab) to make a version of USPORF that is similar to the one he is writing of SPORF for sklearn
    - Semester 1 DoD: PR to sklearn.
 - What distance metrics on the trees to use to create the overall distance matrix output?
    - Currently, uses 0-1 distance. Distance of 0 if you are in the same leaf node as another datapoint, distance of 1 if you are not. Then, average this across all of the trees to get a distance matrix.
    - Could consider other "softer" metrics... for example, maybe you should also be considered close, but not quite as close, to a datapoint that is in a leaf which is close to you in the tree.
    - This project would probably involve implementing a few different metrics first, and then building on the work from the dimensionality reduction and clustering tasks to evaluate the different metrics. 
    - Semester 1 DoD: Usable and presentable code (or adaptation of code) to generate data on nonlinear manifolds in high-dimensional spaces, with the ability to plot 2D manifolds in 3D. A report comparing the ability of U-SPORF using different tree metrics and the results on clustering, classification, dimension reduction, hypothesis testing. At least 5-10 toy simulations showing the effects of large n, large dimension, "task difficulty", linear and nonlinear settings. 
## Application ideas 
 - Use U-SPORF to process genetic datasets (like single-cell RNAseq) 
 - Collaborate with other teams... in theory, U-SPORF is great for _high dimensional noise_
 - Use U-SPORF to cluster 3D neuron morphologies (haven't thought about this much) 
 - Try to replicate and extend findings from 
 [this paper](https://www.biorxiv.org/content/biorxiv/early/2019/08/15/736520.full.pdf). This 
 is more supervised SPORF but there is already code for this, I think it could be fun to try 
 and extend their analysis since it involves both genetics and connectomes. 
 
