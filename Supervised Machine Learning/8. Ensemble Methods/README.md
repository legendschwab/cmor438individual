**Ensemble Methods** refer to combining and aggregating the results of multiple machine learning models to create a new model.

Random forests is as an example of an ensemble method as it combines the prediction of multiple smaller decision trees in a random fashion to get more consistent predictions. Random forests uses the method of **bagging** which is illustrated below.

![Bagging](https://miro.medium.com/v2/resize:fit:1200/0*fdDu8RbNLoUzrrlF.jpeg)

*Credits: Plural Sight*

Another ensemble method is called **boosting**. Boosting is a sequential method where weaker models are improved iteratively in order to correct the errors of previous iterations. Models are re-weighted so that those with low accuracy are given a higher weight and inputted to the next model. 

One disadvantage of boosting is that it is prone to outliers. Because each model attempts to correct the errors of the previous model, outliers can skew results. 


Why do we use ensemble methods? The main reason is to reduce variance in our predictions. Every machine learning model has its own pros and cons and use different strategies to model the relationships within our data. For example, the perceptron classifies by using a linear hyperplane whereas k-Nearest Neighbors is effective on clustered data that are grouped in "ball" shapes. The effectiveness of each model will vary depending on the data we have and the features we use. However, by combining the results of several machine learning models either through averaging for regression or majority vote for classification, results are more consistent and overall accurate. 