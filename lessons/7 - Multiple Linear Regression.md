# Dataset Business Problem Description

&nbsp;&nbsp;&nbsp;Fifty startups is going to be a venture capitalist fund challenge. We've got we've only got five columns. But the real interesting thing about this data is that this is like an very realistic lifelike business challenge. So you've got 50 companies here 50 companies in total. And what they have is they have some extracts from their profit and loss statements from their income report.  
&nbsp;&nbsp;&nbsp;So how much did the company in this given financial year that you're analyzing and for how much in that year did it spend on research and development how much did it spend on an administration like paying employees paying executives and so on. And how was it spent on marketing to those of the tree. And which state it works in. And finally what is the profit What was the profit of that company for that financial year.   
&nbsp;&nbsp;&nbsp;And the challenge here is this is a data set is totally anonymize so we don't know the companies. And also there's only 50 companies so there is a venture capitalist fund that has hired you as a data scientist to analyze these 50 companies over analyze this data set and create a model that will tell the venture capitalist fund which types of companies it should. It is most interested in investing and their main criteria is the profit. So profit is their dependent variable. The most important variable for them and these are all independent variables.

![](../Assets/photos/Multiple%20Linear%20Regression_1.PNG)


# Multiple Linear Regression Intuition

&nbsp;&nbsp;&nbsp;Let's have a quick look at multiple linear regression. So here's the equation for multiple linear regression.

![](../Assets/photos/Multiple%20Linear%20Regression_2.PNG)

&nbsp;&nbsp;&nbsp;Now, going back to our example of producing potatoes on a farm, we might want to predict how many potatoes we are yielding depending on how many kilograms of nitrogen fertilizer we're using, what the average temperature in the season is, and how many millimeters of rainfall we've seen in the season.

![](../Assets/photos/Multiple%20Linear%20Regression_3.PNG)



# Assumptions of Linear Regression

&nbsp;&nbsp;&nbsp;Here, we've got a data set with a linear regression applied and this linear regression seems to be serving its purpose really well. However, if we look at the following three data sets, we can see that a linear regression is applied each time and in fact, it's exactly the same linear regression as in the first case. However, those linear regressions are not serving their purpose, in fact they are misleading. So we shouldn't be using linear regressions in those situations.  
&nbsp;&nbsp;&nbsp;These four data sets are called the `Anscombe's quartet` and they illustrate that you can't just simply, blindly apply linear regression, you have to make sure that your data set is fit for using linear regression. And that's where assumptions of linear regression come in.

![](../Assets/photos/Assumptions%20of%20Linear%20Regression_1.PNG)

So let's have a look at them. There's going to be five assumptions in total plus an extra check.   
&nbsp;&nbsp;&nbsp;The first assumption is linearity. We want to make sure that there is a linear relationship between our dependent variable and each independent variable. And if you look at the chart here on the right, you'll see that the linear regression is misleading. There is actually no linear relationship between the two variables. So we wouldn't use this kind of model there.
  
&nbsp;&nbsp;&nbsp;The second assumption is homoscedasticity. And even though it sounds like a complex term, it actually simply means equal variance. Meaning that you don't want to see a cone type shape on your chart whether an increasing cone or a decreasing cone. Which would mean that variance is dependent on the independent variable. So in this case, we wouldn't use a linear regression either.

&nbsp;&nbsp;&nbsp;The third assumption is multivariate normality or normality of error distribution. If you look at the chart here on the right, you can feel that something is off. The best way to intuitively think about it is if you look along the line of the linear regression, you want to see a normal distribution of your data point. In the case on the right here, we can see something different. And so, again, we wouldn't apply a linear regression there.   

&nbsp;&nbsp;&nbsp;The fourth assumption is independence of observations. And this includes the term no autocorrelation. Sometimes you'll see the assumption titled as no autocorrelation. And what that means is that we don't want to see any kind of pattern in our data. A pattern in the data, like we see here, indicates that our rows are not independent, that some rows are affecting other rows and other rows, et cetera. A classic example of this would be the stock market where previous prices affect future prices, which affect future prices and so on. So in this case, we wouldn't apply a linear regression model.

