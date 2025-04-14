sparse data = hard for classifiers to say anything meaningful (space is empty), need to compress features into important combinations
PCA is unsupervised learning technique for dimensionality reduction

reduces number of features in a dataset while preserving variance

making new features that are combinations of previous features

Covariance measures joint variability of 2 random variables: if 2 vairiables increase together their covariance is positive

lots of features don't affect variance in the data, take top k eigen values, we're not choosing the top 4 features, we're taking the top 4 combinations of features

if unsupervised, first use PCA to project onto top components that explain most of the variance, then run clustering algorithm