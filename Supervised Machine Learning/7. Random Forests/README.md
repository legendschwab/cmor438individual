**Random Forests** build upon decision trees by aggregating the results of multiple smaller decision trees into one. This is why we call this model a random forest.

Why do we have use random forests? In normal decision trees, the model is pretty sensitive to training data points, especially outliers. Since data points can dramatically
affect the various splits. By combining the results of mutliple smaller trees, we balance out the extreme values and get more accurate results.

There are two steps to building a random forest: bootstrapping and aggregation. Together, the process is called "bagging". 

## Bootstrapping

Boostrapping is the process of taking several samples **with replacement** from our training data set. We ensure all data sets are the same size $$n$$. 
Previous research in the field suggests that $$n \approx \ln{N}$$ or $$n \approx \sqrt{N}$$, where $$N$$ is the total number of points in our training data set,
is a good sample size. 

Once we have created several samples of our training data, we randomly choose a subset of features for each sample. By doing a random feature selection, we
balance out the selection of "useful" and "un-useful" features. If we used all the features for every sample, each sample will have decision trees to 
behave extremely similarly. We want to best balance out the extremeties in our data, so we want varied decision trees to get more accurate results.

## Aggregation

Once we've created our samples and chosen features, we create fit a decision tree for each sample as normal. This applies for both classification and regression models.
Now, when we are given a new data point from our testing data and asked to make a prediction, we apply each data point to each decision tree, using the 
features selected for each tree to make a prediction. Once we have all the predictions, we take the majority voting or mode as our prediction for classification models.
For regression models, we take the average output value for each decisions tree to get our overall prediction.

In the following data set, we will use Random Forests to predict board games as those that are long (play time less than 60 minutes) and short (play time greater than 60 minutes) based on the features of complexity, rating, minimum age, and 