&nbsp;&nbsp;&nbsp;The fifth assumption is lack of multicollinearity. Basically, we want our independent variables or predictors not to be correlated with each other. If they're not correlated, then we can build a linear regression. If they are correlated, then if we do proceed and build a linear regression model, then the coefficient estimates that we get in the model will become unreliable.

&nbsp;&nbsp;&nbsp;And the sixth point is the outlier check. This is not an actual assumption but rather an extra check that is important to keep in mind when building linear regression models. If you look at the chart here on the right, you can see that the outlier is significantly affecting the linear regression line that we get. So something that we want to consider is, should we remove the outliers before building a linear regression or do we want to build a linear regression with the outliers included? This will depend on your business knowledge and knowledge of the data set.

![](../Assets/photos/Assumptions%20of%20Linear%20Regression_2.PNG)


# Multiple Linear Regression Intuition Step 3

&nbsp;&nbsp;&nbsp;Today we're talking about dummy variables. So basically the information that we have is the profit of each company or of each startup then the R&D spend the admin spend the marketing spend So those three are expenses that the company incurred and then the state in which it operates either in York or California.  
&nbsp;&nbsp;&nbsp;The challenge that we're faced with is that the venture capitalist Fund wants to see if there's any correlations between profit and the months that have been spent on different expenses R&D admin and marketing and also with on which in which stage the company operates. Is there a correlation between profit and all these variables and how would you go about creating a model to understand how knowing R&D spend admin and marketing and stay to predict profit and so therefore profit is our dependent variable and the rest the blue ones are all independent variables.  
&nbsp;&nbsp;&nbsp;And what we need to do is build a linear regression. So let's go ahead and get started as we would with multiple inner aggression.  
And then you've got the state variable and here when we get here we're questioning what should we place in our equation for the state column because we don't actually have a number we don't have a dollar value or any other type of number to add into our equation or we can just add a word into the equation.  
&nbsp;&nbsp;&nbsp;And the thing here is that the state is actually a categorical variable so we talked about types of variables before and we understood that there's categorical variables and there's numeric variables. Well in this case state is a categorical variable and therefore we can add it to our equation. We need to do something about this situation and the approach that you need to take when you face categorical variables in regression models is you need to create dummy variables.  
&nbsp;&nbsp;&nbsp;Let's see how we we can do that.  
First you need to go through your column and find all the different categories you have. So in this case we have two categories. So for every single category that you followed you need to create a new column for New York we're going to create a column called New-Yorker for color for immigrants create calm California so we're kind of expanding our data set and adding some additional columns into it. And how do we populate the column. So this is the fun part to populate these columns.  
&nbsp;&nbsp;&nbsp;The start of the New Yorker. You find all of your rows where the state actually says New York and you need to for those Rosing to put a one in the your column and then in California for all the rows that say California. Basically for all the rows that don't say new or whatever else they say you just put a 0 and then for California for the column California you do the same thing. Wherever A says California in the state column you place a 1 in the California column and for any other values in the state column you place a zero in the California column.  
&nbsp;&nbsp;&nbsp;And so you end up with a data set like this and these two new columns are called dummy variables and building your regression model from here is very simple. All you have to do is use the New York column and you're going to be using it instead of states you know going you'd be using state anymore. And basically you add a variable which is before times D1 and D1.  
&nbsp;&nbsp;&nbsp;In this case is your dummy variable for New York and you don't use the California column either. So as you can see here all the information in our data is preserved. If we just stick to the one New York column because you can tell right away if one is a one then it's a company that works and it operates in New York. If one is a zero it's a company that operates in California. So we didn't lose any information by including only the New York call. And we will actually talk more about why you should never include all of your dummy variable columns in your regression model.  
&nbsp;&nbsp;&nbsp;For now I would like to discuss two things so first of all the New York column or all of the dummy variables they work as switches. In this case let's look at the New York column which we're including in our regression. It works like a light switch so if it's a one then you know that this company is in New York. If it's a zero Sol off in this case in the case of the picture then you know that the company doesn't work in New York option so the dummy variables work like light switches. And that's why they're ones and zeros and they don't need any other values in them. And the second thing is that when you look at this approach it might seem biased. So we are including a variable for New York and there's a coefficient for New York so we basically have this benefit of having a coefficient in our equation for New York which is before but for California there's no coefficient because when D-1 is zero that whole loss part of the equation becomes zero and there's no benefit of a coefficient in our equation for California and might seem biased at first but in reality that's not the case because the way regression models work is that they will take by default that state or that variable that dummy variable that you have not included will become the default situation for this regression model.  
&nbsp;&nbsp;&nbsp;So basically what that means is that the coefficient for California is going to be included in the constant and be zero. And by default when D1 is equal to zero this whole equation will turn into an equation you can think of it as it'll turn into equation for California. But then when D1 becomes one you're adding before which is once again like this is a very basic explanation but you're adding a coefficient which is the difference between New York and California.  
&nbsp;&nbsp;&nbsp;So basically you're altering from California to New York by flipping this light switch if it's on off then kind of default state and the whole equation is working for California. If it's on on then by adding that before you're altering the equation from the default state of California to New York.

