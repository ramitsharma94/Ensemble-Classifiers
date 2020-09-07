# Ensemble-Classifiers

All about Ensemble Classifier

The word Ensemble basically means a group of items viewed as a whole rather than individually. And this simple technique is applied in Data Science where we aggregate the predictions of a group of predictors (classifiers) and often through this approach we get predictions better than the best individual classifier. 
 But while implementing Ensemble Classifier it is very important to keep in mind that ensemble methods work best when the Classifiers are as independent of one another as possible as this will increase the chance of making very different types of errors, hence, improving the ensembles accuracy. 

Some of the Ensemble techniques are: 
1.	Voting Classifiers 
2.	Bagging and Pasting 
3.	Boosting 
4.	Stacking 
Let’s go through all these techniques one by one. 
Voting Classifiers
Voting classifiers, as the name implies, is a technique where the result of different classifiers are aggregated and predictions are made based on the class that get most votes. There are two types of Voting classifiers:
a.	Hard Voting Classifier: The hard-voting classifier is a type where the voting is applied to the predicted class labels. Such that a class is predicted in favor of whoever has the highest number of votes. For Ex. Assume that there are three classifiers that classify a training sample:
•	Classifier 1 -> Class A
•	Classifier 2 -> Class B
•	Classifier 3 -> Class A
Via majority vote, we would classify the samples as “Class A”
b.	Soft Voting Classifier: However in soft voting, the predicted class is the one with the highest class probability, averaged over all the individual classifiers. For Ex. Assume there are three classifiers:
•	Classifier 1 -> {0.40, 0.60)
•	Classifier 2 -> (0.47, 0.32)
•	Classifier 3 -> (0.40, 0.53)
So, the probability for class A is (0.40 + 0.47 + 0.40)/3 which is 0.423 and the probability for class B is (0.60 + 0.32 + 0.53)/3 which is 0.4833. Based on the highest probability averaged by each classifier the predicted class is B.

Bagging and Pasting
 Bagging and Pasting is one of the other ensembling technique. But here, rather than aggregating predictions from various models, we will aggregate the predictions of a single machine learning model trained over various random subsets of data.
So, Bagging also called as Bootstrapping is a simple method of random sampling with replacement. Meaning that the instances can appear in the subset twice or more. 
Whereas, Pasting is a technique of random sampling without replacement such that the instance cannot appear more than once in the same subset. 
Bagging usually gives much better results than Pasting since it introduces a bit more diversity in the subsets that predictor is trained on but it is always better to experiment with both.
Boosting 
Boosting is another ensemble technique which combines several weak classifier into a strong classifier. The main idea behind boosting is to use the same predictor sequentially, such that with each sequence it tries to correct the mistakes of its predecessor. There are two main types of Boosting Algorithms: 
a.	AdaBoost: The algorithm of AdaBoost is as follows: 
•	Train a base classifier and make predictions of training set 
•	Compare the predictions with true labels and based on that increase the weights of misclassified instances 
•	Train a new classifier with updated weights and again check the predictions and update the weights of misclassified instances and so on. 
b.	Gradient Boosting: The Gradient Boosting algorithm is similar to the AdaBoost algorithm, the only difference is that in gradient boosting, the predictor tries to fit the residual error made by the predecessor, instead of tweaking instance weights.

Stacking
Stacking is the last part of the ensembling technique. Stacking is based on a simple idea of training a model to perform aggregation instead of using functions like hard-voting to aggregate the predictions of all classifiers in an ensemble.
The model in stacking is also called as Blender. And the approach is to first split the dataset into training set and holdout set. The first subset is used to train predictors in the first layer. After that the first layers predictors are used to make predictions on the second (held out set) to check the accuracy. Once that is done, the first layers prediction will now become the input for the blender. 
It is also possible to train several different blenders in order to maximize the accuracy of the overall model.
