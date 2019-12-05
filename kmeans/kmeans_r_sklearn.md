# KMeans in R and Python

## Overview

[KMeans](https://scikit-learn.org/stable/modules/clustering.html#k-means) performs [clustering](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html) by attempting to arrange samples among groups of equal variance.  
The main differences between implementation in R and sklearn are:

* R has more options for algorithms to use
* sklearn provides you an option (the default, *kmeans++*) to speed up convergence 

If using an example dataset:

| V1 | V2 |
| --- | --- |
| 1   | 2   |
| 2   | 3   |
| 2   | 0   | 
| 8   | 2   | 
| 10   | 4   | 
| 10   | 5   | 
| 9   | 3   | 

In [R](https://www.r-bloggers.com/k-means-clustering-in-r/), you'd run these commands to perform kmeans clustering, and create a basic figure:

        # create empty dataframe x
        x <- setNames(data.frame(matrix(ncol=2, nrow=7)), c("v1", "v2"))
        # assign values to columns V1 and V2
        x[, "V1"] <- c(1,2,2,8,10,10,9)
        x[, "V2"] <- c(2,3,0,2,4,5,3)
        kmeans_x <- kmeans(x[, 1:2], 2, algorithm="Lloyd")
        ggplot(x, aes(v1, v2, color = kmeans_x$cluster)) + geom_point()
        
In sklearn on Python, you'd run these commands to perform kmeans clustering, and create a basic figure:

        from sklearn.cluster import KMeans
        import numpy as np
        X = np.array([[1,2], [2,3], [2,0], [8,2], [10,4], [10,5], [9,3]])
        kmeans = KMeans(n_clusters=2, random_state=0, algorithm="full").fit(X)
        
        # print figure
        import matplotlib.pyplot as plt
        import numpy
        
        plt.scatter(X[:,0], X[:,1])
        


Note that sklean in Python **only** can use Ekand and Lloyd algorithms. 


## References

1. [KMeans reference doc on sklean](https://scikit-learn.org/stable/modules/clustering.html#k-means)

2. [KMeans usage doc on sklearn](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html)

3. [Original Paper for Elkan's Algorithm](https://www.aaai.org/Papers/ICML/2003/ICML03-022.pdf)

4. [Blog on KMeans Clustering using Lloyd's Algorithm](https://datasciencelab.wordpress.com/tag/lloyds-algorithm/)

5. [A Somewhat Verbose description of the algorithms available in R for KMeans](https://stackoverflow.com/a/20450717)
