# Polynomial Regression Intuition

![](../Assets/photos/Polynomial%20Regression_1.PNG)  
&nbsp;&nbsp;&nbsp;So let's have a look at when you'd use a polynomial regression when it would come in handy. Let's say you've got a observation a set of directions which are abs then the line that fits this data is always simple in your aggression. You can see it filters fitted quite well. But let's for a change say that the data set looked something like this. So if we try to use a simple linear regression here where is expressed like that you'll see that it doesn't fit quite well so in the middle you've got data underneath and then as you go further the data will be above the line.  
&nbsp;&nbsp;&nbsp;Well we can try to correct that by using a polynomial regression Let's have a look. So instead of the linear regression we're going to conductive polynomial regression and that's in this case fits perfectly.

![](../Assets/photos/Polynomial%20Regression_3.PNG)  
![](../Assets/photos/Polynomial%20Regression_2.PNG)  



# Polynomial Regression in Python Step   
![](../Assets/photos/Polynomial%20Regression_4.PNG)  
![](../Assets/photos/Polynomial%20Regression_5.PNG)  
![](../Assets/photos/Polynomial%20Regression_6.PNG)  
![](../Assets/photos/Polynomial%20Regression_7.PNG)  

&nbsp;&nbsp;&nbsp;Now, what we're gonna do, is we're gonna create a multiple linear regression model, but instead of having different features, you know, x1, x2, and xn, well, these features will be x1, x1 squared, and x1 at the power of n. And we'll actually tune this parameter n a bit to try several powers.  
&nbsp;&nbsp;&nbsp;The process of building this model on Python will be first to create a matrix of the powered features, you know, a matrix of features, but not containing different features like x1, x2, and xn, but a matrix of features containing x1 as a first feature, then x1 squared as a second feature, and then x1 at the power of n as an nth feature. So that will be our matrix features, and we will call it x poly.  
&nbsp;&nbsp;&nbsp;And then we will create a linear regressor object, you know, from the LinearRegression class, to integrate these powered features of this matrix of features, in this new linear regressor.

![](../Assets/photos/Polynomial%20Regression_8.PNG)  
![](../Assets/photos/Polynomial%20Regression_9.PNG)  
![](../Assets/photos/Polynomial%20Regression_10.PNG)  
![](../Assets/photos/Polynomial%20Regression_11.PNG)  
![](../Assets/photos/Polynomial%20Regression_12.PNG)  
![](../Assets/photos/Polynomial%20Regression_13.PNG)  

























