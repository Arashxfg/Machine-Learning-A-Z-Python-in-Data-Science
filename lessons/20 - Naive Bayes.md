# Bayes Theorem

![](../Assets/photos/Naive%20Bayes_1.PNG)


# Naive Bayes Intuition

&nbsp;&nbsp;&nbsp;Well let's have a look here we've got a data set. So it has two features. It has x1 and x2. And there are two categories Category 1 which is rated Category 2 which is green but instead of working with these abstract terms we're going to convert them into something that we can understand a bit better or something that's a bit easier to operate with or to talk about. So we're going to call the Y variable extra variable salary and the x 1 variable is going to be age. So basically we are presenting observations or people that are part of a data set in terms of their age and salary as you can see we have 30 people here on this chart. And the candidate is we're going to replace them with walks. Meaning that person walks to work and Green will be dry. That means that person drives to work. And so now we get our problem to the machine learning challenge that we're going to be solving. What happens if we add a new observation a new data point into the set.  
How do we classify this new data point.  
And so the question is is this person going to be classified as a person who walks to work or is this person going to be classified as a person who drives to work and then they leave base algorithm is going to help us solve this challenge.

![](../Assets/photos/Naive%20Bayes_2.PNG)

&nbsp;&nbsp;&nbsp;We need a plan of attack it is going to be quite a complex approach. But at the same time we're going to break it down into steps and they'll all make sense will be very easy to understand. So our plan of attack we're going to take the Bayes Theorem and we can apply it twice. First time we're going to apply it to find out what is the probability that this person walks given his features and X over here is the features or presents the features of that data point.

![](../Assets/photos/Naive%20Bayes_3.PNG)

&nbsp;&nbsp;&nbsp;so let's go back to the visualization here.  
So here you can see that this is our new datapoint that person has a certain age so let's say the age of that person maybe is like 25 years old. And then they have a salary so let's say their salary is $3000 per year. So those are features of this observation right now we're only working with two variables just for simplicity's sake so we can visualize things age and salary but in reality there could be many many many more features that could be features on how many what what industry they work in or how many years of education they have or how long they've had a driver's license for. And I think they got off how far away they live from work so there could be lots of variables. But at the same time right down are you going to be dealing with two age and salary and regardless of how many variables you have they will be called in we're going to call them features. So given the features of x so given the age of 25 and the salary of $30000 and we'll talk in more detail about exactly what we mean by features just in the moment. And so therefore this part represents that person that we're trying to classify what is the likelihood of a person with those features. So we know that we are taking somebody for those features that we have in our new data point. What is the likelihood of them walking and then you've got the right side. So we're going to talk through each one of these as we calculate them. But for now let's just give them their names going from right to left. So this one on over here is called the prior probability and we're going to calculate that first because it's the easiest to calculate. Next one is the marginal likelihood and we're going to calculate that second the third one is a likelihood. That's just the names that they have. And we're going to Califate that third. And finally what we're looking for is called the post theory or probability we're going to calculate that force. All right so that's our plan of attack for step 1. This is all still step 1 to calculate the probability that somebody walks. Given those features X that we see in our new data point. Next we're going to have Step two where we're going to calculate the probability that somebody drives given those features X that we see in our new data point. And again here will have the probability which will calculate first then the marginal likelihood then the likelihood and then you'll get to pester probability. And finally we're going to compare the possibility that somebody walks given features X and versus the probability that somebody drives human features X and then from there we'll decide which class to put that new data point in. So as you can see that the base class for is a probabilistic type of classify because we're first calculating the probabilities and then based on probabilities we're assigning it close.  
So are you ready to form these steps it's going to be lots of fun we're going to take it nice and easy nice and slowly so that we understand everything.

![](../Assets/photos/Naive%20Bayes_4.PNG)  
![](../Assets/photos/Naive%20Bayes_5.PNG)  
![](../Assets/photos/Naive%20Bayes_6.PNG)

