**K-Nearest Neighbors** is a **non-parametric** learning algorithm that labels data points with a category or predicts a value by inferring information from the k "closest" training data points.

We can do both classification and regression with k-nearest neighbors. For
classification, we find the k-closest data points based on feature values to our new data point. Out of the k, we see which category label is most common and assign it to this new data point. If instead, we take the average label value from the neighbors, we get a regression problem.

How do you determine an appropriate value of k? Often times, an odd k value is used so that there will never be a tie between the top 2 categories.

What does "closest" mean? This idea of "closest" usually refers to L2 **Euclidean** distance but other forms of distance can be used. We will explore both Euclidean distance and Manhattan distance when applying this algorithm. Manhattan distance may be good when dealing with the curse of dimensionality. The curse of dimensionality refers to challenges of detecting patterns and analyzing relationships in high-dimensional data. When dealing with high-dimensional data, data may be more sparse so Euclidean distance can overexaggerate the distance between points. Thus, Manhattan distance may be more appropriate for kNN. 

In this following notebook, we will use the speed and height of a roller coaster to predict whether a roller coaster has inversions or not. We will first use L2 Euclidean distance but we will also try Manhattan distance and compare our results. 


-- Notes from Class:
-- Curse of dimensionality, high dimensional space is essentially empty, each feature vector is mapped to the majority label of the training instances, have to store all of those instances, memory issues
-- Test set should not be used to pick k. Instead, we should create a separate validation set. Test set should never influence any parameters of the model.
