# Simple Linear Regression Intuition

&nbsp;&nbsp;&nbsp;Let's have a look at simple linear regression. So here's the equation  

![](../Assets/photos/simple%20linear%20regression_1.PNG)

So on the left, we have our dependent variable, which we're trying to predict. On the right, we have our independent variable, which is the predictor.  
&nbsp;&nbsp;&nbsp;we are going to use that example we mentioned about predicting the output of potatoes on a farm based on the amount of fertilizer that we use.

![](../Assets/photos/simple%20linear%20regression_2.PNG)



# Ordinary Least Squares

&nbsp;&nbsp;&nbsp;So, we have our data points. The question we’re answering in this tutorial is :  
How do we know which of the sloped lines is the best one?  
As we can see, there are multiple slope lines we could draw through our data points. To answer these questions, we need to apply the method of `Ordinary Least Squares` (OLS).  
&nbsp;&nbsp;&nbsp;Visually, this works by vertically projecting our data points onto our linear regression line. We would need to do this for every individual regression line we consider, but for simplicity, we’ll focus on this central line in the tutorial.  
&nbsp;&nbsp;&nbsp;For each pair of points, we now have two values : y<sub>i</sub> and y^<sub>i</sub>.  
y<sub>i</sub> is the actual potato yield.  
In our example, a farm produced a potato yield when using a specific amount of nitrogen fertilizer.  
y^<sub>i</sub> on the other hand, is the predicted yield from the regression line we’re analyzing.  
&nbsp;&nbsp;&nbsp;As you can see, there’s a slight difference between the actual yield and the predicted yield. This is not a normal line that perfectly pass through every data point. That’s impossible. But we want the best line, which depends on minimizing these differences.  

![](../Assets/photos/simple%20linear%20regression_3.PNG)


# Simple Linear Regression in Python

![](../Assets/photos/simple%20linear%20regression_4.PNG)  
![](../Assets/photos/simple%20linear%20regression_5.PNG)  
![](../Assets/photos/simple%20linear%20regression_6.PNG)  
![](../Assets/photos/simple%20linear%20regression_7.PNG)  
![](../Assets/photos/simple%20linear%20regression_8.PNG)  
![](../Assets/photos/simple%20linear%20regression_9.PNG)  
![](../Assets/photos/simple%20linear%20regression_10.PNG)


&nbsp;&nbsp;&nbsp;Linear Regression is one of the most commonly used statistical modeling methods in data science. It’s also a topic that attracts many questions from our community of students.  

***Question 1: How do I use my simple linear regression model to make a single prediction, for example, to predict the salary of an employee with 12 years of experience?***  

***Question 2: How do I get the final regression equation y = b0 + b1 x with the final values of the coefficients b0 and b1?***

![](../Assets/photos/simple%20linear%20regression_11.PNG)  
![](../Assets/photos/simple%20linear%20regression_12.PNG)  
![](../Assets/photos/simple%20linear%20regression_13.PNG)  
![](../Assets/photos/simple%20linear%20regression_14.PNG)  
![](../Assets/photos/simple%20linear%20regression_15.PNG)   
![](../Assets/photos/simple%20linear%20regression_16.PNG)  
![](../Assets/photos/simple%20linear%20regression_17.PNG)   
![](../Assets/photos/simple%20linear%20regression_18.PNG)   
![](../Assets/photos/simple%20linear%20regression_19.PNG)















