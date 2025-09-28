# Decision Tree Regression Intuition

&nbsp;&nbsp;&nbsp;So you may have heard the term cart which stands for classification and regression trees. And this is an umbrella term that encompasses two types of decisions trees and as if croaky guessed they are classification trees and regression trees. And in this course we're going to talk about both types but specifically in this section we're focusing on the regression trees. And I wanted to mention right away that regression trees are a bit more complex than classification trees and that's why this is going to be a bit longer and is going to require some additional attention. But nevertheless we're still going to break this kind of somewhat complex topic into a very simple bite sized elements of information so it will all make sense. 

![](../Assets/photos/Decision%20Tree%20Regression_1.PNG)

&nbsp;&nbsp;&nbsp;So let's get straight into it. So here we've got a scatterplot which represent our Darcis sardars that that has been given to us. And the interesting thing about the scatterplot is that we've got to independent wearables x1 and x2. And what we're predicting is a third variable a dependent variable which is white and you cannot actually see one in the. And that is because this is a simply a two dimensional chart only fit the two variables. Why is the third dimension. And if you think about it's like sticking out of your screen that's where that dimension is. And this is just a projection of all the points on the x1 x2 plane. And so if I add a dimension I would look something like that. But once again we can see why right now. And the interesting thing is that we don't actually need to see why because we need to work with this scatterplot for us for a little bit to build our decision tree. And then once we've built it will return to y. Now a quick point I wanted to make here is that I've seen decision trees explained with just one independent variable so x 1 or just X and Y and then and in that case yes you can you can just put X-1 over here and then.  
&nbsp;&nbsp;&nbsp;Why would go here and you would have a bit of a different kind of diagram and you'd be able to explain it that way. But at the same time I think it might not really drive the point home and it can be a bit confusing when it's explained like that although sometimes it is done. Nevertheless I thought would go the full way would do the full monty and would look at this problem with two independent variables because it'll be a more robust explanation so it will make it a bit more complex but is definitely worth it in the long run because that way will understand the decision tree regression and bit or Ashland I would say quite a bit better.  
So let's continue we've got the X1 and x2 these are independent variables the dependent variable we can't see it adds the third dimension and we're actually going to forget about it for a little while.  Right so we're going to just forget about it because we need to work with this scatterplot to see how our decision is going to be great. So once you run the regression tree or decision tree algorithm in regression sense of it what will happen is your scatterplot will be split up into segments and let's have a look at how an algorithm could go about doing that.

![](../Assets/photos/Decision%20Tree%20Regression_2.PNG)

&nbsp;&nbsp;&nbsp;So an algorithm would create a split or here for example at somewhere around 20. So it would basically split your diagram or your scatterplot into two parts. Everything else less than 20. Everything that's great and 20 for the X1 variable then another split would happen here. So for all of the elements in this side they would be compared to 170 greater or less then had been on the split here and then maybe another split over here. Now how and where these splits are conducted is determined by the algorithm. And it is actually involves looking at something called the information entropy and it is a mathematical concept it is quite complex. So it basically means when I perform this split right is this split increasing amount of information that we have about our points. Is it actually adding some value to our the way that we want to group our points and the algorithm knows when to stop is when there is a certain minimum for the information that needs to be added. And once like it cannot add any more information to our set up by splitting these leaves they're called leaves so each one of the splits is called the leaf by splitting these leaves.  
&nbsp;&nbsp;&nbsp;Ones it can add more information than stops or in or the algorithm could let's say stop when you have less than 5 percent well if you were to conduct a split then you would have less than 5 percent of your total points in that leaf and then that leaf wouldn't be created. So there are different variations of different options for that to happen. And but look the most important thing is of course where the splits are happening. And if you'd like to learn more about that you'd you'd need to study a bit more about information entropy. We're not going to go into that mathematical depth right now for us it's sufficient to know that the algorithm can handle this and that it is finding the optimal splits of our data set into these leaves. And the final These are called terminal leaves and then we're going to focus on the practical application of this algorithm how and why we're using these decision trees and how this regression is going to work.

![](../Assets/photos/Decision%20Tree%20Regression_3.PNG)

