---
tags:
  - MachineLearning
---
##### Algorithm
We will combine the [[ML02 (Bootstrap Aggregation)]] and the method of the random subspaces to construct our [[ML02 (Decision Trees - CART)]] to obtain our random forests.

having $D = (x_1,y_1),....,(x_n,y_n)$ as our dataset
and B as number of trees, m as number of features
for i = 1, ....., B:
choose bootstrap sample $D_i$ from $D$ and then construct a tree $T_{i}$ using $D$ where at each node we choose random subset of m features and we only consider splitting on these features.

After all this we just do our normal aggregation technique over the B trees.

one of the problems that each single tree has high variance, but after aggregation on B trees you manage to reduce the variance of the overall final estimator