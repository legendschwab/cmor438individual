Up until now data has been defined in terms of feature vectors in $R^n$. However, many data sets are better described by a relational structure. **Graph Theory** refers to using graph-like structures to better understand the relationship between data points. Examples include social networks and shortest-path problems. 

Formally, a graph is defined as a tuple of 2 sets, vertices $V$ and edges $E$ that connect vertices. Edges connect the vertices either with direction in directed graphs or in both directions in undirected graphs.

![graph](https://ds055uzetaobb.cloudfront.net/brioche/uploads/9NiHeGq6rf-2000px-petersen_graph_3-coloringsvg.png?width=1200)

*Credits: Cloud Front*

There are many problems we can explore with graph theory. In this folder, we will explore label propagation and maximum clique.

**Label Propagation** is a clustering algorithm that allows us to find clusters of vertices in a graph. Our goal is to label each vertex in the graph a class based on similarities. 

The general intuition of label propagation is that nodes tend to adopt the community (the label) that the majority of their neighbors belong to. We start by assigning each node $v$ a unique label $L(v) = v$. Then, we follow an iterative process where at each iteration, every node updates its label: $L(v) \leftarrow \arg\max_{l}${
$u \in N(v) : L(u) = l$}.

Ties are broken randomly and we repeat this until convergence (labels no longer changing). In the following notebook, we will implement label propagation to cluster Facebook users based on who they follow. The data set was taken from [Kaggle](https://www.kaggle.com/datasets/wolfram77/graphs-social?resource=download).

This data set is a directed graph meaning that person $A$ can follow person $B$ but not vice versa. For the label propagation algorithm, we will consider neighbors as only out-going neighbors. This makes sense for a social media network since your feed shows the content of the people you follow, so you're likely to join the category of the people you are following.

**Maximum Clique** refers to the problem of finding the largest subset of vertices where all vertices are adjacent to each other. In the context of a social networks, this would be the finding the largest group of people who are all friends with each other. 

We will formulate this as a integer linear program and solve it on the Peterson graph (pictured above).

