# Kernel SVM Intuition

&nbsp;&nbsp;&nbsp;So as you recall, in the support vector machine situation, we had a set of observations which belonged to different classes, and the point was to find this decision boundary between them so that any future observations could be identified which class they fall into. And in this case, we can see that there's a decision boundary, and the support vector machine algorithm tells us exactly how to find that boundary. 

![](../Assets/photos/kernel%20SVM_1.PNG)

&nbsp;&nbsp;&nbsp;But what happens when we cannot find a boundary? What happens in a situation like this, for example? We can't just draw a line through these points, right? We can't just separate them with a straight line. We can't separate them with a horizontal line. We can't separate them with a vertical line. Whatever we try to do, we cannot separate these points in the same way that the support vector machine algorithm told us to.

![](../Assets/photos/kernel%20SVM_2.PNG)

&nbsp;&nbsp;&nbsp;Well, this happens because in this case the data is not linearly separable. So here we've got the two examples side by side.  
On the left the linearly separable data, and on the right the non-linearly separable data. And what the support vector machine algorithm does is it helps us find that decision boundary or correctly place that decision boundary. But it does have an assumption. The assumption is that the data is linearly separable. So basically it's saying that it is possible to place the decision boundary. So the support vector machine algorithm helps us choose the optimal decision boundary out of the multiple decision boundaries that we can draw. Whereas in the non-linearly separable case, we can't even draw one single decision boundary or linear decision boundary. So, therefore, the support vector machine algorithm just won't work by definition. And so what are we going to do?  
&nbsp;&nbsp;&nbsp;Well, and this is what this section is about. This section is about coming up with an algorithm that will help us deal with situations like that where we have to extract this class when it is surrounded or in other situations where you can't just simply just draw a line. And the way this section is structured, or the intuition tutorials of the section is first of all we're going to explore a method we just called going to higher dimensional space, where we will learn how we can take this data set and add an extra dimension into our space that we're dealing with and make our data linearly separable.

![](../Assets/photos/kernel%20SVM_3.PNG)


# Mapping to a higher dimension

&nbsp;&nbsp;&nbsp;In today's tutorial, we will find out how we can take our non-linearly separable data set, map it to our higher dimension and get a linearly separable data set, invoke the support vector machine algorithm, build a decision boundary for our data set, and then project all of that back into our original dimensions.  

First off, we're going to look at a simplified example. We're going to look at a one-dimensional data set. So, normally we visualize everything in the PowerPoint with two dimensions to make it, you know, look pretty and so that we can kind of understand how it would work in multiple dimensions, but, right now, that will be a bit too complex for us to start with so we're going to start with a single dimension. So, here we've got the X one-dimension, we've got some points here, so we've got nine data points, and as we can see they are non-linearly separable. So, in a, in this dimensional in a single dimension, dimensional space a linear separator would not be a line it would be a dot, right?  
So in a two dimensional space, a linear separator is a line, in a three-dimensional space it's a hyperplane, but in a one-dimensional space it's a single dot. So can we separate separate the green from the red with a single dot here? So, this is a non-linearly separable data set. Now, how can we apply the method of increasing the dimensionality of this space to make it a linearly separable data set in a higher dimension?

&nbsp;&nbsp;&nbsp;So, we're going to create this mapping function on the fly. So, let's say that this point over here is around 5.

![](../Assets/photos/kernel%20SVM_4.PNG)

&nbsp;&nbsp;&nbsp;It doesn't really matter, it can be any number, but just for argument sake, let's say that this point over here is 5, right? And then it keeps going. So, our first step to build the mapping function. There can be multiple mapping functions that you can build, I'm just gonna show you one that came to my mind. So, the first step will be to go F = X-5 so to subtract 5 from our data set. That is going to move everything to the left. So, basically, now this is what the result looks like. 

![](../Assets/photos/kernel%20SVM_5.PNG)

&nbsp;&nbsp;&nbsp;And then the next step would be to square all of that. So F is now = to X-5 squared. Well, basically, you'll have this squared function going through your chart and then all of these will be projected onto the function. So, that's what it looks like F = X-5 squared.