![](../Assets/photos/dunmmy%20variables.PNG)



# Multiple Linear Regression Intuition Step 4

&nbsp;&nbsp;&nbsp;What will happen if we include the second dummy variable in the model as well. Let's see then tension here is that you're basically duplicating a variable.  

![](../Assets/photos/dunmmy%20variables_2.PNG)

&nbsp;&nbsp;&nbsp;This is because D2 always equals to one minus D1 the phenomenon where one or several independent variables in a linear regression predict another is called multicollinearity as a result of this effect the model cannot distinguish between the effects of D-1 from the effects from of D2. And therefore it won't work properly. And this is called the dummy variable trap. If you do the math behind this scenario you will see that the real problem is that you cannot have these three elements in your model at the same time the constant and both the dummy variables.  

![](../Assets/photos/dunmmy%20variables_3.PNG)

&nbsp;&nbsp;&nbsp;So to sum up whenever you're building a model always admit to one dummy variable and this applies irrespective of the number of dummy variables they are in that specific dummy set. If you have nine then you should only include eight if you have 100. Then you should only include 99 of them. Also note that if you have two sets of dummy variables then you need to apply the same rule to each set. For instance we could have had a column which specifies the industry in which the companies operate to build the model in that case we would have had to perform exactly the same steps and create another set of dummy variables specifically for that column. And then we would include all but one of those dummy variables in our actual model.

![](../Assets/photos/dunmmy%20variables_4.PNG)



# Multiple Linear Regression Intuition Step 5

&nbsp;&nbsp;&nbsp;How to build models step by step.  
Do you remember the good old days when we had one dependent variable and one independent variable. Everything was easy and we just had a simple linear regression that we had to build. And everything worked great.

![](../Assets/photos/building%20a%20model_1.PNG)

&nbsp;&nbsp;&nbsp;But now in our data we have all these columns. Those easy days are gone now all of these columns are potential predictors for a dependent variable and there's just so many of them and we need to decide which ones we want to keep and which ones we want to throw out.

![](../Assets/photos/building%20a%20model_2.PNG)
![](../Assets/photos/building%20a%20model_3.PNG)

&nbsp;&nbsp;&nbsp;And you'll ask why do we need to throw out columns or do we need to get rid of data why can't we just use everything in our model?  
Well I can think of two reasons of the top of my head. Number one is garbage in garbage out.  
If you throw in a lot of stuff into your model then your model will not be a good model it won't be reliable it won't be doing what it's supposed to be doing is going to be a. So to speak garbage model.  
And number two at the end of the day you're going to have to explain these variables and understand And number two at the end of the day you're going to have to explain these variables and understand of your dependent variable and you will have to explain that to your executives to your boss to people you're presenting to. So if you have a thousand variables is not going to be practical to try and explain that. So you want to keep only the very important ones the ones that actually predict something. So how do we construct a model. This is the process of building the model selecting the right variables. So how do we construct a model.

