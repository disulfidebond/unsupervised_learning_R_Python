# DBSCAN in R and sklearn Python

## Overview

[DBSCAN](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.DBSCAN.html#sklearn.cluster.DBSCAN), or Density-Based Spatial Clustering of Applications with Noise, has well-documented [implementations in R](https://cran.r-project.org/web/packages/dbscan/dbscan.pdf) and [sklearn](https://scikit-learn.org/stable/auto_examples/cluster/plot_dbscan.html).

In lieu of providing exact examples of both here, commented code is provided for the above examples.


In R, parameters for eps must be supplied when the function call to dbscan() is made.  

        dbscan(iris, eps = .5, minPts = 5)

If desired, you can calculate the fixed radius NN frNN(), and then provide this to dbscan()

        data(iris)
        iris <- as.matrix(iris[,1:4])
        fr <- frNN(iris, eps = .5)
        dbscan(fr, minPts = 5)
        
In sklearn, the usual implementation is:

        db = DBSCAN(eps=0.3, min_samples=10).fit(X)
        
You can also modify/compute the number of clusters in labels.

## References

[sklearn DBSCAN documentation](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.DBSCAN.html#sklearn.cluster.DBSCAN)

[sklearn DBSCAN example](https://scikit-learn.org/stable/auto_examples/cluster/plot_dbscan.html)

[R documentation and example for DBSCAN](https://cran.r-project.org/web/packages/dbscan/dbscan.pdf)