![](../Assets/photos/kernel%20SVM_6.PNG)

&nbsp;&nbsp;&nbsp;And now what we want to do is we just want to see that it is, indeed, linearly separable. There's our linear separator. So, in a two-dimensional space, as we remember, a linear separator is a straight line, and, as you can see, this data set became linearly separable in this dimension.  
So, you can see that we were able to take this line and separate all of the red elements or of our data set from the green element.

![](../Assets/photos/kernel%20SVM_7.PNG)

&nbsp;&nbsp;&nbsp;So, there's our two-dimensional space and, basically, you would apply the same principle. So, here you cannot apply, or you cannot invoke, the support vector machine algorithm because it is not a non-linearly separable data set in this space, but, then, you would apply some sort of mapping function. And the same thing applies to two-dimensional space moving into a three-dimensional space. You would map it into a three-dimensional space and then, somehow, it would become a linearly separable data set in this space. And here we've got the new dimension, which is Z, and in a three-dimensional space the linear separator is no longer aligned; it's a hyperplane. And so this hyperplane separates the two parts of our data set in the way we want. So, the support vector machine algorithm has helped us build this hyperplane.

![](../Assets/photos/kernel%20SVM_8.PNG)

&nbsp;&nbsp;&nbsp;And then, basically, so we've got this result, then we just project it back into our two-dimensional space and we've got this circle that encompasses our classes, or separates our classes. And there we go, we've got the non-linear separator. So, as you can see, we can still, even though we have got a a bit of a more complex problem where we cannot directly apply the support vector machine algorithm as we used to, we can still go into a higher dimension and then apply the support vector machine algorithm. And, like, we won't go into detail if it's possible all the time, and if there's cases when it's not possible, and so on what you would do there,

![](../Assets/photos/kernel%20SVM_9.PNG)

&nbsp;&nbsp;&nbsp;but the point is that there is a solution that you can explore the higher dimensions so that this is not a dead end. You can just do that. But there's a problem. There's a problem with this algorithm. And the problem is that mapping to a higher dimensional space can be highly compute-intensive so it might require a lot of computation, a lot of processing power, and, you know, the larger your data set the more of a problem this can cause. And, therefore, this approach isn't the best because you can imagine, like, you have a a data set and then mapping it to a higher dimension, performing all the calculations there, and then coming back to your lower dimension. For a computer that can cause a lot of delays. It can cause a lot of, like, processing backlog and issues in, in that sense.

![](../Assets/photos/kernel%20SVM_10.PNG)


# The Kernel Trick

&nbsp;&nbsp;&nbsp;So here we've got the Gaussian or the radial basis of function kernel, and those are two interchangeable terms. And, now let's have a look at this function.  
So, K stands for kernel, and it's a function applied to two vectors. The X vector, so this is just a some sort of point in our dataset, and L stands for landmark. I means there might be several landmarks. I means there might be several landmarks. And then that equals to an exponent in the power of minus the double vertical lines, mean the distance between X and the landmark squared divided by two sigma squared. 

![](../Assets/photos/kernel%20SVM_11.PNG)

&nbsp;&nbsp;&nbsp;Well, let's explore this through a visual example. So here I've got an image which represents this particular function for a specific sigma for a specific landmark. But this is what it looks like when you visualize it.

![](../Assets/photos/kernel%20SVM_12.PNG)

&nbsp;&nbsp;&nbsp;So let's go through this step by step. Let's look at the tip of this visualization. It's right in the middle of this whole XY plane. And so if you project that back onto the plane and the bottom, you'll have the kernel, or not the kernel, that's the landmark. We're gonna call it the landmark, that's where the middle of this bottom square is, and that's from where we're measuring the distance. So K, this distance X minus LI this distance that we're squaring here will be measured from that landmark.

![](../Assets/photos/kernel%20SVM_13.PNG)

