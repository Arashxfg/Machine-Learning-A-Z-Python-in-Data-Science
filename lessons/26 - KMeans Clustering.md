# What is Clustering Supervised vs Unsupervised Learning

&nbsp;&nbsp;&nbsp;Clustering can be defined as grouping unlabeled data. What does that mean?  
Well, so far in this course, we've been working with supervised learning types of algorithms, which include regression and classification. And the way supervised learning algorithms work is that you already have some training data and an answer and answers in that training data that you supply to the model. So, for example, in the case of classification, you have input data, which could be images of apples and you have annotations explaining these are apples or labels for these apples. And then you supply that to the model. You ask the model to learn from these, from this data with answers. And then you can supply a new image and ask, "What is this?" And it will provide the answer saying that this is an apple.  
&nbsp;&nbsp;&nbsp;Now, unsupervised learning is different. Here, we don't have answers, and the model has to think for itself. So, for example, we might have input data for these images without any labels, supply them to the model and ask them to group these fruits into different categories, even though we don't know the category, we don't supply the categories. So the machine has no understanding which is an apple, which is a banana, and so on. It can just see that there are certain similarities in the data, certain differences in the data, and from that it can make conclusions and create its own groups. And this is all the while it doesn't understand what it is looking at, doesn't understand the term apple or banana. So, that is the difference between supervised and unsupervised learning. In a nutshell, in supervised learning, you give the model an opportunity to train where it has the answers. In unsupervised learning, you don't have the answers to supply to the model.

![](../Assets/photos/KMeans%20Clustering_1.PNG)

&nbsp;&nbsp;&nbsp;So, let's look at an example of this in a business sense. Here we have an X Y-axis with annual income of your customers, of a store, for example and the spending score. So how often do they spend? How much do they buy? All their spending patterns. All of this is combined already into a spending score. So when you plot your customers, it might look like this and you don't have any preexisting categories. You don't have any preexisting classes or groups of customers to group them into. You want to create those groups. So that's where you would apply clustering. And by applying clustering, it would show you that these are probably likely groups of customers. And then you could go into this further, dig deeper and understand why these groups might be emerging, what this might be in a business sense, in a spending sense, in a customer sense, understand how to best service these customers, to what kind of promotions to send to one group versus the other, what kind of reminders or what kind of offers to create for these different customers and how to best use this information in your business. So, that's clustering. As you can see, it's very different to what we've discussed before.

![](../Assets/photos/KMeans%20Clustering_2.PNG)



# KMeans Clustering Intuition

&nbsp;&nbsp;&nbsp;So here we have a scatter plot of our data points, and we want K-Means Clustering to create clusters. So we don't have any classes or categories in advance, we don't have any training data, we just have this data, and we want to create the clusters.  
Well, the first thing is, well, first step is that you need to decide how many clusters you want. We'll talk about how to make this decision in next tutorial. For now, let's say, we decided on two clusters.

![](../Assets/photos/KMeans%20Clustering_3.PNG)

&nbsp;&nbsp;&nbsp;Then, for each cluster, you need to place a randomly placed a centroid on this scatter plot, wherever you like, it doesn't have to be one of the existing points. Now, what happens next is K-Means will assign each of the data points to the closest centroid.

![](../Assets/photos/KMeans%20Clustering_4.PNG)

&nbsp;&nbsp;&nbsp;In this case, it's easiest done by joining this equidistant line. Anything above is blue, is assigned to the blue centroid, anything below is assigned to the red centroid. 

![](../Assets/photos/KMeans%20Clustering_5.PNG)

&nbsp;&nbsp;&nbsp;Now, the next step is quite interesting. We need to calculate the centre of mass, or center of gravity for each of the clusters, the preliminary clusters that we've identified. Of course, the centroid is not included in this calculation. So for example, for the blue cluster, we need to take all the X coordinates and take the average, and take all the Y coordinates, take the average. That'll give us the place, the position of the center of mass.

![](../Assets/photos/KMeans%20Clustering_6.PNG)

&nbsp;&nbsp;&nbsp;And then, we move the centroid to those positions. Once they've moved, we repeat the process, we reassign data points to the closest centroid. So again, equidistant line, change the colors of the data points and assign. And again, we calculate the center of gravity, center of mass, move the centroids, do the process again. Reassign, calculate the center of mass, move the centroids, do the process again. Reassign, calculate the center of mass, move the centroids, do the process again. And until we get into situation where doing the process again doesn't change anything, like in this state where we've drawn the equidistant line and already all the blue points are above and all the red points are below. And so that means we've come to the end of the K-Means Clustering step by step process. And those are our final centroids.

![](../Assets/photos/KMeans%20Clustering_7.PNG)  
![](../Assets/photos/KMeans%20Clustering_8.PNG)  
![](../Assets/photos/KMeans%20Clustering_9.PNG)  
![](../Assets/photos/KMeans%20Clustering_10.PNG)  
![](../Assets/photos/KMeans%20Clustering_11.PNG)




# The Elbow Method

&nbsp;&nbsp;&nbsp;So here, we have our data points. And as you can see, they're in two dimensions. I just wanted to say, before we continue, that k-means clustering doesn't necessarily have to work in just two dimensions. It can work in many dimensions, but for simplicity's sake, we're looking at two-dimensional examples because they're easier to illustrate. So our data points are here, and we already know how k-means clustering works. The question is, how do we decide how many clusters to select in that very first step? Because it's up to us.  
Well, the elbow method is one of the approaches to help you make this decision. There are other methods as well, and moreover, sometimes, you might already know in advance from your domain knowledge about the problem how many clusters there should be or how many classes you would like to have. But if that information's not available, then the elbow method is a pretty good way of finding the optimal number of clusters.

