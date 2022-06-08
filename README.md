# Linear Regression

Linear regression can be broadly classified into:
1. simple linear regression
2. multiple linear regression
3. Polynomial regression

Real world data is never linear. Stochastic errors are always present in the data. So, real worl data is sort of linear but not perfectly linear.
Our aim of implementing Linear regression is to obtain a line or plane or hyperplane for which is MSE is minimum i.e. residuals are minimum.

β₀ - This is offset. Even if all independent variables are zero, dependent variables will have some value and it is the value of β₀.

βₙ  - These are the values of slopes associated with the variables. There values signify the the degree of dependence of the dependent variable on the independent variables. If the slope value corresponding a variable is high, then we can say that the value of dependent variable is highly dependent on that variable.



![WhatsApp Image 2022-06-07 at 6 59 13 PM](https://user-images.githubusercontent.com/92416952/172392835-5b29742b-78fb-44bc-a62d-8faf3f73d0f4.jpeg)
We can see that the β₀ value shows the intercept on the dependent variable axis. And the β₁ and β₂ values show two cases of slope values for an independent variable. β₂ value has higher slope than β₁, this means that the degree of dependence of the dependent variable on the independent variable is higher when the slope value is more. We can also put this as, for some change in the independent variable, dependent variable is more sensitive for changes made in the independent variable when the slope value is β₂.

There are two approaches to solve the problem using Linear regression.
1. Closed form solutions :
    a) In this approach we obtain the model i.e. the weight or slope values for all the variables using a formula based approach. 
    b) This approach involves a finite number of mathematical operations. So, we get the slope values for all the variables i.e. β values and hence the equation for          line or plane or hyperplane. 
    c) This is nothing but our model.matrix inversion is 
    d) Closed form solution technique used for linear regression is known as OLS (Ordinary Least Squares) technique.
    e) OLS technique is implemented in the sklearn class of Linear Regression.
    
3. Non closed form solutions
    a) This approach involves approximations based method. Here Number of steps are not finite.
    b) So, here the model (best fit line or plane or hyperplane) i.e the weight or slope values (β₀ β₁ β₂ ..... βₙ) are found out using approximations. With each step        we reach closed to the best fit weight values.
    c) Technique used in this case is Gradient Descent.
    d) Gradient Descent is implemented in the sklearn class of gradient descent.
    
## Question -When comparing both closed form and Non closed form approaches, we can say that when number of features are very high, we need to use the Gradient Descent technique implemented in the SGDRegressor from sklearn class. Why?

## Answer- Because there is a matrix inversion term in the formula of OLS ( ordinary least squares ) technique for the multiple linear regression.

![WhatsApp Image 2022-06-07 at 7 58 58 PM](https://user-images.githubusercontent.com/92416952/172407421-e6ebb6d3-98fa-47d6-bf59-f3e87dbaa8c5.jpeg)
 
If we look at the computational complexity of mathematical oerations, we can see that the time complexity for the matrix inversion will be O(n³). For a data set having m data rows and m number of columns, the order of (XᵀX)⁻¹ matrix will be (m+1)*(m+1). If a data has 999 rows and 999 features, the order of matrix (XᵀX)⁻¹ will be 1000*1000 ( we have added 1 to the order so as to account for the β₀ intercept term in the β matrix. So, here the time complexity for the mateix inversion operation will be O(n³)= 1000000000. This is huge!! 
So, as the size of dataset increases, time complexity for the matrix inversion term will increase in the cubic nature. If a dataset having large number of columns or the dataset is image based or texual data based, this mathematical oparation of matrix inversion will take a lot of time.

OLS formulae for simple linear regression (only one dependent variable column ) and multiple linear regression ( multiple dependent variable columns) are as follows :
![WhatsApp Image 2022-06-07 at 8 55 35 PM](https://user-images.githubusercontent.com/92416952/172419748-b8f797c6-d4f4-4037-8945-17efd656da12.jpeg)
For deriving these formulae for the model parameters , i.e. the slope values corrrsponding to all the features and the β₀ value, we need to decide on the cost function ( Squared in order to nullify the cancelling of the '+'ve and the '-'ve slope values AND divided by number of rows in the dataset so as to reduce the huge number we get because of sqaring of the distances of actual and predicted Y values). We differentiate the cost function with respect to the β slope values.

My own simple linear regression LINK

# Multiple Linear regression-
While visualizing we can only visualize upto two independent variables and one dependnent variables. Beyond that the data points and the classification boundaries are plotted into hyperplanes. For 1 DV and 1 IV, we find equation of best fit line. For two IV and 1 DV, we find equation of best fit plane. For more than 2 IV and one DV, we find equation of best fit hyperplane.

For n numbe rof features, equation of predicted value y becomes - 
![WhatsApp Image 2022-06-08 at 7 51 18 AM](https://user-images.githubusercontent.com/92416952/172517495-52f16fc9-8e80-4208-bdd3-ac739de6a4fe.jpeg)
β is the weight allocated to that feature for finding out value of target variable.
β₀ is the offset. If all feature values become zero, then the value of target variable is β₀. It is actually the intercept value and is also present in hyperplanes plotted in highr dimansion plot.

My own multiple linear regression LINK

# Polynomial Regression-
![WhatsApp Image 2022-06-08 at 9 13 15 AM](https://user-images.githubusercontent.com/92416952/172527081-17066b97-6f35-4a9e-9073-917aeaddde98.jpeg)
Degree for polynomial regression is a hyperparameter. For lower values of degree hyperparameter, model underfits. For higher values of degree hyperparameter, model overfits.
## Question-  Why is it still calles linear regression even though now there are higher degrees of x present?

## Answer- Because relationship between DV (y) and coefficient values β is still linear.
To use polynomial regression, we need to do extra preprocessing step for creating additional columns in the dataset corresponding to higher degrees of x.