&nbsp;&nbsp;&nbsp;Step one.  
All right so here we have our installation. Let's move it to the left a little bit so we can make some space. Now we're going to calculate the first probability in our Bayes Theorem. We're going to calculate the probability that somebody walks right just the overall probability. What does that mean. That is the probability that somebody to fight knowing anything about them so we're just saying we're going to add a new observation to our data set into here. But we don't know their age and we don't know their salary is going to put it somewhere into our data set. What is the probability that this person that we're adding to our database walks to work bullets. Very easy answer for from here we don't have much choice. The only thing we can do is calculate the number of read observations. Number of people that actually walk and divide by the overall number so probably that person walks to work with farden any other knowledge is the number of walkers and number of people or walk which is these are adults divided by the total number absorption the green dots are the gray dot isn't participating these are adults divided by the total number absorption the green dots are the gray dot isn't participating in these calculations. So here we have probably if somebody walks is 10 10 red dots divide by 50 dots overall.

![](../Assets/photos/Naive%20Bayes_7.PNG)

&nbsp;&nbsp;&nbsp;Here's our data set again. And the first thing you can do is we're going to select a radius and we're going to draw a circle around our observation like that. Now this radius you need to select on your own and you need to decide for you. Algor and this is going to be like an input parameter or an algorithm you could select less because like that more it's up to you. Now what does this radius do. Well what we're going to do is we're going to first of all let's just to make things easier. We're going to remove our DOT for now just so that it's not confusing us. And then we're going to look at all the points that are inside this series and what we're saying here is that all of the points inside the circle are we going to deem them to be similar in terms of features to the point that we had. The point that we had. Remember it had an age of for example 25 and a salary of $30000 per year. So now we're going to draw a radius around it and let's say anybody between the age of 20 and 30 and in the salaries of $25000 to $35000. Anybody that falls in that circle again is it's not a square it's a square is a circle. Anybody who falls somewhere is somewhere in that vicinity is going to be deemed similar to the new data point that we're adding to our data set. So as you can imagine this radius is actually going to have a big say in the way your algorithm works. Well let's say we have this radius and this is how it all played out. We have three red dots one green dot in them. So now what do we do. How do we calculate the probability of X and what is the probability of X. Well the probability of X is the probability of a new point that we add to our data set being similar in features to the point that we actually are adding to it. So basically it's a probability of that new point that we're adding or like any random point that we add is the probability that any random point to fall into this circle and P of X is calculated as the number of similar observations so the number of observations that already we can see in the circle so 1 2 3 4 divided by the total number of durations which is 30. So p of X is foredoomed Bethy. Once again just to reiterate P of x it tells us what is the likelihood of any new random variable that we add to this data set fulling inside the circle. And it is 430 because we only have four. Based on prior knowledge we can solve this for here and this 2d it also is four with 30.

![](../Assets/photos/Naive%20Bayes_8.PNG)

&nbsp;&nbsp;&nbsp;So there is our chart. And now what we're going to do is we're going to draw the same circle again and once again we're going to remove the gray point for now and we're going to color a circle. And so anything that falls inside the circle is deemed to be similar to the point that we're adding. So the question is what is the probability that a randomly selected data point from our data set will be similar to the data point that we're adding. So basically what is the likelihood that a randomly selected data point will be from this circle given this vertical pipe means given that that person walks that we know that that person walks to work the other way to think about this is we're only working with people who walk to work. So we're only working with the red dots which represent people who walk to work. So let's forget about the green dots. They're like they're now they're faint and we're not even talking about them at all. We're only talking about the red dots. So the question is given that we're only working with the red dots What is the likelihood that a randomly selected datapoint from our daughter said from the red dots is somebody who exhibits features similar to the point that we are adding to our daughters. And so basically what is the likelihood that a randomly selected red dot falls into this gray area into the circle. That's what the question we're asking. And there's also very simple now that we know how all this works. It's basically the number of civil or observations among those who work so the number of red dots that actually fall inside this red circle in this great circle that's three divided by the total number of walkers so people and total number of people who walk to work and that is three over 10. So that's our P of the likelihood of somebody exhibiting the features similar to that broader point that we're about to add given that we're only selecting among the red dots.

![](../Assets/photos/Naive%20Bayes_9.PNG)

&nbsp;&nbsp;&nbsp;So that's three over 10 and that was our likelihood. So now if we plug all that in so there we go that likelihood is done. So if you plug all of that in. We'll get our posterior probability. So three over 10 times 10 or 30 and divided by four or three. So if we calculate that Ill give us zero point seventy five. Seventy five percent is the probability that somebody that we put into the place where we're putting x is should be classified as a person who walks to work. That was step one was pretty intense ride pretty exciting to calculate this value.

