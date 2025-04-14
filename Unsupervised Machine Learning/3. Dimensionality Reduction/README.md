*Principal Component Analysis* is an unsupervised machine learning algorithm that helps with dimensionality reduction. When we are dealing with huge data sets that are very sparse, it is hard for classifiers to say anything meaningful because space is empty. Thus, we need to compress features into important linear combinations while preserving the variation in our data. By doing so, we can significantly reduce the dimension.

Covariance measures joint variability of 2 random variables: if 2 vairiables increase together their covariance is positive

lots of features don't affect variance in the data, take top k eigen values, we're not choosing the top 4 features, we're taking the top 4 combinations of features

if unsupervised, first use PCA to project onto top components that explain most of the variance, then run clustering algorithm
