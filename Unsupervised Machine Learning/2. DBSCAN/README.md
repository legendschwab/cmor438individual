DBSCAN is a density-based clustering algorithm that groups together points that are closely packed and marks points in low-density regions as outliers (noise). 

Unlike k-means, DBSCAN does not require the number of clusters to be specified in advance. The algorithm determines that value of $k$.The intuition with DBSCAN is to look at densely packed points and group them together at clusters. Note that while k-means clustering is limited to ball-like shapes,  DBSCAN is flexible enough to extend to other cluster shapes as well.

![DBSCAN](https://substackcdn.com/image/fetch/f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F071b3ee2-5df1-4900-8539-a55d2ee18d8e_3221x2180.png)

*Credits: Daily Dose of Data Science*

The general algorithm begins with defining core points in our data set. Core points have at least $k$ points within an $\epsilon$ distance surrounding it. Both $k$ and $\epsilon$ are user-defined parameters. 

Afterwards, randomly choose a core point and assign it to cluster 1. Add all core points close to this initial core point to cluster 1. Then, add all core points that are close to any other core point in cluster 1. Keep adding core points iteratively until there are none left. Afterwards, add all non-core points that are close to cluster. Now, you have finished creating the first cluster.

Repeat this previous step by selecting a new core point that has not already been assigned to a cluster. Keep going until all core points have been assigned to a cluster. At the end, all remaining points that are left over are considered noise.

In the following notebook, we will repeat what we did in k-means clustering to help cluster locations of roller coasters in the United States to help plan our next trip.