![](../Assets/photos/building%20a%20model_4.PNG)

&nbsp;&nbsp;&nbsp;Well there are five methods that we're going to discuss of building models.  
We're going to talk about each one of them just now before we do I wanted to say that sometimes you'll hear `stepwise regression` so stepwise regression actually refers to number 2 3 and 4 because as it likes really the the true step by step methods. But sometimes you will hear people say stepwise stepwise regression in reference to just not before so there will replays be bidirectional elimination of stepwise regression and that's fine that's normal that's just because that's the more as you'll see from what we discuss.  
&nbsp;&nbsp;&nbsp;Bi directional ammunition is kind of the more general approach and when people say stepwise regression they kind of by default infer imply imply that is bi directional elimination and you have to inferred from there.

![](../Assets/photos/building%20a%20model_5.PNG)

&nbsp;&nbsp;&nbsp;Method number one `all in`. It's not a technical term I just call it all in basically what it means is just throw in all your variables. Something we just discussed we shouldn't do. When would you do that. One is if you have prior knowledge if you know that these exact variables are the ones are your true predictors you don't have to build anything you already know that this is the case. You might know it from domain knowledge or you might know it because you've done this model before somebody just gave you these variables and said please build a model. Well then you don't really have a choice. You just build the model.  
The other one is you have to perhaps like I can't really think of good examples here but maybe there's some framework in your company that says that you have to use these variables right. So it's kind of similar to prior knowledge but it's not it's not a it's not your decision it's you might want to do it differently but there is a framework.  
And number three you would use this method if you're preparing for a backward elimination type of construction of regression which is our next type.

![](../Assets/photos/building%20a%20model_6.PNG)

&nbsp;&nbsp;&nbsp;So let's move on to `backward elimination`.  
Step one you have to select a significance level to stay in the model. So by default we're going to go with 5 percent so 0.05 and we're going to use it in the next step so it's at the beginning you decide on this significant level.  
Step two you fit the full model with all possible predicter So you kind of do that all in approach which we just talked about and you put all of your variables into your model and now we're going to start getting rid of them.  
Step three you considered the predicter with the highest P-value.   
So after you fitted the model you'll see the one with the highest P value. So if p is greater than your significance level then you go to Step 4 and Step 4 is you have to remove that predict to remove basically the variable that has the highest P value. And from Step 4 you fit the model before this variable so there's a star here because I just wanted to remind myself to tell you that if you just remove the variable. Obviously you can just say that.  
OK now now I've got the new model you have to actually refit them all you have to re recreate them all rebuild it with the fewer number of variables so if you had maybe I don't know a hundred variables and you removed them one of them you have 99 now. Well you have to rebuild it so the coefficients are going to be different. The constant is going to be different. And you you need to perform that step because once you remove a variable it affects all the other variables in your whole regression.  
And so after Step 5 you go back to Step 3. Once again you look for the variable with the highest value in your new model. You take it out you remove. So basically step 4 you remove it. You fit the model again with one less variable. And so on and you keep doing that until you come to a point where the even the variable of the highest P value that p value is still less than your significance level. So if that condition P is greater than sL is not correct then you don't go just have 4 anymore. You go to fin and this case is the finish. And your model is ready. So as soon as all of the variables that you have left in your model are there p values are less than the significance level. Your models prepared.

![](../Assets/photos/building%20a%20model_7.PNG)

