**Principal Component Analysis** is an unsupervised machine learning algorithm that helps with dimensionality reduction. When we are dealing with huge data sets that are very sparse, it is hard for classifiers to say anything meaningful because space is empty. Thus, we need to compress features into important linear combinations while preserving the variation in our data. By doing so, we can significantly reduce the dimension.

A term important to principal component analysis is covariance. Covariance measures joint variability of 2 random variables, so if 2 variables increase together their covariance is positive. When the covariance matrix suggests that 2 variables are highly correlated with each other, it's likely that including both features is redundant to understanding our data. Thus, we may want to use principal component analysis to find the proper combination of features that best captures the data.

The foundation of PCA is the eigenvalue decomposition of the covariance matrix. Intuitively, eigenvalues capture the most essential information of a matrix. So we take top $k$ eigenvalues and corresponding eigenvectors to get the top $k$ combinations of features. This helps reduce dimensionality of data while preserving information. Then, using matrix multiplication, we can project our original data to these eigenvectors to get our new features. 

![pca](https://numxl.com/wp-content/uploads/principal-component-analysis-pca-featured.png)

*Credits: NumXL*

From then, we can rerun algorithms such as clustering and potentially yield better results. In the following notebook, we will consider 6 features of roller coasters and perform dimensionality reduction to see if that can impact clustering.
