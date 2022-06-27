# Fake-News-Detection

######    #######

### Why we use fit_transform() on training data but transform() on the test data?

#### fit_transform()

fit_transform() is used on the training data so that we can scale the training data and also learn the scaling
parameters of that data. Here, the model built by us will learn the mean and variance of the features of the training
set. These learned parameters are then used to scale our test data.

So what actually is happening here! 🤔

The fit method is calculating the mean and variance of each of the features present in our data. The transform method is
transforming all the features using the respective mean and variance.

Now, we want scaling to be applied to our test data too and at the same time do not want to be biased with our model. We
want our test data to be a completely new and a surprise set for our model. The transform method helps us in this case.

#### transform()

Using the transform method we can use the same mean and variance as it is calculated from our training data to transform
our test data. Thus, the parameters learned by our model using the training data will help us to transform our test
data.

#### Here is the simple logic behind it!

If we will use the fit method on our test data too, we will compute a new mean and variance that is a new scale for each
feature and will let our model learn about our test data too. Thus, what we want to keep as a surprise is no longer
unknown to our model and we will not get a good estimate of how our model is performing on the test (unseen) data which
is the ultimate goal of building a model using machine learning algorithm.

### Passive Aggressive Classifiers

Passive-Aggressive algorithms are generally used for large-scale learning. It is one of the few ___online-learning
algorithms___. In online machine learning algorithms, the input data comes in sequential order and the machine learning
model is updated step-by-step, as opposed to batch learning, where the entire training dataset is used at once. This is
very useful in situations where there is a huge amount of data and it is computationally infeasible to train the entire
dataset because of the sheer size of the data. We can simply say that an online-learning algorithm will get a training
example, update the classifier, and then throw away the example.