&nbsp;&nbsp;&nbsp;Next method is the `forward selection`.  
This is it sounds like the opposite and the picture in the top right corner does illustrate the opposite. But it's a much more complex than just simply reversing the procedure. You will see that it's a much larger procedure.  
We started with step 1.  
Select the significance level to enter the model. And in this case once again we're going to select 5 percent.  
Then we go to Step 2.  
We fit all possible simple regression models. So we take the dependent variable and we create a regression model with every single independent variable that we have. And then we select out of all those models we select the one which has the lowest p value for the independent variable. So you can already see that that is in itself a lot of work.  
Then what we do is we move to step three.  
We keep this variable that we've just chosen and we fit all other possible models with one extra predicter added to the one we usually have. So what does that mean? That means we've selected a simple linear regression with one variable. Now we need to construct all possible linear regressions with two variables where one of those two variables is the one of various. So basically we add on all possible all of the other variables one by one so we choose OK let's add on this variable and then let's add on the next one like. But separately so we construct all possible 2 variable linear regressions and just keeping definitely keeping the variable that we're very selected.  
So what do we do after that.  
Out of all of these possible two variable regressions we consider the one where the new variable that we added had the lowest p value. So if that p value is less than our significance level meaning that you know that variables a good one it's a significant variable then we moved back to Step 3. What does that mean ?  Means that now we have a regression with two variables and now we will add a third variable We'll try all possible variables that we have left as our third variable and then out of all of those models with three variables we will go to Step 4 and we'll select again the one of the lowest p value for that third variable.  
So basically we'll be keep growing the regression model but not just randomly will be actually selecting out of the all all of the possible combinations every single time and growing at one variable at a time. And then we will only stop when the variable that we've added It has a p value that is greater than our significance level. So when this condition is less than SL is not true then we don't go to Step 3 we finished the regression y well because that variable though we just added is no longer is not significant anymore. And we also know that we selected the one with the lowest P-value So there is no other variable that we can add that its p value will be greater will be less than s.l any any regression which is from then onwards it will the variable the new variable will always be insignificant. And so here we finish the regression. And the trick here is that you keep not the current model but the previous one. And that makes sense because you've just added a variable which is insignificant So what's the point of that variable just move a step back.

![](../Assets/photos/building%20a%20model_8.PNG)

&nbsp;&nbsp;&nbsp;And next we're moving on to the `bidirectional elimination`.  
So this one as you can assume or perhaps yes it combines the two step one. Select a significant level to stay or to enter and a significant level to stay. So we're going to select in both cases Phipson but it's up to you what you select set to perform the next step of the forward selection meaning that the one that we just discussed. So where new variables when they enter in order to enter they have to be less than the significance level to enter. So basically add on a new variable based on the forward selection method. Step 3 perform all of the steps of the backward elimination process. So now you should have two variables. Start getting rid of them and see if you can get rid of any of them and then move back to step 2 so then grow by another variable. And every time you go by verbal say let's say you were at five verbalising went to six since you went to six you have to form all the steps of backwardly mesh so you don't just eliminate one variable if you can eliminate one to three however many you can. And then from there you go back to Step 2. And so this is a very iterative process. You keep doing that until at some point you cannot add new variables no variables can enter or no old variables can exit as soon as you get there. Then you proceed to the finish because your model is ready to call. You can add anything you can take anything out that means you've you've created the model. So this is one of the more tedious methods.

![](../Assets/photos/building%20a%20model_9.PNG)


&nbsp;&nbsp;&nbsp;And finally `all possible models`.  
So this is the most probably Saro approach but also the most resource consuming approach because you select a criterion of goodness of fit for instance that caky criterion can be the R-squared lots of different criterions then you construct all possible regression model so if you had and variables and there'll be a two to the power of and minus one total combinations of these variables and that that's exactly how many models there can possibly be and then step three you select the one of these models with the best criterion that you're looking at. There you go your model is ready.    
So sounds easy but let's have a look an example even if you have 10 columns in your daughter you'll have 1023 models. That's insane. That's an insane amount of models and we're not talking about columns that you've already filter out so call them that you know that like in our example you might have five or six columns. Now we're talking about when you get a data set that you need just is pretty much a rule and it has like maybe 100 columns.  
Well it's not a good approach because basically it's growing exponentially the number of models is growing exponentially. And it's it's very resource consuming to get a result from this approach.