&nbsp;&nbsp;&nbsp;So let's take a point and look at it. So there is a point, it's somewhere on our plane, it's quite far away from the landmark. There's a distance. So we're taking that distance, we're squaring that distance dividing it by two sigma squared, taking negative and then we want to see what the result will be. And so how can we confirm that this visualization is actually indeed aligned with this formula. So it's pretty simple. The distance here, let's assume it's quite large, right?  
So it's quite a large distance compared to some other points that are closer to the landmark. So basically the distance here is a large number. And if we take a large number and we square it, right? We get an even larger number. And then we divide by two sigma squared, assuming it's still a large number, again depends on the sigma and we'll find out the role of sigma in the this tutorial. But assuming this is still a very large number so you've got a very large number here, and then you saying negative, you're making it a negative. A very large but negative number. So if you take an exponent and you put it into a power of very negative, a very large negative number, That gives us a value very close to zero. So it's basically equivalent to saying, one divided by E to the power of a thousand, and that is a very, very small number. So that basically means when you're far away from the landmark or from the center, you get pretty much zero on the vertical axis, and which aligns with our image here.

![](../Assets/photos/kernel%20SVM_14.PNG)


&nbsp;&nbsp;&nbsp;Now let's have a look at another example. So at this point is actually closer to the landmark. And here if we measure the distance, it's quite small. So now if you take a small number you square it and you still have a small number, you divide by two sigma square, you still have a small number, so you look at E to the power of minus a small number. So let's say E to the power of minus, So let's say E to the power of minus, for example, or E to the power of minus 0.1. So that basically means, so this number is close to zero as you get closer to the landmark then this number gets closer to zero. So, and we know that E the power of minus 0.01, 0.0001, and so on, basically as you get close to zero E to the power... We get closer to E to the power of zero. And E to the power of zero is one. So basically as you get closer to your landmark this number here gets smaller and smaller and smaller and the whole right part over here converges to one. So it becomes bigger, bigger, bigger, bigger, bigger. And you climb this hill up to the top where you get to one in at the very landmark itself. So when you exactly hit the landmark, you get to the top. And so that is just a quick way of checking that this image is indeed the kernel function that we're looking at. Why is this all useful? Why do we need this? Well, because we are going to use this kernel function to separate our data set to build that decision boundary.

![](../Assets/photos/kernel%20SVM_15.PNG)

&nbsp;&nbsp;&nbsp;There is our two dimensional space : 

![](../Assets/photos/kernel%20SVM_16.PNG)

&nbsp;&nbsp;&nbsp;And now what we are going to do is we are going to take the landmark and put it somewhere among our data set. And there's a whole methodology on how the machine learning algorithm, when you implement it in R or Python or any other language, how it does it. And we are not going to go into detail on that because we're just focusing on the intuition. But basically there's a way to find an optimal placement for these landmarks. And so landmark is placed .

![](../Assets/photos/kernel%20SVM_17.PNG)

&nbsp;&nbsp;&nbsp;and next what happens is the distance as you can see here, the circumference around this kernel function is actually projected here onto our visualization. So what this circumference allows us to do is it allows us to take all of the points that are within that circumference and have them like assign them a value of above zero. So anything outside the circumference all of this blue stuff, so basically all these red points, they'll get a value of zero, right?  
If you apply this function. Or a value very very close to zero. If on the hand any point falls within the circumference, based on this function, it'll get a value of above zero. And that is how we can separate the two classes, the green from the red. Just if we pick the right sigma, so here we know that sigma actually, well, we don't know that yet, but what's a sigma's role is that it defines how wide this circumference is. So if you increase sigma, this circumference will increase. Like this picture didn't change, but it should change. This circumference here would increase and you'd take more of a space up, or if you decrease sigma, the circumference will decrease and therefore you'll take less points. And so basically by finding the right sigma, you can set up the correct kernel function to assign zero values to all of the points that you don't want in your classification, and values above zero to the points that you do want in your classification. And that will allow you to separate the two.  
That will allow you to classify each one. And that in essence is the kernel trick. We have created a decision boundary, without actually going into a higher dimensional space. Without having to project all of our or create a mapping function that's going to, take us through dimensional space and do all the computation. The point is we're not doing the computations in the higher dimensional space. We're still doing the computations in the lower dimensional space. Yes we have this visual representation that involves a higher dimensional space. But at the same time if you look at the computational part, we were just calculating this formula and then we're saying if this is greater, if this is equal to zero, then assign class red, if this is greater or equal to, greater than zero than assigned class green. If you look at the computation, it's actually happening still in the two dimensional space, and that's called the kernel trick. So all of a sudden you can adjust your decision boundary and it's non linear.

