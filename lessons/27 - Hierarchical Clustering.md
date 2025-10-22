# Hierarchical Clustering Intuition

&nbsp;&nbsp;&nbsp;All right so what is hierarchical clustering. Well believe it or not. But if you have points on your scatterplot or data points like we looked at previously this is a two dimensional space. If you apply a hierarchical clustering or just say H.C. for short. What'll happen is you will get clusters again a very very similar to K means In fact sometimes the result of no results can be exactly the same as k means clustering. But the whole process is a bit different.

![](../Assets/photos/Hierarchical%20Clustering_1.PNG)

&nbsp;&nbsp;&nbsp;So let's talk about it in a bit more detail. So the first thing that we need to note is that there's two types of hierarchical clustering:   
`agglomerative` and `divisive`.  
So agglomerated is the bottom up approach and you'll see in more detail just now what that means so we'll be starting at the very bottom and then building our way up device of his opposite starting at the top and devising a cluster into multiple in this course we'll be focusing on agglomerative approach.

![](../Assets/photos/Hierarchical%20Clustering_2.PNG)

&nbsp;&nbsp;&nbsp;So the agglomerative clustering How does it work well to start off we're going to break it down into step by step approach and then we'll look at an example and manually perform the classroom. All right so step one in H.C. is to make each data point a single point cluster so that forms and or and data points.  
Your first step is to look at each one of them as an individual cluster.  
Then Step two is to take the two closest data points and make them one cluster to combine them into one cluster that forms and minus one clusters then sip that is to take the two closest classes out of the ones now that you now have and make them one cluster that forms and minus two clusters then it's a to repeat step 3 until there is only one class to basically just keep repeating step three and combining points into bigger and bigger and bigger clusters. And so there's only one huge cluster left. So you just keep repeating step three. And at the end you're done and you'll have one huge cluster left and how to get from one to two or three classes. 

But one thing that stands out here is the words closest clusters. Now we've already talked about distances and we mentioned you clearly that you can use Euclidean distances or other distances and that's totally fine when you're working with the usual point. But here we're actually going a step even further we're talking about not just the proximity of points but actually proximity of clusters. And this is something worth noting so I'd like to pause here for a bit and or I kind of step to the side and talk about the closeness of clusters and how you measure distance between clusters because that can really affect your algorithm if using hierarchical clustering.

![](../Assets/photos/Hierarchical%20Clustering_3.PNG)

&nbsp;&nbsp;&nbsp;So first of all Euclidean distance just to get this out of the way once and for all Euclidean distance is in a two dimensional space it's calculated like that. So the distance so x if you got two points one with the coordinates x 1 and Y 1 p to coordinate x to y to then nuclear and distance or the length of this line is calculated as X to minus x 1 so that the distance between the x's squared plus the distance between Y is squared. So basically and then you add them up and then take the square. So basically it's that and you've got a right angled triangle over here and you've got the cattle out here and you've got another one catgut here. 

![](../Assets/photos/Hierarchical%20Clustering_4.PNG)

&nbsp;&nbsp;&nbsp;And now let's talk about the distance between two clusters so let's say you have two clusters the red and the blue. How do you measure the distance between them. What is the definition of the distance between two clusters.

![](../Assets/photos/Hierarchical%20Clustering_5.PNG)

&nbsp;&nbsp;&nbsp;It's not as obvious as it might sound at the start because there can be a couple of options for instance you can.  
Option one is to take the two closest points and measure that and call that the distance between the two clusters.

![](../Assets/photos/Hierarchical%20Clustering_6.PNG)

Option 2 is actually take the two further points and call that the distance between two classes is also a valid approach.

![](../Assets/photos/Hierarchical%20Clustering_7.PNG)

Option 3 Take the average take the average of all the distances between the different points in the classes all the combinations of different points and take the average of that distance.  

Option 4 is take the distance between the centroid and find the Central is and find the distance between the centroid and call that the distance between the two clusters.

![](../Assets/photos/Hierarchical%20Clustering_8.PNG)

&nbsp;&nbsp;&nbsp;So it's a very important part of her called clustering what you define as the distance between two classes because that can significantly impact the output of your algorithm. Now we're not going to delve much deeper into this. It's just something to remember to note. And based on your particular situation where there's a business problem or other type of data science problem based on what exactly do you think is the best approach you're going to need to define that in your algorithm so just keep that in mind that for the hierarchical clustering algorithm the distance between clusters is a crucial element and you need to remember what exactly you are setting at is you setting it to be how you defining it in your approach.


&nbsp;&nbsp;&nbsp;Now let's move back to our example so we've already looked at the step by step rules and I I'm a big fan of step by step approach. Now we have this step by step approach and it might have seemed a bit overwhelming as always because we didn't have an example. But now we're going to have that example and we're going to look at how to build those hierarchical classes.

![](../Assets/photos/Hierarchical%20Clustering_9.PNG)

