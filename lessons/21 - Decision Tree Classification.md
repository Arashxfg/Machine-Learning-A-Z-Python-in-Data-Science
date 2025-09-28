# Decision Tree Classification Intuition

&nbsp;&nbsp;&nbsp;You might have heard the term cart. It stands for classification and regression trees and this term is an umbrella term for two types of trees which are what we see calcification trees and regression trees. Now the difference is that classification trees they help you classify your data so they won't give categorical variables such as male or female apple or orange or different types of colors and variables of that sort. Whereas aggression trees they are designed to help you predict outcomes which can be real numbers so for instance the salary of a person or the temperature that's going to be outside and things like that. So those are the two different types and we're going to be talking about classification trees in this section of the course.

![](../Assets/photos/Decision%20Tree%20Classification_1.PNG)

&nbsp;&nbsp;&nbsp;So here we've got an example with lots of points on our two dimensional scatterplot. Now how does a decision tree work. So it is going to do is cut it up into slices in several iterations so let's have a look. So they'll be split one. They'll be split two so split one split our data at X to equal 60 split to split our daughter X1 equals 50 split three. But our Exotic or 70 and split for split our data at x 2. It's not shown here it's about 20. So that is how a decision tree works and the basis for the split. So how are these splits selected how does the algorithm know where to select the splits. Well basically if you have a look at it now and then the split is done in such a way to maximize the number of category in each of these splits so to maximize For instance we want maximum Reade's categories here and here is why it's still the same but then the next split maximizes the number of green here and them more red here. It's a very basic way to explain it. In reality there's some complex mathematics happening in background. The split is trying to minimize entropy. And so it's informational entropy it's a very interesting term. It would take hours and hours and hours for us to go through all of that right now. And so if you want to get into the deeper mathematics behind this algorithm then you certainly can research that. But for us it's sufficient that we're just looking for the optimal split or the algorithms going to find optimal splits that are going to maximize the number of different points in each one of these new pockets are actually called leaves So we've got the starting scatterplot and then at the end you've got these leaves and the final leaves are actually called a terminal lease. So that's how this will occur.

![](../Assets/photos/Decision%20Tree%20Classification_2.PNG)

&nbsp;&nbsp;&nbsp;Now let's rewind a bit and let's do that whole procedure again. But while we're performing the splits we're going to start constructing a decision tree an actual decision tree. Let's have a look.  
So there is our split number one. And what it's doing is it's splitting our daughter at the 60 level. So now let's construct a decision tree that's going to ask that question. So is X too greater than 60 or less than 60 so if is great and 6 it falls into one branch if it's less than 60 it will fall into the next range. So there we go X-2 is less than 60. No yes and no. Next is split two only splits the Data that is above 60 x to verbal. So let's have a look at that. We're only dealing with data that is above X-2 So it's over here and now we're checking. So I'm going back now. Now we're checking as split to happens at 50 for the X1 variable. So here we go x X1 is less than 50 yes or no. So if and here you can see that right away this split already you can tell us whether something is green or red. So if it's less so if we're already above 60 and then below 50 then it's green which we can see here if we are above 50 then it's red which we can see here. So that's how this classification works and all let's deal of the remainder. So here we've got a split 3 happening at 70. If you're below 70 you're obviously going to be red otherwise we're going to need to do another split. So below 70 then it's red. Now we've got to do on the split split for if it's above 20 then it's green. If it's below 20 then it's red if it's above 20 then it's green so that's a no if it's below then yes. So with these decision trees are a good way to structure them is to always keep. Yes yes yes yes. On one side so like if you if you're looking for yesses they're always going to the left looking for those go into the right or vice versa. Just don't mix them up. And then the terminal leaves will predict exactly what color or what classes is left. But at the same time even if you don't get to the terminal leave because it's a very simple tree. Trees can be very very long. And so sometimes you might not even get to the bottom so if you want to classify new observation and for example this observation falls into this section away here then it would go down this road than here and there you go here. But let's say you don't even get to the end you get to somewhere right here. Then in these boxes that don't that have still they still have a mixture here as is a mix of green or red. Then the rule here is that realistic classification occurs so here we know instead of checking this last condition we'll just check what is the likelihood of it being green and red. So here we see that there's more green and red so if we're just going to leave it at this box then we'll just say that it's it's a green dot whereas if we leave it at this hold box if we just just do this part so we only go check the first condition and then we'll leave it here. Then we would automatically say that it's a red dot. If we don't go down the decision tree and check more conditions so that's another way of using a dictionary instead of going to a down to the very end. You can stop at any point and then just use the probabilities to predict your classification. And another thing is that it doesn't always have to be the two variables. So for instance in a decision tree just like any other machine learning algorithm you can have a multidimensional data set which has lots of different columns so in our case we only have two but you might have lots and lots of columns and then you could have a mix of questions being asked here and that's up to the algorithm to come up with those questions.

![](../Assets/photos/Decision%20Tree%20Classification_3.PNG)



# Decision Tree Classification in Python

![](../Assets/photos/Logistic%20Regression_1.PNG)  
![](../Assets/photos/Logistic%20Regression_2.PNG)  
![](../Assets/photos/Logistic%20Regression_3.PNG)  
![](../Assets/photos/Logistic%20Regression_4.PNG)  
![](../Assets/photos/Logistic%20Regression_5.PNG)  
![](../Assets/photos/Decision%20Tree%20Classification_4.PNG)
![](../Assets/photos/Logistic%20Regression_7.PNG)  
![](../Assets/photos/Logistic%20Regression_8.PNG)  
![](../Assets/photos/Logistic%20Regression_9.PNG)  
![](../Assets/photos/Decision%20Tree%20Classification_5.PNG)
![](../Assets/photos/Decision%20Tree%20Classification_6.PNG)













































