![](../Assets/photos/kernel%20SVM_18.PNG)  
![](../Assets/photos/kernel%20SVM_19.PNG)  
![](../Assets/photos/kernel%20SVM_20.PNG)

&nbsp;&nbsp;&nbsp;So here, this is a much, it is a very simplified formula but if you take two kernel functions, you just add them up. In reality they have to be coefficients teta here, teta here, and then another teta before. So they have to be coefficients with these with the kernel formula, it's a bit more complex than that. But in simple terms, if you take two kernel functions and you just add them up, then because the value of this function, if let's say this is kernel, or this is your landmark one, because the value of the function, when you get further away, it becomes zero, right? They don't really interfere. So as you move away from this landmark, so this landmark will only encapsulate all of these points around here, and then as you move away, this will be zero everywhere.  
Everywhere else, including in these points. But then this one will be non zero, close to this landmark. And so if you just add them up, you will get non zero values for exactly all of those points. And so therefore you can draw a non-linear decision boundary, which even looks like this. And the formula here would be the point is assigned to the green class when this equation is greater than zero, and the point is assigned to red class when this equation is equal to zero. Now again, this is a very simplified example, in reality, this is a bit different. It's greater or equal to zero, this is less than zero. And that's because we have the coefficients and it is a bit more of a complex, more of complex mathematics behind it. But we don't really need to go into those depths. The point is that we understand here that we can create this non-linear, very complex decision boundary without having to go into a higher dimensional space. Everything is still happening in those same dimensions simply because we're applying the kernel functions. And that is why this method is called the kernel trick. 

![](../Assets/photos/kernel%20SVM_21.PNG)



# Types of Kernel Functions

&nbsp;&nbsp;&nbsp;And today we're going to talk about the different types of kernel functions. So the final thing that you need to know about the kernel SVM is that the radial basis function, which is also called the gaussian function, is a not the only kernel function that is used in this method. So let's have a look at a couple.  
&nbsp;&nbsp;&nbsp;So here we've got the gaussian or the RBF kernel, which we've already spoken about. Then there's also a popular choice which is a sigmoid kernel, and that's a formula on the right, it's in a bit of a different notation, but the essence is the same, is that you still select a landmark, and then, then from there, depending on the distance of the landmark, different results will occur. But in this case, as you can see, this kernel function is directional. So anything, even like just looking at it in this two dimensional space is just a projection. You can see that anything to the right will be automatically right away will have a high value, so it will be included in your classification. Anything to the left will be excluded. So sometimes you might require these situations. So maybe if you look at a two dimensional space, just imagine those points that we had, points on one side are not in your classification. On the other side are your, in your classification, you want to somehow outline that decision boundary or highlight that points, processing points are, should be in your classification then a sigmoid kernel is a popular choice. Also, we've got polynomial kernels, which are also popular.

![](../Assets/photos/kernel%20SVM_22.PNG)



# NonLinear Kernel SVR Advanced

&nbsp;&nbsp;&nbsp;So this is one of the most advanced tutorials in the support vector series of tutorials. Please make sure that you've completed all the previous tutorials on SVR and SVM and Kernels before proceeding with this tutorial because you'll need all that knowledge to be able to tackle this one.  
So imagine you have a data set like this and you are trying to fit a support vector regression onto this. Plus you want to see what kind of trend line is there or what kind of equation is behind this. How do you model, what kind of model can we fit to this? A support vector regression model. So that you can predict what the next value is going to be for a new point that is added to the plot. So if you know X, what is gonna be Y. 

![](../Assets/photos/kernel%20SVM_23.PNG)

