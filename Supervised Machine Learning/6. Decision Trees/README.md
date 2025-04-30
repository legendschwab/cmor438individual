**Decision trees** are machine learning algorithms that can perform both classification and regression. They have a tree-like structure with parent and child nodes. At each layer of a decision tree, we split our data into 2 sets.

## Classification

For classification,  we create a tree that has either root nodes or leaf nodes. At root nodes, we separate our data into 2 groups based on a feature condition. 

![classificationexample](https://images.datacamp.com/image/upload/v1677504957/decision_tree_for_heart_attack_prevention_2140bd762d.png)

*Credits: Data Camp*

For example, for the above heart attack risk classification example, age is used to split the data into 3 child nodes. Then, we look at the child nodes. If all the data in a node is in the same category, that node is a leaf node and no more splitting is required. This would correspond to the Age 18-30 node. Otherwise, we have a root node and need to separate our data once again via another condition.

How do we decide what conditions go on our leaf nodes? The model chooses conditions that create splits that maximize the information gain. We measure the amount of information in a state via entropy. 

The entropy $$H(X)$$ of a split $$X$$ is given by:

$$
H(X) = -\sum_{i} p_i \log p_i
$$

where:

- $$p_i$$ is the probability of being in class $$i$$
- The logarithm is typically taken as base 2 (bits) or base $$e$$ (nats).

Note that entropy ranges from 0 to 1. If entropy is high, we are uncertain about the classifications of the current data in our node. If entropy is low, we are certain about the classification of the data in our node. Given this definition of entropy, the model chooses the split that will maximize Information Gain:

$$
IG = H(\text{parent}) - \sum_{i} w_i H(\text{child}_i)
$$

where:

- $$H(\text{parent})$$ is the entropy of the parent node.
- $$H(\text{child}_i)$$ is the entropy of the $$i$$-th child node.
- $$w_i$$ is the weight of each child node, given by the proportion of samples in that child.

## Regression

For regression, each data point has features mapped to a continuous output value as opposed to a category. Given feature values, our goal is to predict the output value. Using decision trees for regression is very similar to classification. We have parent and child nodes that allow us to continuously split our data until we reach leaf nodes. 

Using our training data, we determine the conditions that split are data at each node by calculating variance reduction. Our goal is maximize the amount of variance, a measure of uncertainty, that is reduced with each split. The concept of variance is comparable to entropy in the classification model. Mathematically, variance reduction is defined as:

$$ VR = Var(\text{parent}) - \sum_{i} w_i Var(\text{child}_i)$$

where:

- $$Var(\text{parent})$$ is the variance of the output values in the parent node.
- $$Var(\text{child}_i)$$ is the variance of the output values in the $$i$$-th child node.
- $$w_i$$ is the weight of each child node, given by the proportion of samples in that child.

We get to a leaf node once we've reached a maximum depth to the tree, the minimum number of samples per node is reached, or when variance reduction is within a negligible threshold. Note that maximum depth and minimum number of samples are parameters that can be fine tuned using validation. 

Once we've trained our model, we can make a prediction using our testing data. To make a prediction, we follow the path of parent and child nodes, splitting the data based on the conditions, until we reach a leaf node. Then, to make the prediction, we take the **average** of the output values of the training data points that belong to that node. 

In the following notebook, we will revist the idea introduced in K-Nearest Neighbors to figure out how to classify roller coasters as those with inversions and those without. In this case, we will use height, speed, and G-Force as our features.
