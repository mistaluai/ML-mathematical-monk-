---
tags:
  - MachineLearning
---
## Chapter Notes
##### Basic Definition
* Given data (x, y) and modeling f(x) 
* Basically you form a binary tree and minimize the training error in each leaf
* For the *classification* we take the majority vote of the leaf
* For the *regression* we take the average of the Ys
##### Growing a regression tree
there is no way to get the optimal tree but we an use the *greedy algorithm* where we choose the optimal decision of each step, for *regression* we choose the coordinate and split that will decrease the error in a high dimensional space.
$$
min_y \sum_{i:x_{ij} > S}(y-y_i)^2 +\ min_y \sum_{i:x_{ij} <= S}(y-y_i)^2
$$
for the *first* split choose j and s to minimize this equation, for splitting *region R* we try to minimize the following
$$
min_y \sum_{i:x_{ij} > S,x\in R}(y-y_i)^2 +\ min_y \sum_{i:x_{ij} <= S, x\in R}(y-y_i)^2
$$
to make sure that our calculations is within the R region, and this continues recursively.
what's our *base case* to stop ? when **there is one point x in the region** or **only consider splits resulting in regions with specific range of number of points**
after growing your tree you might need to prune it for performance, also you can grow it using randomization techniques instead.
##### Growing a classification tree
here we also use the *greedy algorithm* but here what we are trying to minimize is
$$
E_R = min_y \frac{1}{N_R}\sum_{i:x\in R} I(y_i \neq y), N_R = i:x_i\in R
$$
for the *first split* we choose j and s to minimize 
$$
E_{R_1}(j, s) + E_{{R_1}^{'}}(j, s)\ where\ {R_1}(j, s) = x_i : x_{ij} > s , {R'_1}(j, s) = x_i : x_{ij} <= s
$$
for *splitting Rk* we choose j and s to minimize
$$
E_{R_k}(j, s) + E_{{R_k}^{'}}(j, s)\ where\ {R_k}(j, s) = x_i : x_{ij} > s , {R'_k}(j, s) = x_i : x_{ij} <= s
$$
here our *base case* might be on of the two we mentioned earlier but also we can **stop when Rk contains only one class of points**
#### Generalizations for the trees
##### Impurity measures
* Er which is misclassification rate in region R
* Hr (Entropy) which is the sum over classes times the log of the probability $$H_R =  - \sum_{y\in Y} P_R(y)log(P_R(y)) $$
and the entropy tries to make a region as homogeneous as possible and it can directly replace the Er 
* Gr (Gini index) which is the sum over classes multiplied by one minus the probability $$G_R = \sum_{y\in Y} P_R(y)(1-P_R(y))$$
