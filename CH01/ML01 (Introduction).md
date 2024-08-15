---
tags:
  - MachineLearning
---
## Chapter Notes
#### Defintion (1.1)
Algorithms for inferring unknowns from known
#### Classes of ML Problems
##### Supervised Learning (1.2)
Given data (X1, Y1), you want to choose function f(x) = y  that generalizes well.
* Classification: when Ys are finite
* Regression: when Y are in R or multidimensional space
##### Unsupervised Learning (1.3)
Given data X, you want to find patterns in the data
* Clustering: finding clusters and groups in the data
* Density Estimation: you assume that the data come from a probability distribution and you want to estimate their densities 
* Dimensionality Reduction: finding lower dimensional space to represent the data
##### Variations on supervised and unsupervised learnings (1.4)
* Semi-supervised: when some of the Ys are missing in the data
* Active Learning
* Decision Theory
* Reinforcement Learning 
##### Generative vs Discriminative models (1.5)
* Discriminative Approach: it is modeling the P(y|x)
* Generative Approach: modeling both P(x,y) = P(x|y) * P(y)
