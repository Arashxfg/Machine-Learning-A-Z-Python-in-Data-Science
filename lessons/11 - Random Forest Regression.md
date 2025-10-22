# Random Forest Regression Intuition

&nbsp;&nbsp;&nbsp;Today we're talking about that random forest and the intuition behind it. As specifically we're talking about the random forest applied to regression trees rather than classification resistance but the concept is very simple and you'll find that this story is very similar to the one for the random forest on classification trees.  
So a `random forest` and `ensemble learning`. So `random forest` is a version of `ensemble learning` you've got other versions such as `gradient boosting` and `ensemble learning` is when you take multiple algorithms or the same algorithm multiple times and you put them together to make something much more powerful than the original.

![](../Assets/photos/Random%20Forest%20Regression_1.PNG)

&nbsp;&nbsp;&nbsp;So you pick a random K data points from your training set so now we're kind of going to leverage a lot what we talked about in the session on regression trees. So you remember there we had lots of data points and then we built a regression tree and we put the decision tree and use that to forecast the value that would be assigned or the y value for any new element that will be added to our data set as the average in the terminal leaves space. So here what we're doing is we're using the whole dataset we had. And we're only picking K data points from that training set. Then we're going to build a decision tree associated to these K data points rather than building a decision tree based on everything your data set you just building a decision tree based on those data points that just like a subset of your data set. then you choose the number of trees that you want to build and you repeat steps on it. So you just keep building and building and building these trees or building a lot of regression decision trees. And then finally you use all of them to predict so for a new data point you make each one of your entries predict the value of y for the data point in question and assign the new data point that average across all of the predicted y values. So basically instead of just getting one prediction you getting lot of prediction by default. See these algorithms are set to about 500 trees at least. So you're getting 500 predictions for the value of y. And then you taking the average across those. And in that way you're not just predicting one tree be ridiculed based on a forest of trees. And that improves the accuracy of your prediction because it is you're taking the average of many predictions and therefore even if one is somehow one of the decision trees was built exactly perfectly because the way of those data points were selected it just didn't turn out as a perfect tree or a gray tree even if you're using it by itself. You'd get a bad prediction because using the average it is less likely. So you're going to get a more accurate prediction and more. And the second thing is that there are more stable algorithms like this `ensemble algorithms` are more stable because any changes in your data set could really impact one tree. But two for them to really impact a forest of trees is much harder so therefore ensemble is much more powerful in that way.

![](../Assets/photos/Random%20Forest%20Regression_2.PNG)


# Random Forest Regression in Python

![](../Assets/photos/Random%20Forest%20Regression_8.PNG)  
![](../Assets/photos/Random%20Forest%20Regression_3.PNG)  
![](../Assets/photos/Random%20Forest%20Regression_4.PNG)  
![](../Assets/photos/Random%20Forest%20Regression_5.PNG)  
![](../Assets/photos/Random%20Forest%20Regression_6.PNG)  
![](../Assets/photos/Random%20Forest%20Regression_7.PNG)  




































