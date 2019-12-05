# Spectral Clustering in R and sklearn Python

## Overview

In R, there are a few options. There is a [package](https://www.rdocumentation.org/packages/anocva/versions/0.1.1/topics/spectralClustering) that will perform this task, and the required input is a NxN similarity matrix.

Nura Kawa also created a custom implementation, which is [included in this repo](https://github.com/disulfidebond/unsupervised_learning_R_Python/blob/master/spectral_clustering/spectral-clustering.R).

Sklearn has no formalized implementation for spectral clustering, but [towardsdatascience](https://towardsdatascience.com/spectral-clustering-aba2640c0d5b) has a writeup and explanation.

Note that both the towardsdatascience writeup and the Nura Kawa implementation rely on a nearest-neighbors approach.


## References

[Documentation and example of Spectral Clustering in R](https://www.rdocumentation.org/packages/anocva/versions/0.1.1/topics/spectralClustering)

[Writeup and custom implementation of Spectral Clustering in R by Nura Kawa](https://rpubs.com/nurakawa/spectral-clustering)

[Sklearn implementaion of Spectral Clustering](https://towardsdatascience.com/spectral-clustering-aba2640c0d5b)