&nbsp;&nbsp;&nbsp;So we're going to rewind all of this a little bit and we're going to create these splits one by one and alongside we're going to actually start drawing our decision tree. So there's our diagram brand new and fresh. And there goes our For a split. So now we're going to start creating our decision tree. The split happened at 20 so let's start drawing. There is our first decision and we have two options. Yes and No. All right so let's have let's see what happens next. Next happens a split to split to happens at 170 and only happens for the points that are greater than 20. So that means you would check this condition X-1 is less than 20 meaning you checked no. The answer's no. And then you check if x 2 is less than 170 X-News less than once and then a split 3 happens on the other side and it checks if x 2 is alyssum 200. Let's add that here X to this and it and then split 4 happens at 40 and it checks if x 1 is greater or less than 40 and split for only happens for the point that answered to split one they answered. No it's not less than 20. And to split two they answered no. It's yes it's actually less than 170. So no not less than 20 years. It's less than 170. And then this split will four happens X-1 is less than 40. Yes. All right so that's our decision tree. It's done it's drawn. And so what happens next. How what do we actually populate into those boxes. Well this is where we need to remember about our dependent variable. The third dimension and what we need to check here is how are we going to predict the value of y for a new observation that gets added to our scatterplot or our daughters. So let's say we add a observation which is has x 1 equal to 30 and x 2 equals to 50. It did fall somewhere over here. And 50 is somewhere we're headed for some or are here. So obviously it falls into this terminal leaf. And how does that information. So as you can see we've been adding these plates we've added information into our system. So how does that information that now we know that it falls into this terminal leaf. How does that information help us in terms of predicting the value of wife for that new element that we're going to add. Well the way it works is it's actually pretty straightforward. The way it works is you just take the averages of each of your terminal leaves. So you take the average of y for all of these points and that'll be the value that will be assigned to any new point that falls in this terminal. The same for this terminal leave Same for this terminal. Same for this one and same for us. So let's have a look. Let's say the average for why here are sixty five point seven The average for wise here is three hundred point five 1023 here. Minus sixty four point one zero points on here. So for that point that we just discussed with X1 = 30 and x2 = 50 the predicted value of y. The regression tree algorithm would predict a value of minus sixty four point one. If it were to fall in any other terminal if then that's what the value there would predict. So as you can see it's actually pretty straightforward. It's it's very simple as just taking averages but you do need to remember that we are working on the whole point of this exercise is to add more information into our chart into our system to better predict why. Because if you think about it what was our other option what is our default option if the default option were far running any machine learning on this data set is to just take all of the points and take the average across all of the points and whatever that is wherever you point the new element of data that is added to our data set wherever it falls. We just assign. It's always that's average for all of the points that we had existing previously. What we did now is we've split our diagram up into these terminal leaves the machine learning algorithm has added information nurture into our system. And so now we can more accurately predict the value or assign the value of y to a new coming element. And as you can see now it's averages across all of them averages taken into specific parts or segments of our scatterplot and therefore it is or it's supposed to be more accurate. That's the whole point of the regression tree. And now the last time we are left to do is to add the values into our decision tree so basically we just add those values in here and now whenever we have a new value. What would happen is the algorithm which is go through this these checks ended with check where it falls and assign the value. And that's pretty much it. So the scatterplot is more for like physicalization conceptual purposes so you can maybe drive some insights from there. But the core of decision tree is actually held here and that's why the algorithm is called a regression tree.

![](../Assets/photos/Decision%20Tree%20Regression_4.PNG) 
![](../Assets/photos/Decision%20Tree%20Regression_5.PNG)



# Decision Tree Regression in Python

![](../Assets/photos/Decision%20Tree%20Regression_6.PNG)  
![](../Assets/photos/Decision%20Tree%20Regression_7.PNG)  
![](../Assets/photos/Decision%20Tree%20Regression_8.PNG)  
![](../Assets/photos/Decision%20Tree%20Regression_9.PNG)  
![](../Assets/photos/Decision%20Tree%20Regression_10.PNG)  
![](../Assets/photos/Decision%20Tree%20Regression_11.PNG)











 
























































































































 