&nbsp;&nbsp;&nbsp;Well you might want to try and fit a linear support vector regression and it'll look something like this. You'll have these support vectors, but as you can see like intuitively, you can tell it doesn't fit right? Like you can tell that something is going on here beyond linear and while this it might model may be okay there somewhere at some points, clearly if you get a point with X over here you're gonna get the incorrect value. Or if X is over here, you're gonna get an incorrect value. It doesn't fit, looks like something else is going on You might try something like that. Then that won't fit as well. That doesn't fit. So it doesn't look like a linear model fits here and it looks like something more complex is going on. So how do we build a support vector regression that will fit our data here?

![](../Assets/photos/kernel%20SVM_24.PNG)  
![](../Assets/photos/kernel%20SVM_25.PNG)

&nbsp;&nbsp;&nbsp;Well, this is where non-linear SVR comes in. It's gonna be quite interesting because we need to go to a new dimension. And that's why we're going to add this box. It's just for visualization purposes. Like our data hasn't changed. Our axis are the same, but just for us, once we're transitioning to a third dimension to keep track of things, we're gonna add this box and we're gonna add these diagonals as well as a point, a red circle in the middle, just so visually we can see what's going on. It'll help us. It's just like a visual aid. Has nothing to do with the algorithm itself, it's for illustrative purposes.

![](../Assets/photos/kernel%20SVM_26.PNG)

&nbsp;&nbsp;&nbsp;So now we're going to actually take this and look at it from a different perspective at an angle. So at an angle it looks like this. And that will allow us to build that dimension Z. Now let's get rid of the previous view and we're going to make a copy of it because there's gonna be quite a lot of things going on. And in order to keep track of everything, we'll have two charts that are developing in parallel. 

![](../Assets/photos/kernel%20SVM_27.PNG)

&nbsp;&nbsp;&nbsp;We're going to add a kernel and in this case we're gonna add a new function to take us into a third dimension. We're gonna add the a radial basis function or the RBF. So here, there we go.  
That's what it looks like. That's with the RBF. You can see our data vaguely underneath but here you can see it more clearly. And just to, as a reminder the formula for the RBF function is over there. Now if we project our data onto this RBF you'll see how it works.  
So first of all, the center zero or this 0.0000 on x or Y axis projects straight into the very top. And if you, we discussed this before in the tutorials if you put 0, 0, L is the distance from the center you'll get the very top, you'll get a one. Now let's see how these other points, the other points in our visualization will be projected onto the view. So we're gonna start with this point over here. So that point will be projected into this point in the Z axis somewhere here. By the way some of these things might not be absolutely a hundred percent accurate as I'm drawing them here but they deliver, hopefully they deliver the point home. Okay, so now this point will be projected to over here somewhere, next point over there. And this point, this point and then the following point will be almost at zero. So all this blue stuff over here, the bottom is very very close to zero, very close to zero. So as you can see, we've been keep keeping track on on the left. We've done all of these points over here. Now the other points, the remaining points, these ones they're actually, we can't see them and not to in order not to clutter things, anything in this quadrant in this triangle here, we're not gonna plot it because it's on the back, on the opposite side of this radial basis function or this view And we just not gonna plot it, but just we can just imagine that they're also projecting onto this mountain on the other side.  
&nbsp;&nbsp;&nbsp;Well, next we need to, in a, these three dimensions we need to create, run a linear model. So now we're in three dimensions. Now we can run a linear model. And a linear model in three dimensions is not aligned. So in two dimensions, it's a straight line. In a three in three dimensions, a linear model is a hyperplane.

![](../Assets/photos/kernel%20SVM_28.PNG)

&nbsp;&nbsp;&nbsp;So now if we run a linear model, you'll see that it will...  
How does it fit our data? It fits our data something like this. And what do we want from here? So once we fit the hyper plane to our data in these three dimensions, what do we want from here? We want to see where does it actually cross? Where does it intersect our RBF, our radial based function. So basically all the surface that we see here including the floor, this whole surface where does it intersect? Well it intersects over across this yellow line. So that's the point of intersect or the line of intersect.

![](../Assets/photos/kernel%20SVM_29.PNG)

