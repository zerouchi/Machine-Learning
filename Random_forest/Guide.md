Random Forest is one of the most popular and commonly used algorithms by Data Scientists. Random forest is a Supervised Machine Learning Algorithm that is used widely in Classification and Regression problems.

 It builds decision trees on different samples and takes their majority vote for classification and average in case of regression.

1. Collection of n no. of base model which are all decision trees
2. Row sampling and feature sampling: we take a sample of rows and column in each base model of decision tree.                         


Classification - Majority voting classifier
Regression - average of prediction of all base models

Bagging and Boosting techniques
![Bagging](https://github.com/zerouchi/Machine-Learning/assets/79967043/886ace11-9b21-42dc-9e29-cc1af4b27a38)

￼
Bagging
Bagging, also known as Bootstrap Aggregation, is the ensemble technique used by random forest
1.  A large data set is taken and divided into n sample where n is equal to the no. of ml model we are using
2. Each model is trained with some sample of data

![Uploading Screenshot 2023-10-12 at 2.29.13 PM.png…]()

￼

 Boosting
It combines weak learners into strong learners by creating sequential models such that the final model has the highest accuracy. For example,  ADA BOOST, XG BOOST.

Boosting is one of the techniques that use the concept of ensemble learning. A boosting algorithm combines multiple simple models (also known as weak learners or base estimators) to generate the final output. It is done by building a model by using weak models in series.





Random forest >> decision tree cause it reduce the risk of overfitting data by reducing the variance in testing dataset

Decision tree == low bias , high variance
Random forest == low bias , low variance

Important Hyperparameters in Random Forest

Hyperparameters are used in random forests to either enhance the performance and predictive power of models or to make the model faster.

1. Hyperparameters to Increase the Predictive Power

n_estimators: Number of trees the algorithm builds before averaging the predictions.

max_features: Maximum number of features random forest considers splitting a node.

mini_sample_leaf: Determines the minimum number of leaves required to split an internal node.

criterion: How to split the node in each tree? (Entropy/Gini impurity/Log Loss)

max_leaf_nodes: Maximum leaf nodes in each tree

2. Hyperparameters to Increase the Speed

n_jobs: it tells the engine how many processors it is allowed to use. If the value is 1, it can use only one processor, but if the value is -1, there is no limit.

random_state: controls randomness of the sample. The model will always produce the same results if it has a definite value of random state and has been given the same hyperparameters and training data.

oob_score: OOB means out of the bag. It is a random forest cross-validation method. In this, one-third of the sample is not used to train the data; instead used to evaluate its performance. These samples are called out-of-bag samples.