&nbsp;&nbsp;&nbsp;So step one make each data point a single point cluster that forms a six clusters Let's have a look at that. You can see every single point is a separate cluster.

![](../Assets/photos/Hierarchical%20Clustering_10.PNG)

&nbsp;&nbsp;&nbsp;Next take the two Close's data points and make them one cluster where we can see that these two points are the closest.So we're putting them together in one class and now we have five classes one two three four and these two are one class.

![](../Assets/photos/Hierarchical%20Clustering_11.PNG)

&nbsp;&nbsp;&nbsp;Step three take the two closest clusters are the ones we had and turn them into one cluster. So out of the classes we have because remember each point are these four. So if we go back here each point here is a separate class and this is a classroom. So now just measure the distances between clusters and let's say in our example we're going to be talking about the distance between clusters as the minimum distance so that would be the distance between those two classers that would be the distance that would be measure all the difference between clusters and you find out that these are actually the closest clusters and you combine them into one class. Next you repeat step three so next out of these have coursers out of one two three four clusters you can see we had five. Now we have for every time we reduce the number of clusters by one of these four classes which are the class as well. The this seems as the closest cluster so we're going to combine that.

![](../Assets/photos/Hierarchical%20Clustering_12.PNG)

&nbsp;&nbsp;&nbsp;Now out of these three clusters which of course it looks like these two are. So combining them and now we've only got two classes left so the last step would be to combine them because they are by default going to be the closest. So there we go. And so that is the end of our algorithm. That's how it converges. You've we've gone through the process of CRE of going from all points seen as an individual cluster so each point is an individual cluster to now we only have one cluster that combines all of the points.

![](../Assets/photos/Hierarchical%20Clustering_13.PNG)  
![](../Assets/photos/Hierarchical%20Clustering_14.PNG)  
![](../Assets/photos/Hierarchical%20Clustering_15.PNG)




# Hierarchical Clustering How Dendrograms Work

&nbsp;&nbsp;&nbsp;Hello welcome back to the course of machine learning in the breeze tutorial we talked about the hierarchical clustering the intuition behind it and how it works. But at the same time we didn't quite understand what the whole purpose of H.C. wasn't what the benefit of it was yes we went from a huge amount of classers where every single point or data element was considered a cluster and then to one big cluster but as a result and now we have one huge costs are what's what's the point of all of it.  
How do we get to the result we want. The actual clustering so I can K-means For instance we would have two or three closer's. How do we get to that right number of clusters. So this is where the Dendrograms come in and they will help us understand everything.

&nbsp;&nbsp;&nbsp;So here I've got a chart on the left which contains six points and on the right of the go to another chart we're going to use this chart to create a Dendrograms. Now I know it might sound a bit confusing at first especially because we haven't talked about that diagrams but through creating one we will learn what they are.  
&nbsp;&nbsp;&nbsp;So we're going to now go through the H.C. algorithm and slowly create those clusters. So to start off with every single point is an individual cluster. Right so every single one of these points is an individual cluster.

![](../Assets/photos/Hierarchical%20Clustering_16.PNG)

&nbsp;&nbsp;&nbsp;Next what we're going to do is we're going to find the two closest points which are these two and put them into one cluster. So that's our step 2 in our algorithm.  
That's the two closest points. And now we're putting them into one cluster. Now what we want to do on this diagram here on the ground is we want to somehow signify that these were indeed the two closest points because the Dendrograms is kind of like the memory of the H.C algorithm. Going to remember every single step that we were performing. So there they are those two boys P2 and P3. How do we signify that we've just connected them and that they were the closest well to connect them would use like a horizontal line. But then where would we put it would you put at the very bottom would we put a bit higher. What's going to determine the distance. How high are we going to places like. So this line is actually placed this height actually has a meaning this height is the median distance between them.  
And it also represents the computed dissimilarity between the two points are the two clusters. And what that means is the further away two points are.  
And that is been measured or captured in identity Gramp by the height of this bar how high we're setting it. And then the bar itself just shows us that we connected P2 and P3.

![](../Assets/photos/Hierarchical%20Clustering_17.PNG)


&nbsp;&nbsp;&nbsp;Next we're going to move on and we're going to proceed to the next step in our shelter and we can perform step three. So we're going to find in the next two closest clusters and connect them. So here we've got all each each point out of these four is a cluster. Then we've got this cluster. Now we need to find the two closest are all of them. And let's say or from what we see these two other closest So let's outline them. There we are. And so now they form their own cluster. Now we want to point that out in the Dendrograms as well.  
Well we agreed that this vertical axis represents the Euclidean distance and Euclidean distance represents the dissimilarity between two of our observations.

![](../Assets/photos/Hierarchical%20Clustering_18.PNG)