![](../Assets/photos/Naive%20Bayes_10.PNG)

&nbsp;&nbsp;&nbsp;Next step a step to do the same thing for the likelihood that somebody with features X will be classified or should be classified as a person who drives to work. And here to you a challenge I'm going to challenge you to post this video or rewind back to find out. To have the image in front of you and do these calculations yourself to actually go through the same steps and perform those calculations. If you'd like to see and compare to my calculations then I'm going to put in another video after this one so another tutorial after this one in the course you can just go to the next tutorial and compare. Otherwise I'm going to show you the result now. So the result is one of a 24 likelihood or this are from the right probability is 20 or 30 margin electrical remains unchanged for with. Likelihood changes to one over 20. So the probability of somebody who exhibits features X being a person who drives to work is 25 percent.

![](../Assets/photos/Naive%20Bayes_11.PNG)



# Naive Bayes Intuition Extras

![](../Assets/photos/Naive%20Bayes_12.PNG)

&nbsp;&nbsp;&nbsp;Question: Why is this algorithm called the naive base algorithm? Well the answer is pretty simple. The answer is because the Bayes theorem requires some independent assumptions and the base theorem is the foundation of the naive base machine learning algorithm and therefore the data base machine learning algorithm also relies on these assumptions which are often times not correct and therefore it's kind of naive to assume that they're going to be correct. That's the reason why it's cold.

![](../Assets/photos/Naive%20Bayes_13.PNG)

&nbsp;&nbsp;&nbsp;Let's go back to our example and see what what that means. So here we've got age and salary. And based on those we're using the Naive base algorithm to classify our data points into people who drive to work or people who walk to work. Well the Bayes theorem the way we apply it actually requires that age and salary have to be independent of the variables that we're working with. In this case is your salary have to be independent and that is like a fundamental assumption of the base theorem and then you can only apply it and then you can't get those probabilities and so on. But in our case if you just think about it fundamentally it is probably not the case. Probably there is some sort of correlation between age and salary because as a person gets older their experience grows their their number of years that they've spent and the workforce grows and therefore their salary grows so it's natural for the salary to grow if age. It might not be a super strong correlation for it not for everybody but overall there is some sort of correlation. So they're not absolutely independent variables and also you can even see that from the chart you can just by looking at our child see that there's some sort of correlation between the two variables. And therefore given that they are not independent you can't really apply the Bayes Theorem and therefore you can apply the base algorithm to machine learning and that's why it's called Naive a base algorithm because oftentimes it's applied even though the variables or the features are not independent or not completely independent and it's still applied and it still gives good results. And that's why it's called naive because it's a naive assumption.

![](../Assets/photos/Naive%20Bayes_14.PNG)

&nbsp;&nbsp;&nbsp;Number two P(X)  
So let's have a look at what we performed. So kind of like rewind and analyze what we did in our steps in the proof. So in step 2 what we did is we took over. So when we were calculating X we drew a circle around our new point. We were moved the data point just so it's not in the way. And then we shaded the area. And so what is P(X) will peel back is the likelihood that a randomly selected point from this dataset will exhibit the features similar to the datapoint that we are about to add. And as we agreed anything in that circle is deemed to be similar to our data point. Another way to think about it is what happens if I throw in a random variable or random data point into this data set right now. What is the likelihood that it will fall into the circle what is the likelihood that it will exhibit features similar to the features of the point that I'm about to add into the data set. So basically it falls into that circle and so pay of X is the number of similar observations or similar observations means observations similar to the points that we're about to add. Divided by the total number of observations which is true in our case. So it's four four we can see that there's four points in this circle right now divided by three. And the interesting thing here is that this result is the same both times. So this is in step two in step one where we were calculating for the people who walk to work. So the ability for people who walk to her. It was the same so basically X doesn't change with you calculating it in in the instep one where we're calculating the probability that the person with these features is a person who walks to work or if you calculate in the Step 2 scenario where you are calculating if that person with these features is a person who drives to work and therefore it's the same time. 

![](../Assets/photos/Naive%20Bayes_15.PNG)

