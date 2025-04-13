K-Means Clustering is the most common unsupervised machine learning algorithm. 

![kmeans](https://miro.medium.com/v2/resize:fit:1080/0*irrlUXS1tmYanvT0.png)

*Graph for K-Means Clustering (Credits: Medium)*

This algorithm begins by randomly assigning k data points as our centroid values to represent the initial clusters. Then, all the training data points are classified into one of the k clusters based on closest distance. Similar to kNN, we can use various forms of distance but the most common is Euclidean distance. Afterwards, the centroid values are updated by averaging the values of all the points in the cluster. This iterative process is repeated until the amount that the centroids change is within a small tolerance. This means the algorithm has converged. 

How do you determine the value of $$k$$? 

The elbow method is a common method to see which $$k$$ value is most optimal. We create a plot of $$k$$ against the Within-Cluster Sum of Squares (WCSS). This is the sum of the squared distances between each point and its cluster centroid, illustrating how well data points are clustered around their respective centroids. Obviously, if we increase $$k$$ to be the number of unique data points, every data point would be their own centroid and the WCSS would be 0. However, that would be meaningless and defeat the purpose of clustering. Thus, we want plot WCSS against multiple $$k$$ values to find the "elbow point", which is where the rate at which WCSS improves decreases. This $$k$$ value balances accuracy and efficiency.

![ElbowMethod](https://towardsdatascience.com/wp-content/uploads/2020/10/1tZSzGfCRX2NtaSGGaMcejw.png)

*Elbow Method for K-Means Clustering (Credits: Towards Data Science)*

However, I also want to explore another method for evaluating the success of our clustering algorithm.

There should be 2 goals with clustering algorithms:
1. Intragroup Similarity: Elements within each cluster should be as similar to each other as possible
2. Intergroup Differences: Elements from different clusters should be as different from each other as possible

Thus, I'll define a new metric called clustering distinctness (CD) that is computed as: 

Let:

- \( \mathbf{x}_i \) be a data point.
- \( C_j \) be the centroid of the cluster that \( \mathbf{x}_i \) belongs to.
- \( \mathcal{C} \) be the set of all centroids.
- \( d(\mathbf{x}_i, C) \) be the distance between point \( \mathbf{x}_i \) and centroid \( C \).
- \( \bar{d}_{\text{other}}(\mathbf{x}_i) \) be the average distance from \( \mathbf{x}_i \) to all centroids **excluding** \( C_j \).

Then the **Cluster Distinctiveness** for the entire dataset is:

\[
\text{Distinctiveness} = \sum_{i=1}^{n} \left( \frac{1}{k - 1} \sum_{\substack{C \in \mathcal{C} \\ C \ne C_j}} d(\mathbf{x}_i, C) - d(\mathbf{x}_i, C_j) \right)
\]

In the following notebook, we will apply K-Means Clustering to the coordinate location of roller coasters in the United States.



1. pick k centroids
2. assign each point to the nearest cenroid; that is its label (euclidean distance only does balls of data, manhattan distance does boxes)
3. For each group assign a new centroid to the average

how to determine k?
take a distance measure from each point to each centroid and sum up for each point and divide by the number of points in that cluster, sum up these averages across 

Come up with and try different measures for K.
- standard deviation, variance

Maybe a metric: each point you take the sum of distances to the centroids of other clusters and then subtract out the distance to the centroid of the cluster the point belongs in, divide this sum by k and then average across all points

want points to be far from other cluster centroids but close to their own cluster centroid