# What is Cross Validation?

Cross Validation is a technique which involves reserving a particular sample of a data set on which you do not train the model. Later, you test the model on this sample before finalizing the model

Here are the steps involved in cross validation:

1.You reserve a sample data set.

2.Train the model using the remaining part of the data set.

3.Use the reserve sample of the data set test (validation) set. This will help you to know the effectiveness of model performance. It your model delivers a positive result on validation data, go ahead with current model. It rocks!

# What are common methods used for Cross Validation ?

# 1. The Validation set Approach

In this approach, we reserve 50% of dataset for validation and rest 50% for model training. After testing the model performance on validation data set. However, a major disadvantage of this approach is that we train a model on 50% of the data set only, whereas, it may be possible that we are leaving some interesting information about data i.e. higher bias.

# 2. Leave one out cross validation (LOOCV)

In this approach, we reserve only one data-point of the available data set. And, train model on the rest of data set. This process iterates for each data point. It is also known for its advantages and disadvantages. Let’s look at them:

We make use of all data points, hence low bias.

We repeat the cross validation process iterates n times(where n is number of data points) which results in higher execution time

This approach leads to higher variation in testing model effectiveness because we test against one data point. So, our estimation gets highly influenced by the data point. If the data point turns out to be an outlier, it can lead to higher variation.

# 3. k-fold cross validation

From the above two validation methods, we’ve learnt:

1.We should train model on large portion of data set. Else, we’d fail every time to read the underlying trend of data sets. Eventually, resulting in higher bias.

2.We also need a good ratio testing data points. As, we have seen that lower data points can lead to variance error while testing the effectiveness of model.

3.We should iterate on training and testing process multiple times. We should change the train and test data set distribution. This helps to validate the model effectiveness well.

Do we have a method which takes care of all these 3 requirements ?

Yes! That method is known as “k- fold cross validation”. It’s easy to follow and implement. Here are the quick steps:

1.Randomly split your entire dataset into k”folds”.

2.For each k folds in your dataset, build your model on k – 1 folds of the data set. Then, test the model to check the effectiveness for kth fold.

3.Record the error you see on each of the predictions.

4.Repeat this until each of the k folds has served as the test set.

The average of your k recorded errors is called the cross-validation error and will serve as your performance metric for the model.


Now, one of most commonly asked question is, “How to choose right value of k?

Always remember, lower value of K is more biased and hence undesirable. On the other hand, higher value of K is less biased, but can suffer from large variability. It is good to know that, smaller value of k always takes us towards validation set approach, where as higher value of k leads to LOOCV approach. Hence, it is often suggested to use k=10.

# How to measure the model’s bias-variance?

After k-fold cross validation, we’ll get k different model estimation errors (e1, e2 …..ek). In ideal scenario, these error values should add to zero. To return the model’s bias, we take the average of all the errors. Lower the average value, better the model.

Similarly for calculating model’ variance, we take standard deviation of all errors. Lower value of standard deviation suggests our model does not vary a lot with different subset of training data.

We should focus on achieving a balance between bias and variance. This can be done by reducing the variance and controlling bias to an extent. It’ll result in better predictive model. This trade-off usually leads to building less complex predictive models.