&nbsp;&nbsp;&nbsp;And the next step is to again repeat step 3 so we're going to look among these. All of these clusters of which are the closest. So there we go. So this one is the was the closest I'm going to back here. This cluster is closer to this cluster containing other closer and pretty much out of all the distances between the clusters.  
So what do we do next is we combine these clusters into one cluster.  
Now we need to represent that somehow here so what we just did is we took this cluster that we have to be connected with P1.

![](../Assets/photos/Hierarchical%20Clustering_19.PNG)

&nbsp;&nbsp;&nbsp;So we are going to combine them and represent that on dendrograms. So here the hotline is very high because the distance dissimilarity was very high between these two clusters.  
So you can just by looking at the dendrograms understand in which order these classes were formed

![](../Assets/photos/Hierarchical%20Clustering_20.PNG)



# Hierarchical Clustering Using Dendrograms

&nbsp;&nbsp;&nbsp;Today we're going to put the two together and learn how to get the maximum value out of our hierarchical clustering algorithms.  
What we need to do with the Dendrograms or what we can do is look at the horizontal levels and set thresholds so we can set heights thresholds or distance actually distance thresholds are also called dissimilarity thresholds because this vertical axis measures the median distance between points which also represents the dissimilarity between them or points or clusters. So what we can do is set a threshold for all dissimilarity and we can say that we don't want dissimilarity to be greater than this level so again doesn't matter with the absolute value is. It matters what the relative value is and how it looks on this image. So we were setting the dissimilarity threshold we saying that anything if we come across clusters that are above this threshold so we don't want within a cluster to have dissimilarity above this threshold so what that will do is will give us two clusters.  
So let's say we've got some values here that say this is 1.5 this is 2.0. So let's say we want to set the threshold at 1.7. And what this is doing is it is not allowing any clusters that would have dissimilarity of greater than 1.7 within them. And as you can see from the Dendrograms we can tell that all the everything below that level this cluster and this cluster they don't have dissimilarity of 1.7 because the similarity is represented by these vertical lines and that's how the customer thresholding works. And the interesting part about pentagrams is you can quickly tell how many clusters you will have at a certain threshold by just looking at how many vertical lines this horizontal threshold actually crosses .

![](../Assets/photos/Hierarchical%20Clustering_21.PNG)

&nbsp;&nbsp;&nbsp;All right so let's have a look at another example. Let's have a look at a example where we put threshold at this level so somewhere just below where we combined. We can have four clusters because it crosses forward lines 1 2 3 4.

![](../Assets/photos/Hierarchical%20Clustering_22.PNG)

&nbsp;&nbsp;&nbsp;Let's say we want to set our dissimilarity threshold very low at point three meaning that we don't want clusters that have any noise within them that have dissimilarity greater then this threshold. So we're not going to allow any clusters like that.

![](../Assets/photos/Hierarchical%20Clustering_23.PNG)

&nbsp;&nbsp;&nbsp;you'll get just by looking at the Dendrograms can tell right away and you can that way find the optimal level for the threshold of the optimal number of clusters that suits your project the best. So but how do you find the actual not just an optimal number of classes that you think is optimal What is the demographic giving us any ideas about the optimal number of clusters. What can we tell from the Dendrograms that might be a good guide for us to select the optimal number of clusters.  
Well there's a great giveaway that the underground contains and that is the vertical distance because it is measuring and dissimilarity. So one of the standard approaches is just to look for the highest vertical distance that you can find on the to. So basically any line that will not cross any horizontal lines. So for instance this line can be considered this like can be considered. This line cannot be considered for that research because it crosses a hypothetical horizontal line so you what you need to do is kind of like every horizontal line you have just imagined extends all the way across to denigrate every single horizontal lung you have and now find the longest line among yours among your existing vertical lines that doesn't cross any horizontal any of these extended horizontal among your existing vertical lines that doesn't cross any horizontal any of these extended horizontal cross this horizontal line that we have coming from this red line between P5 and P-Six.  
And so this is the largest distance and therefore the best or the recommended approach. Again it's not a set in stone approach is a kind of one of the things that you could do is take a threshold that will cross this largest distance across that large distance threshold and then use that threshold to calculate the optimal number of clusters and actually find them. So once we've crossed this largest distance with our threshold doesn't matter we said you can sit here as head low or you can set high as long as it crosses this line then.

![](../Assets/photos/Hierarchical%20Clustering_24.PNG)

![](../Assets/photos/Hierarchical%20Clustering_25.PNG)



# Hierarchical Clustering in Python

![](../Assets/photos/Hierarchical%20Clustering_26.PNG)

![](../Assets/photos/Hierarchical%20Clustering_27.PNG)

![](../Assets/photos/Hierarchical%20Clustering_28.PNG)

![](../Assets/photos/Hierarchical%20Clustering_29.PNG)

![](../Assets/photos/Hierarchical%20Clustering_30.PNG)

![](../Assets/photos/Hierarchical%20Clustering_31.PNG)














































































































































 