&nbsp;&nbsp;&nbsp;So what does that mean. Well let's have a look at formalists so you can see that the formula in step 1 it was p off. The problem of person who exhibits features X that he walks he or she works walks to work and there's a formula in Concepcion X is at the bottom and for a step two it was a possibility of a person who exhibits features X being a person who drives to work. And as you can see proof of X is at the bottom here. So what did we do in step 3. So let's move on to Step Three from here. Step three we compared the two. So now if we take these two formulas these right sides of the formulas and put them into the comparison like that. You will see that at the bottom the denominator is the same. Now though we know that the demon nominator is not zero and it's actually greater than zero probabilities is never less than zero and we know it's not zero. So we can just get rid of it. We can multiply both sides by X and therefore the sign won't change. And also we'll get rid of the denominator. And that way we won't actually have to perform that calculation. So that's one less calculation to perform. So you can just compare the top part of these calculations and so that is what is done a lot of the time. So if you've done other courses on machine learning or if you've read some maybe articles on machine learning you will find that this is oftentimes the case and also sometimes it is not mentioned that this is happening so sometimes it's assumed that or it can be assumed that you know what's going on. So just be careful that look out for that. As we discussed it's totally valid to do it that way but that is only if you're comparing the two. Right if you're only comparing the two then you can do that if you actually wanted to calculate the value. So we said 75 percent 25 percent. You want to calculate the value can't do that because it will be two different realities because you're supposed to divide by a certain value. It's not the actual value. And moreover if you want to like it comparing is OK but calculating the actual value and maybe some perform some operations or you know you calculate the value from this. You want to compare the value from this scenario to a value from another problem right. Like a value from a different kind of a scenario where p of X will be different right. Not from this particular example that you're working with. You want to compare the probability of the person being a person who walks to work. In this example to the possibility of that person being a person who walks to work from a different example right where it will be different if you want to compare across like that. That will also not work because you know X is different so be careful of that. It's always the safer and safer way is always just to perform the full calculation. But if you're doing an orphan or if you just want to save some time or if you just maybe we're reading other literature then it's it's also good to know about this approach where the denominator can be dropped when just comparing between the two.

![](../Assets/photos/Naive%20Bayes_16.PNG)

&nbsp;&nbsp;&nbsp;What happens when we have more than two classes. So remember in this scenario I only had two classes the red the green or the people who walk to work and the people drive to work what happens when you have more classes. How is the challenge different. Well when do we have only two classes we compared as we remember we compared the people the probability that a person who exhibits features X walks to work so basically that new data point that we added. What is the probability that it's a person who walks to work versus what's the probability that that new data point is a person who drives to work. And it turned out that we were comparing 75 percent versus 25 percent and 75 percent was greater than 25 percent and therefore probability of the person of that person be a person who walks to work was greater than that person being a person who drives to work. And therefore we decided to classify them as a person who walks to work. And it's very straightforward. And moreover you'll find that every time when you just have two classes it'll always add up to one. So we didn't even have to calculate the second one. We could have just stopped at this one because if this is 75 percent this one is automatically 25 percent.  So always going to be like that if you have two classes the way changes if you have three classes it is it gets more interesting right. Then there are still two more left. So if you're working with one of just two classes since you calculate one you're done you can decide right away if it's greater than 50 percent then you assign that class if it's less than 50 percent yes another class if it's equal to 50 percent then you've got like a tie whereas if you have two or three or more classes then just counting the one won't be enough because then you have two other ones and you would still have to calculate and at least another one so just means that it's more of an interesting selection problem when you have more classes that's pretty much the main thing that changes when you have more classes.



# Naive Bayes in Python

![](../Assets/photos/Logistic%20Regression_1.PNG)  
![](../Assets/photos/Logistic%20Regression_2.PNG)  
![](../Assets/photos/Logistic%20Regression_3.PNG)  
![](../Assets/photos/Logistic%20Regression_4.PNG)  
![](../Assets/photos/Logistic%20Regression_5.PNG)  
![](../Assets/photos/Naive%20Bayes_17.PNG)  
![](../Assets/photos/Logistic%20Regression_7.PNG)  
![](../Assets/photos/Logistic%20Regression_8.PNG)  
![](../Assets/photos/Logistic%20Regression_9.PNG)  
![](../Assets/photos/Naive%20Bayes_18.PNG)  
![](../Assets/photos/Naive%20Bayes_19.PNG)  

















 




























































































 


















































 





















































 









 

























 






