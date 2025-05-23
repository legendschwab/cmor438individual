Up until now data has been defined in terms of feature vectors in $R^n$. However, many data sets are better described by a relational structure. **Graph Theory** refers to using graph-like structures to better understand the relationship between data points. Examples include social networks and shortest-path problems. 

Formally, a graph is defined as a tuple of 2 sets, vertices $V$ and edges $E$ that connect vertices. Edges connect the vertices either with direction in directed graphs or in both directions in undirected graphs. Below is an example of the Peterson graph, which is an undirected graph. It has 10 vertices and 15 edges.

![graph](https://ds055uzetaobb.cloudfront.net/brioche/uploads/9NiHeGq6rf-2000px-petersen_graph_3-coloringsvg.png?width=1200)

*Credits: Cloud Front*

There are many problems we can explore with graph theory. In this folder, we will explore label propagation and maximum clique.

**Label Propagation** is a clustering algorithm that allows us to find clusters of vertices in a graph. Our goal is to label each vertex in the graph a class based on similarities. 

The general intuition of label propagation is that nodes tend to adopt the community (the label) that the majority of their neighbors belong to. We start by assigning each node $v$ a unique label $L(v) = v$. Then, we follow an iterative process where at each iteration, every node updates its label: $L(v) \leftarrow \arg\max_{l}${
$u \in N(v) : L(u) = l$} where $N(v)$ refers to the neighbors of vertex $v$.

Ties are broken randomly and we repeat this until convergence (labels no longer changing). In the following notebook, we will implement label propagation to cluster Facebook users based on who they follow. 

**Maximum Clique** refers to the problem of finding the largest subset of vertices where all vertices are adjacent to each other. In the context of a social networks, this would be the finding the largest group of people who are all friends with each other. 

We will formulate this as a integer linear program and solve it on the Peterson graph (pictured above) as an example and then the Facebook dataset.

