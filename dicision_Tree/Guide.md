Decision trees are a popular machine learning algorithm that can be used for both regression and classification tasks. They are easy to understand, interpret, and implement, making them an ideal choice for beginners in the field of machine learning. 
Pruning

Before learning more about decision trees let’s get familiar with some of the terminologies:


* Root Node: The initial node at the beginning of a decision tree, where the entire population or dataset starts dividing based on various features or conditions.
* Decision Nodes: Nodes resulting from the splitting of root nodes are known as decision nodes. These nodes represent intermediate decisions or conditions within the tree.
* Leaf Nodes: Nodes where further splitting is not possible, often indicating the final classification or outcome. Leaf nodes are also referred to as terminal nodes.
* Sub-Tree: Similar to a subsection of a graph being called a sub-graph, a sub-section of a decision tree is referred to as a sub-tree. It represents a specific portion of the decision tree.
* Pruning: The process of removing or cutting down specific nodes in a decision tree to prevent overfitting and simplify the model.
* Branch / Sub-Tree: A subsection of the entire decision tree is referred to as a branch or sub-tree. It represents a specific path of decisions and outcomes within the tree.
* Parent and Child Node: In a decision tree, a node that is divided into sub-nodes is known as a parent node, and the sub-nodes emerging from it are referred to as child nodes. The parent node represents a decision or condition, while the child nodes represent the potential outcomes or further decisions based on that condition.

* ![ROOT Node](https://github.com/zerouchi/Machine-Learning/assets/79967043/23780288-5ef0-4450-a499-c8f1d3d27d18)


￼



A decision tree is a non-parametric supervised learning algorithm for classification and regression tasks. It has a hierarchical tree structure consisting of a root node, branches, internal nodes, and leaf nodes. Decision trees are used for classification and regression tasks, providing easy-to-understand models.

* When we remove sub-nodes of a decision node, this process is called pruning. It is the opposite process of splitting

The Decision Tree algorithm intuition is as follows:-
1. For each attribute in the dataset, the Decision-Tree algorithm forms a node. The most important attribute is placed at the root node.
2. For evaluating the task in hand, we start at the root node and we work our way down the tree by following the corresponding node that meets our condition or decision.
3. This process continues until a leaf node is reached. It contains the prediction or the outcome of the Decision Tree.

The primary challenge in the Decision Tree implementation is to identify the attributes which we consider as the root node and each level. This process is known as the attributes selection. There are different attributes selection measure to identify the attribute which can be considered as the root node at each level.
There are 2 popular attribute selection measures. They are as follows:-
* Information gain
* By using information gain as a criterion, we try to estimate the information contained by each attribute. To understand the concept of Information Gain, we need to know another concept called Entropy.By using information gain as a criterion, we try to estimate the information contained by each attribute. To understand the concept of Information Gain, we need to know another concept called Entropy.

Entropy is represented by the following formula:-



linkcode
![entropy-formula](https://github.com/zerouchi/Machine-Learning/assets/79967043/898f337c-24d4-4146-8615-d7ddb2c582c6)

￼
In a decision tree, the output is mostly “yes” or “no”
The formula for Entropy is shown below:
![706025](https://github.com/zerouchi/Machine-Learning/assets/79967043/b223a1c5-df75-40e9-bfe3-cbbfd191f716)

￼
Here,
* p+ is the probability of positive class
* p– is the probability of negative class
* S is the subset of the training example
  
                          0<E(S)<1
Always remember that the higher the Entropy, the lower will be the purity and the higher will be the impurity.

using the entropy we are getting the impurity of a particular node, we don’t know if the parent entropy or the entropy of a particular node has decreased or not.
For this, we bring a new metric called “Information gain” which tells us how much the parent entropy has decreased after splitting it with some feature.

Information gain measures the reduction of uncertainty given some feature and it is also a deciding factor for which attribute should be selected as a decision node or root node.

￼
It is just entropy of the full dataset – entropy of the dataset given some feature.



* Gini index
Gini index
￼![410199](https://github.com/zerouchi/Machine-Learning/assets/79967043/66c622f8-9a8f-4022-ba65-26672dab5b02)

Hyper parameter tuning
Certainly, we can categorize the hyperparameters of decision trees into two groups based on their impact on model performance and training speed:

Improving Prediction Power (Model Performance):
* Criterion:
    * Choosing an appropriate criterion (e.g., "gini" or "entropy") can affect how well the model differentiates between classes.
* Splitting Strategy:
    * The choice of splitting strategy ("best" or "random") impacts the quality of the splits made during tree construction.
* Maximum Depth:
    * Increasing the maximum depth allows the model to capture more complex patterns in the data, potentially improving prediction power.
* Minimum Samples per Leaf:
    * Increasing this parameter can help prevent overfitting by ensuring that leaf nodes contain a minimum number of samples.
* Minimum Samples per Split:
    * Similar to min_samples_leaf, this parameter helps prevent the creation of very small nodes that may capture noise.
* Maximum Features:
    * Controlling the number of features considered for each split can impact the model's ability to generalize.
* Class Weight:
    * Adjusting class weights is important for handling class imbalance and improving the prediction power for imbalanced datasets.
* Minimum Impurity Decrease:
    * Setting a threshold for impurity decrease ensures that splits only occur when they significantly improve the model's performance.
* Pruning Parameters:
    * ccp_alpha (Complexity Parameter) is used for pruning the tree to prevent overfitting.

Improving Speed (Training Time):
* Presorting:
    * The presort parameter determines whether data is presorted for faster splitting. However, it's been deprecated in recent versions of scikit-learn.
* Random State:
    * Setting a random seed (random_state) can control the randomness during tree construction but doesn't directly impact model performance.
* Warm Start:
    * Enabling warm_start can speed up training by reusing the existing tree and further training it on new data.
* Maximum Leaf Nodes:
    * Controlling the number of leaf nodes can affect the complexity of the tree and, indirectly, the training time.
* Minimum Weight Fraction Leaf:
    * This parameter sets a minimum weighted fraction of samples required for a leaf node, affecting the tree's size and training time.
* Sibling Leaves:
    * min_impurity_split determines the minimum impurity required for a split in a sibling, influencing the tree structure.

There are many ways to tackle this problem through hyperparameter tuning. We can set the maximum depth of our decision tree using the max_depth parameter. The more the value of max_depth, the more complex your tree will be. The training error will off-course decrease if we increase the max_depth value but when our test data comes into the picture, we will get a very bad accuracy. Hence you need a value that will not overfit as well as underfit our data and for this, you can use GridSearchCV.

Pruning
Pruning is another method that can help us avoid overfitting. It helps in improving the performance of the tree by cutting the nodes or sub-nodes which are not significant. Additionally, it removes the branches which have very low importance.
There are mainly 2 ways for pruning:
* Pre-pruning – we can stop growing the tree earlier, which means we can prune/remove/cut a node if it has low importance while growing the tree.
* Post-pruning – once our tree is built to its depth, we can start pruning the nodes based on their significance.

