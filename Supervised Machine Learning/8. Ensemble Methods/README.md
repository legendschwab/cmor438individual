Ensemble Methods refer to combining and aggregating the results of multiple machine learning models to create a new model.

Random forests is as an example of an ensemble method as it combines the prediction of multiple smaller decision trees in a random fashion to get more consistent predictions. 

![Bagging]("https://images.prismic.io/encord/34b910ef-a1e7-44ac-8e2c-0221c0e639f3_Ensemble+Learning+Bagging+%26+Boosting+-+Encord.png?auto=compress,format")

*Bagging vs. Boosting*

Why do we use ensemble methods? The main reason is to reduce variance in our predictions. Every machine learning model has its own pros and cons and use different strategies to model the relationships within our data. For example, the perceptron classifies by using a linear hyperplane whereas k-Nearest Neighbors is effective on clustered data that are grouped in "ball" shapes. The effectiveness of each model will vary depending on the data we have and the features we use. However, by combining the results of several machine learning models either through averaging for regression or majority vote for classification, results are more consistent and overall accurate. 