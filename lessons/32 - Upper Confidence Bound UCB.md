# Upper Confidence Bound UCB Intuition

&nbsp;&nbsp;&nbsp;Today we're talking about the upper confidence bound and the intuition behind this algorithm of the reinforcement branch of machine learning. So let's get started.  
As we discussed previously, the problem we are solving is a multi-armed bandit problem where you've got five or more or any number of slot machines and you can bet your money in any one of them. And you need to find out how to bet to maximize your returns. And basically we agreed that behind every machine there is a certain distribution and that's because you don't know which of these distributions is optimal. You need to combine exploration of these machines with their exploitation in order to find out which one of these machines is the best and then you can start exploiting that one. And the modern application of this problem is of course advertising.  
&nbsp;&nbsp;&nbsp;So if you have five or 10 or 50 or 500 different ads, how do you find out which one is the best one? Of course, you can run just an AB test and then use the results of that, but that means you're doing the exploration and then you're doing the exploitation separately. You're going to incur lots of costs, you're gonna waste a lot of time. We want to combine exploration, exploitation, and get to the optimal result as soon as we can and maximize the output of our efforts.

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_1.PNG)

&nbsp;&nbsp;&nbsp;All right, so this is a quick summary of the multi-arm bandit problem. So let's go through this very quickly so we can get to the fun stuff. So we have D arms, for example. Arms are ads that we display each time a user comes to a webpage, each time an ad is displayed or a user visits this page, that's a round. For each round "N", we choose which ads to display. Usually, you can only display one ad. Like with the one-arm bandits, you can only pull one of those arms. You can only choose one machine to bet on at each round. And ad "I", gives a reward whether it's a zero or a one. And basically our "I" of ante of "N" is equal to one. If the user clicks on ad and zero, if you didn't, the user didn't. And our goal is to max our total reward we get over the mini round.

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_2.PNG)

&nbsp;&nbsp;&nbsp;So that's basically what we are doing and this is how the upper confidence bound algorithm works. And I won't go into too much detail on this because actually Hadlana is going to run you through this and you're going to code this from scratch in R and you're gonna code this also in Python in the following lectures of the course. So we're not gonna waste, spend time on this. We're actually gonna get to the essence of the algorithm, right?

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_3.PNG)

&nbsp;&nbsp;&nbsp;So let's get to the intuition part which is, how does it work? What's actually happening in the background when this algorithm is running?  
All right, so let's have a look. These are our slot machines or one-arm bandits and each one of them has a distribution behind it. We wanna find the best one, right? Looking at them, we can't tell which one it is But let's see, we do know, let's see we know the end result. Just for arguments sake, what would it look like? Well, this is for instance, in this case, the distribute. These are the distributions behind those machines. You've got, you know, the machine, this is how they're spitting out the results with these distributions. And just by looking at this, you can tell right away which one is the best machine. Which one would you bet your money on constantly if you were playing, it would be this one, right?  
So right away here you can see that this one has the best return and you would want to just, all the time, just bet on this one and your outcome would be the best. But we don't know that, right? We don't know that. And we wanna find that out in the process of playing these machines or using those ads that we're running and find out you know, which one is getting the most clicks. We don't want to, we don't have the time and money to do that exploration before the actual campaign is running. We want to do that in the process. We wanna maximize our return already from the very start. So how do we do that?  
Well, let's transfer these distributions or the actual expected return from these distributions onto a vertical access. 

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_4.PNG)

&nbsp;&nbsp;&nbsp;So we're gonna take these values and we're gonna put them onto a vertical access over here. So there's our vertical access. So for distribution one, let's say the value was there. For distribution two, there was a value we could, we remember it was lower. Distribution three even lower. Distribution four higher, and distribution five the best, right? So those are the expected values or returns for each of those distribution for each of those machines. That's why our Y axis. But again, we don't know that. So how does this algorithm work?  
Well, it assumes some starting point. For every distribution, it just assumes that there is a certain starting value that, okay, let's just assume that because we can't distinguish we can't discriminate against these machines in any way. They all look the same. Let's assume that they all have the same return and let's put it on that level. Now then what the algorithm does is those formulas that are behind the algorithm, they create a confidence band. And it is designed in such a way that with a very high level of certainty that confidence band will include the actual... Will include the actual return or the actual expected return. So basically the first couple of rounds are going to be trial runs.  
So we are going to intentionally just try out the machines at least one time each in order for us to be able to place this value here and come up with a confidence band, which is gonna be very large. So at the very start, it's very large but it is designed specifically in a way that the expected value which is this one over here with a very high level of confidence falls inside this confidence with a little high, with a very high degree of certainty falls inside this confidence bound which is built around this red empirical value which we have derived. At the very start, it's all the same, right? So, and then how does this algorithm work?  
Well, out of all of them, we pick the machine with the highest confidence bound. Right now it can be any of these machines, right? They all have the same confidence bound. We're talking about the upper confidence bound. That's why algorithm's called the upper confidence bound. And so we are just gonna pick any one of them because it doesn't matter which one we pick. Again, we don't know these blue, these color lines, we don't know about them. 

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_5.PNG)

&nbsp;&nbsp;&nbsp;All we see as the agent or as the person analyzing this, we only see these boxes and they're all identical to us, so we just pick any one of 'em. Let's say we pick this one.  
So what happens next is we actually pull that lever of that machine and something happens or we place that ad, right? So we display that ad next and we want to see did the person click on it or did the person not click on it? And in this case, the person didn't click on it, right? So it went, this red value goes down because it's, well now we have another observation just for this machine that is added to the whole sample of observations for this machine. And the value goes down because well always this red value is like the observed average. The observed average is going to, according to the law of large numbers, is always going to, in the long run is going to converge to the expected, expected return or expected average or expected value for this distribution. So, therefore it is a very likely that this value is gonna go down. And now because we have an extra observation the second thing happens is the confidence bound, confidence interval, you see that?  
Confidence interval becomes smaller simply because we have an additional observation. Of course, it doesn't become that much smaller but this is to, just to illustrate a point because we have an additional observation, we are more confident in our predictions, we are more confident in everything that's going on. So the confidence interval slowly starts to shrink.

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_6.PNG)