&nbsp;&nbsp;&nbsp;Now, if we get rid of the plane, we're left of this line. And if we projected back down onto the two dimensions, X and Y, look, watch what happens. So we're not gonna draw it on this plot we're gonna draw it on this plot. So watch what happens. There we go.  
That's our two dimensional line. So the, so that's our intersect line projected on the two dimensional plot. And then effectively E is our model.

![](../Assets/photos/kernel%20SVM_30.PNG)

&nbsp;&nbsp;&nbsp;So if we now look at it in the perspective that we started with you'll see that that is what it looks like. That's the non-linear SVR. Now, I know you probably have a few questions. Let's try to dig into some of the comments. So some of the concepts behind this.  
So first of all, here we have this two dimensional plot. Here is our three dimension, three dimensions. So why is this SVR, right? So where are the support vectors? Well, in a three, in a three dimensional space SVR would run very similarly to how it runs in a two dimensional space. But instead of having like a epsilon and sensitive tube, we would have an epsilon and sensitive space between hyper planes. So we, we would add these two new hyper planes. One would be epsilon above. One would be epsilon below. Remember how we had for linear SVR we had just a tube but now here we have this space in between them. And so basically what that means is any points that are in between the two most utmost hyper planes any points in between them they won't be considered towards like the error for those points will not be considered. What we wanna do is we wanna minimize the error from this epsilon instead of space to the remaining points that are outside. And what this looks like over here is that's our bottom hyperplane. That's its projection array or that's the projection of the part where it intersects with our real basis function. And that's the top hyperplane, that's its intersection or the projection of it's intersection. So this line over here is projected into that one. And basically anything in between was the epsilon sensitive space now has become this Epsilon sensitive tube. And these are the support vectors. The crucial point here is that this is the outcome originally, this is these hyper planes are identified or built from this view from the three dimensional view. So that's where these points come in place. So this point is actually underneath, we can't see it. It's over there. And there's also these two points that are on the left. So from here they're built. And then this is just a projection. Just to put it into a perspective. So that's why it's still a support regression because we have these points. Now hopefully that explains why it's a support vector regression. There's just one last thing I wanted to mention. The final thing is that everything we've been talking about here is for illustrative purposes. In reality, the way this works is very similar to the how the support vector machine works, what we discussed about the kernel trick, that in reality we don't have to go into a third dimension to all these projections and then find our hyper planes find this epsilon sensitive space and then project everything back and get this. It would be too computationally expensive. So what we actually discussed here is a a more complex approach. This would be like the full fledged approach with going into a third dimension, doing the hyper planes, coming back, getting our end result, That would be like the full Monty in a way. But effectively what happens, or in reality is that we use the kernel trick. So just like with the support vector machine we don't have to go into a third dimension. Everything happens in the same space simply by how we use the kernel trick. Now we won't dive into more detail on that. I'll let you think about that in your own time on how the kernel trick would be used here because simply it's a, it's a easier concept than what we discussed. By looking at the example of the kernel trick in the SVM. We can extrapolate how that would work or how that would benefit us here as well. But in a nutshell this is what the non-linear support vector regression is all about. And the best part is of course, the result that it allows us to model non-linear relationships like this and get insights from our data.

![](../Assets/photos/kernel%20SVM_31.PNG)



# Kernel SVM in Python

![](../Assets/photos/Logistic%20Regression_1.PNG)  
![](../Assets/photos/Logistic%20Regression_2.PNG)  
![](../Assets/photos/Logistic%20Regression_3.PNG)  
![](../Assets/photos/Logistic%20Regression_4.PNG)  
![](../Assets/photos/Logistic%20Regression_5.PNG)  
![](../Assets/photos/kernel%20SVM_32.PNG)  
![](../Assets/photos/Logistic%20Regression_7.PNG)  
![](../Assets/photos/Logistic%20Regression_8.PNG)  
![](../Assets/photos/Logistic%20Regression_9.PNG)  
![](../Assets/photos/kernel%20SVM_33.PNG)  
![](../Assets/photos/kernel%20SVM_34.PNG)  

























































































































































































































































































































































































 




















































































































































 





























































  

































