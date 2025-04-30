**Linear regression** is a machine learning algorithm that attempts to determine a linear relationship between a set of inputs and their corresponding output values. It is essentially the perceptron model except without the activation function. Here is the general model: 

$$
y_i = \beta_{0} + \beta_{1} x_{i1} + \cdots + \beta_{p} x_{ip} + \varepsilon_i
= \mathbf{x}^\mathsf{T}_i\boldsymbol\beta + \varepsilon_i, \quad i = 1, \ldots, n
$$

where $$x_{i}$$'s are our input feature values and $$y_{i}$$ are the corresponding output values that we are trying to predict. In linear regression, we make a couple assumptions. Here, we assume that $\varepsilon_i$ are independent and identically distributed (i.i.d.) normal variables. Looking at the plot of $$x_{i}$$ against residual errors allows us to check this assumption. Linear regression is essentially the simple perceptron model without the activation function.

Using the training data $$(\overrightarrow{x}_i, y_i)$$ linear regression seeks to estimate the coefficients ($$\beta$$'s) that minimize the least squares error, which is the sum of squared errors between observed data points and the predicted values.

Solving this linear least squares problem, we get $\hat{\beta} = (X^\top X)^{-1} X^\top y$.

Note that the term **"linear"** in linear regression refers to the linearity of the coefficients, meaning that input values $$x_{i}$$ can be transformed (e.g., log transformation) while still maintaining the linearity of the model. 

This is one of the most intuitive and simple algorithms. This makes it easy for people to understsand and visualize. However, its simplicity also means that a linear model may not be appropriate for many datasets. For instance, **linear regression assumes that data points are independent**, which makes it unsuitable for time series data or other scenarios where observations are correlated. 

In the following notebook, we will apply **linear regression** to analyze the relationship between **the height and maximum speed of roller coasters**. First, we will fit an initial model and perform diagnostic checks to assess its appropriateness. Then, we will remove some outliers based on the type of the roller coaster to improve the linear model. 