&nbsp;&nbsp;&nbsp;All right, so the next step is now we find the next one with the highest confidence bound. So obviously it's not this one, it's one of these four. Just pick any random one. There we go. This one, do the same thing. So again, the ad is displayed, a person either clicks or doesn't click. And that affects the average that we've measured so far. The empirical average or you've pulled the lever you've got a certain, you know, you either won or you lost. And that affects your empirical average, this red line. And as expected, it slowly starts to converge with over like lots of iterations. It'll start to converge to the expected value. So it comes closer and right away you can see now this machine is all of a sudden above all of the other machines, right? So if this was the end of this iteration, that's it. We would assume from here that this is the best machine and we would start exploiting it and therefore this algorithm would be completely useless. But we shouldn't forget about the second thing that happens. The second thing that happens is that because we got an additional observation in our sample now, we are more confident in this interval and these confidence bounds, they're designed. Their only purpose is to include the actual expected value wherever it is.  
We don't know where it is, but they are telling us that this value, this green value somewhere inside this box. But because we got additional observation, we're more confident our sample size is larger. So we are more confident in the overall picture for this machine. So the confidence bounds decreased. And now as you can see, it's no longer the top machine because even though it went up, the confidence bounds went down. So now we're going to look for the next highest confidence bound. 

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_7.PNG)

&nbsp;&nbsp;&nbsp;It can be any one of these three machines. And just look at any one randomly for now, this one. And here, even though the red line is above the blue line so according to the law of large numbers, you'd expect this to converge to that. But sometimes it can randomly occur that it can go the other way, right? It things can happen like this. It's all probability zone. So, basically it might even go up. So there we go, it went up, even though the blue line was below the red line, it can happen as a, you know, like as a, just as per chance, right? In the long run it will converge, but on a random occasion it can go up, it can go in any way.  
And again, we got another element in the sample. So the confidence bands converge. Okay, so we kinda get the picture of what's going on here.

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_8.PNG)

&nbsp;&nbsp;&nbsp;So, now we're gonna pick the next one of the highest upper confident bound, let's say this one. Then we do the trial, we do the round. What happens as the person click on add? Do we win money from the slot machine and it goes down? Probably not. We didn't click on the ad, didn't win money from the slot machine. So the average of our observation goes down, comes closer to the expected value and the confidence bounds also decreased. 

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_9.PNG)

&nbsp;&nbsp;&nbsp;Okay, now we kind of, now we're in business, we can now, all of them are kind of starting to play. Next one is this one, okay, this is the... Now because we know the end result, we know that this is the best one, right? We know that this is the best ad or this is the best slot machine we should be using. But like, because we were kind of like given this insight just for argument's sake or for the purpose of this exercise. But the person that's reforming this algorithm or the algorithm itself, doesn't know that. So, unknowingly, it's actually starting to exploit the best option right now. So again, okay, it goes up, good, confidence band goes down and as you can see, it's still the best one. All right, so now we're gonna do it again. We're gonna use this one again and it comes closer and but the confidence bound goes down. Again, this is all just for illustration purposes. Of course it's not gonna go down by that much just because of one observation, but we don't wanna be sitting here through a thousand iterations. This is just to demonstrate the overall picture. So, even though we exploited the best option by exploiting the best option, we're decreasing the confidence bound which gives an opportunity or by exploiting any option if it keeps going up, keeps being good because we are building up the sample size. This gives an option to the other, gives opportunity to the other options to, or machines or ads to have a chance in the place so that we are not just, you know we're not biased towards which one we think is the best or optimal outcome, optimal machine. 

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_10.PNG)

&nbsp;&nbsp;&nbsp;So now that we move on to this one, same thing comes closer, bounds decrease. 

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_11.PNG)

&nbsp;&nbsp;&nbsp;move on to this one, bounds decrease and we move on this one and bounds decrease.

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_12.PNG)

&nbsp;&nbsp;&nbsp;And then again, this one bounds decrease. And again, this one, might jump closer, bounds decrease. And even though we were very close to, you know finding the solution that, that one, the bounds decrease so much. And you'll actually see this in the practical application and practical tutorials that are following that sometimes we will, after using the optimal option for some time,

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_13.PNG)

&nbsp;&nbsp;&nbsp;after using the optimal option for some time, we'll switch the algorithm will still switch to a suboptimal option just because the bounds are decreasing all the time. And then we'll use this one, bounds will decrease.

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_14.PNG)

&nbsp;&nbsp;&nbsp;and now we're back to the best one, bounds decrease. And then we're just going to be exploiting this one and exploiting this one and exploiting this one because we found out that it's the best one. So that is, in essence, the whole concept behind this upper confidence bound algorithm. And that's how it solves the multi-arm bandit problem. It's a very interesting solution, much more sophisticated than just selecting randomly or running an AB test and then selecting the option, you know that one. So you know if you're an advertising or if you've got campaigns or if you come across problems that are similar to this, always just remember about the upper confidence bound algorithm. You can apply this in your work as well. Very powerful algorithm.

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_15.PNG)



# Upper Confidence Bound in Python

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_16.PNG)

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_17.PNG)

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_18.PNG)

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_19.PNG)

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_20.PNG)

![](../Assets/photos/Upper%20Confidence%20Bound%20UCB_21.PNG)
































































































































































































































































