![](../Assets/photos/KMeans%20Clustering_12.PNG)

&nbsp;&nbsp;&nbsp;So the elbow method requires us to look at this equation for the Within Cluster Sum of Squares, or the WCSS. Don't worry if it looks a bit complex at first. It's actually very simple. It basically looks at the distance between each point and the centroid of its cluster, and you square that distance.

![](../Assets/photos/KMeans%20Clustering_13.PNG)

&nbsp;&nbsp;&nbsp;So let's have a look at this in an example. If those are our data points and we have one cluster, then we just need to measure the distance between each point and that centroid and square it and add them up. If we have two clusters, then we need to do that for the red points on their own, calculate the distance between each point and centroid, square them, add them up, and then do the same for the blue points, and then add them up again. And same thing for three clusters. So, two things to point out here. First one is, as you can see, to calculate all these different within cluster sum of squares for the different options, we actually need the clusters to already exist. So every time, we have to first run the k-means clustering algorithm, and then we calculate the WCSS. So it's kind of a bit backwards. We don't first do the elbow method to find the optimal number of clusters and then do k-means. We do k-means many times, find the WCSS for every single setup, whether it's one cluster, 2, 3, 4, 5, and so on, and then we will be able to apply the elbow method, which is coming up on the next slide. And the second thing to note is that the more clusters we have, the smaller WCSS becomes. You can even see it visually. So here, the distances are high, and especially when you square them, the WCSS will be quite large. Then here, the distances are smaller, and so the WCSS drops. And here, again, the distances become smaller and smaller. And so we can continue increasing the number of clusters until we get to the maximum number of clusters, which equals the number of data points that we have. And then WCSS will be actually exactly zero because each data point is its own centroid and the distance is zero.

![](../Assets/photos/KMeans%20Clustering_14.PNG)  
![](../Assets/photos/KMeans%20Clustering_15.PNG)  
![](../Assets/photos/KMeans%20Clustering_16.PNG)  

&nbsp;&nbsp;&nbsp;And so, the chart that we can build from this looks like this.  
This is the WCSS and, on the y-axis, and on the x-axis, we have the number of clusters. As you can see, it drops off all the way down to zero, as we just discussed. And the elbow method is very simple. It's actually a visual method when you look at this chart and you look for where is the kink in this chart, where is the elbow. There it is. And so that is your optimal number of clusters, basically when the WCSS stops dropping as rapidly. Of course, it's a judgment call, and sometimes, it can be unclear. There might be two potential candidates or more candidates for the optimal number of clusters, but then, in those cases, it's something that you need to decide as the data scientist.

![](../Assets/photos/KMeans%20Clustering_17.PNG)  




# KMeans++

&nbsp;&nbsp;&nbsp;So here we have our dataset and let’s say we want to apply K-Means. For the sake of discussion, assume the centroids are initialized as follows. Once we apply K-Means and all the steps complete, we end up with these three clusters. So this is straightforward. But now, let’s say we have the same dataset and apply K-Means again, but because centroids are randomly initialized, suppose they start as shown here. After running K-Means, we get a different set of three clusters. And this is not good. The results differ between these two runs of the same K-Means machine learning model. The difference arises solely from the centroid initialization. We changed nothing else. This is called the random initialization trap. Why is this problematic? Two main reasons:  
Determinism: When running a machine learning model (like clustering), you want consistent, reproducible results. The outcome shouldn’t vary based on random initialization. If the model provides business insights (e.g., customer segmentation), those insights should not depend on randomness.  
Suboptimal Clusters: Intuitively, the dataset might have clear groupings, but poor initialization can lead to worse clusters (as shown in the lower example). This is why K-Means++ was developed—to combat this trap.

![](../Assets/photos/KMeans%20Clustering_18.PNG)  

&nbsp;&nbsp;&nbsp;It initializes centroids more strategically:  
Step 1: Randomly select the first centroid.
Step 2: For each data point, calculate its distance to the nearest existing centroid.
Step 3: Select the next centroid via weighted probability (based on squared distances).
Repeat Steps 2-3 until all centroids are chosen.

![](../Assets/photos/KMeans%20Clustering_19.PNG)  

&nbsp;&nbsp;&nbsp;Visual Example:  
First centroid (random):
![Point A].
Measure distances, square them, and weight selection.
Next centroid likely chosen from farthest points (e.g., ![Point B]).
Repeat to initialize all centroids.  

This reduces the risk of poor initialization and ensures clusters align better with natural groupings.  
Key Takeaway:  
K-Means++ doesn’t eliminate randomness but minimizes its impact. It leads to more consistent and higher-quality clusters.

Why Use K-Means++?  
More deterministic insights. Avoids suboptimal clusters caused by unlucky random starts.  
In practice, K-Means++ is the default in most libraries (e.g., scikit-learn) due to these advantages.  
Recap:  
K-Means++ improves initialization by prioritizing distant points, leading to better and more stable clustering results.

![](../Assets/photos/KMeans%20Clustering_20.PNG)  
![](../Assets/photos/KMeans%20Clustering_21.PNG)  
![](../Assets/photos/KMeans%20Clustering_22.PNG)  



# KMeans Clustering in Python 

![](../Assets/photos/KMeans%20Clustering_23.PNG)  
![](../Assets/photos/KMeans%20Clustering_24.PNG)  
![](../Assets/photos/KMeans%20Clustering_25.PNG)  
![](../Assets/photos/KMeans%20Clustering_26.PNG)  
![](../Assets/photos/KMeans%20Clustering_27.PNG)  
![](../Assets/photos/KMeans%20Clustering_28.PNG)  
















































 





















 








 























































































































































