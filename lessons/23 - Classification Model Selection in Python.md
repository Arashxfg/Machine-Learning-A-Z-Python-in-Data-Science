&nbsp;&nbsp;&nbsp; Now we are finally going to get an answer to that ultimate question: How do I know which classification model to choose for a particular problem/dataset?

Well we are all going to answer this question together and to do this, I've prepared for you a folder containing all the classification code templates, and a generic real-world dataset which we will use to answer that question above. Here is the link to the whole Model Selection folder, which we will start from in the next tutorial:

https://drive.google.com/drive/folders/1O8vabaxga3ITjCWfwD79Xnyf8RavYuyk



# Confusion Matrix Accuracy Ratios

&nbsp;&nbsp;&nbsp;Today we're talking about the confusion matrix and different accuracy ratios. So let's imagine that we are building a model that will predict based on images, x-ray images of lungs whether there is cancer or not in the lungs. So we're going to build a matrix here on the left, on the top we have the prediction of our model and it can be negative, no cancer or positive. And then on the left we have the actual state of things.  
There is no cancer, in reality there is no cancer. That person doesn't have cancer or positive, that person does have cancer. 

![](../Assets/photos/Classification%20Model%20Selection%20in%20Python_1.PNG)

&nbsp;&nbsp;&nbsp;So, and once we cross these rows and columns we'll have four different cells. The top left one is called the true negative. And by the way, before we go into this, the positioning of these cells depends on the source that you're looking at. Some places draw confusion matrix one way other places other way so, and I'll link to an article about this at the end of this tutorial.  
So back to our true negative. So the cross between negative and negative is a true negative meaning the model predicted that there is no cancer and in reality that person doesn't have cancer. So in this use case it's a great result for the person that's in question. Now the bottom right is called a true positive. The model predicted that this person has cancer and in reality they also have cancer. And while this is not a great result at all for the person in question in this model at least they know that they have cancer and they can now address it with their doctor and potentially, hopefully get better, get treatment. Now in the top right we have something that's called a false positive. The model predicts that the person has cancer, but in reality they don't have cancer. And this is called a type one error. And this is a problem because even though for the person in question, it's a relief that they don't have cancer imagine the emotional stress and suffering that they will go through when they're told by the model that they have cancer, even though they don't have to go through the stress and suffering because they don't actually have any cancer. So it would be much better if the model told them the correct answer made the correct prediction that they don't have cancer. So it would be much better if the model gave them a true negative.  
And then in the bottom left we have a false negative which is a type two error where the person actually does have cancer in reality, but the model says they don't. And this is a very dangerous type of error because in this use case, the doctors won't even treat the person, won't even recommend any treatment plan because they'll think that the person doesn't have cancer and the cancer can grow and get worse. So both errors are not great and we want to avoid them. So the less errors our models make, the better.

![](../Assets/photos/Classification%20Model%20Selection%20in%20Python_2.PNG)

&nbsp;&nbsp;&nbsp;Now let's populate this matrix with actual figures. Let's say we have hundred patients, out of them our model made some predictions and we have 43 true negatives, 41 true positives, 12 type one errors or false positives and four type two errors or false negatives. From this confusion matrix we can calculate the following rates or ratios. We have the accuracy rate and the error rate. The accuracy rate is the total number of correct predictions, meaning the true negatives plus the two positives divided by the total number of patients in this sample. So we have 84 divided by 100 or 84%. And the error rate is the total number of incorrect predictions, meaning the type one errors plus the type two errors. We have 16 of those divided by the total sample size 100. So we have 16% error rate here. So those are two important rates to be able to calculate. So that's how the confusion matrix works.

![](../Assets/photos/Classification%20Model%20Selection%20in%20Python_3.PNG)





















































