![](../Assets/photos/building%20a%20model_10.PNG)


# Multiple Linear Regression in Python Step

![](../Assets/photos/Multiple%20Linear%20Regression_4.PNG)  
![](../Assets/photos/Multiple%20Linear%20Regression_5.PNG)  
![](../Assets/photos/Multiple%20Linear%20Regression_6.PNG)

I would like to answer two important questions.  
&nbsp;&nbsp;&nbsp;The first question is, do we have to avoid, you know to do something to avoid the dummy variable trap?  
And the answer is no; because indeed the Multiple Linear Regression class that we're about to import and which will build the Multiple Linear Regression model itself and actually also train it because remember that a class actually can complete several actions including building it and training it. And while this class will automatically avoid this trap which means that indeed you have nothing to worry about regarding the dummy variable trap, you don't have to remove one of the columns here. And that's the beauty of classes.  
&nbsp;&nbsp;&nbsp;Now, second question, do we have to work on the features to select the best ones with, you know the techniques that Kyril introduced to you, like, for example, backward elimination. Do we have to deploy the backward elimination technique in order to select the features that have the highest P values and that are the most statistically significant?  
And the answer is once again, no. For the exact same reason as the dummy variable trap. The class that we're about to call to build our Multiple Linear Regression model will automatically identify the best features, you know the features that have the highest P values or that are the most statistically significant to figure out how to predict the dependent variable.


&nbsp;&nbsp;&nbsp;let's build together the Multiple Linear Regression model. And now actually, I have some good news because, you know, we're still doing linear regression. And in the previous section we actually did simple linear regression, with which we therefore had one feature in our data set, and now we're doing multiple linear regression, which is exactly the same as simple linear regression except that we have several features.  
&nbsp;&nbsp;&nbsp;So the good news is actually that the class that we're about to use to build and train this Multiple Linear Regression model is actually the exact same class as for the Simple Linear Regression model, it will just recognize that there are several features and therefore that we are doing multiple linear regression, but the rest will be exactly the same.

![](../Assets/photos/Multiple%20Linear%20Regression_7.PNG)  
![](../Assets/photos/Multiple%20Linear%20Regression_8.PNG)


&nbsp;&nbsp;&nbsp;Here we have to understand something important. You know, compared to what we did in the previous section on simple linear regression. This time we actually have several features, right?  
We actually have four features instead of one, like before. ***And therefore we cannot actually plot a graph*** like we did in simple in our regression, where, you know, we have the features and the X axis and the dependent variable and the Y axis, because simply there are four features. We would need actually a five dimensional graph, which is not possible to visualize as humans.  
&nbsp;&nbsp;&nbsp;So what we're gonna do instead you know, instead of visualizing the test set results on a plot, well we will actually display two vectors.  
The first one is the vectors of the real profit in the test set. And remember that the test set actually counts for 20% of the whole data set. You know, the 10 ground truth.  
And a second vector of the 10 predicted profits of the same test set so that we can compare for each startup of the test set if our predicted profit is close to the real profit.

![](../Assets/photos/Multiple%20Linear%20Regression_9.PNG)


&nbsp;&nbsp;&nbsp;Question 1 : How do I use my multiple linear regression model to make a single prediction, for example, the profit of a startup with R&D Spend = 160000, Administration Spend = 130000, Marketing Spend = 300000 and State = California?  

&nbsp;&nbsp;&nbsp;Question 2 : How do I get the final regression equation y = b0 + b1 x1 + b2 x2 + ... with the final values of the coefficients?

![](../Assets/photos/Multiple%20Linear%20Regression_10.PNG)  
![](../Assets/photos/Multiple%20Linear%20Regression_11.PNG)





















































































































  





























































 








































































































 



































   





























