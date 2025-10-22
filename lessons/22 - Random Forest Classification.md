# Random Forest Classification Intuition

&nbsp;&nbsp;&nbsp;Today we're talking about random forests. Let's have a look inside. So first thing we're going to learn is a new concept ensemble learning. What is ensemble learning and learning is when you take multiple machine learning algorithms and put them together to create one bigger machine learning algorithms so that machine learning algorithm the final one is actually using leveraging many different other machine learning algorithms and they can be the same machine learning algorithm as we will see today. We're going to be looking at the random forest method which combines a lot of decision tree method so instead of running a decision tree method which we talked about earlier. So running at once we're going to run it multiple times and that will give us a run of four.

![](../Assets/photos/Random%20Forest%20Classification_1.PNG)

&nbsp;&nbsp;&nbsp;So let's have a look at the step by step process to understand how all of this happens. So step one is you pick a random K data points from the training set. Then you build a decision tree associated to those data points. So instead of building a decision tree based on everything you have in your daughter said you build a decision tree just based on some of the data points that you have. So kind of like a subset of ALL your daughter said Next you choose the number of trees you want to build. And you repeat steps 1 and 2 and then once you have all those trees and you have a new data point so when you want to check where a new data point falls how is classified for a new data point you make each one of your entry trees predict the category of which the data point belongs to. And then you assign the new data points to the category that wins the majority vote. So that's how a random forest works. 

![](../Assets/photos/Random%20Forest%20Classification_2.PNG)

&nbsp;&nbsp;&nbsp;So basically you start off with one tree and then you build another tree another tree another tree and each one of those trees is being built on a randomly selected subset from your daughter. And even though each one of those trees might not be ideal overall on average they can perform very well and that's a major advantage of this algorithm. It's kind of leveraging the power of the crowd so to speak and sort of just relying on one tree. It's checking what all the trees are going to say and then just taking the majority vote and deciding the classification based on that. And that power of numbers can help get rid of certain errors and certain uncertainties in your algorithm and make it more precise.


# Random Forest Classification in Python

![](../Assets/photos/Logistic%20Regression_1.PNG)  
![](../Assets/photos/Logistic%20Regression_2.PNG)  
![](../Assets/photos/Logistic%20Regression_3.PNG)  
![](../Assets/photos/Logistic%20Regression_4.PNG)  
![](../Assets/photos/Logistic%20Regression_5.PNG)  
![](../Assets/photos/Random%20Forest%20Classification_.PNG)
![](../Assets/photos/Logistic%20Regression_7.PNG)  
![](../Assets/photos/Logistic%20Regression_8.PNG)  
![](../Assets/photos/Logistic%20Regression_9.PNG)  
![](../Assets/photos/Random%20Forest%20Classification_4.PNG)
![](../Assets/photos/Random%20Forest%20Classification_5.PNG)























