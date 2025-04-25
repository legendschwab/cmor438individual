**Label Propagation** is a clustering algorithm that allows us to find clusters of vertices in a graph. Our goal is to label each vertex in the graph based on similarities. 

The general intuition of label propagation is that nodes tend to adopt the community (the label) that the majority of their neighbors belong to. We start by assigning each node $v$ a unique label $L(v) = v$. Then, we follow an iterative process where at each iteration, every node updates its label: $L(v) \leftarrow \arg\max_{l}${
$u \in N(v) : L(u) = l$}.

Ties are broken randomly and we repeat this until convergence (labels no longer changing). In the following notebook, we will implement label propagation to cluster [insert something].
