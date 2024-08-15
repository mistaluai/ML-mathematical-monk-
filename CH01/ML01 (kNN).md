---
tags:
  - MachineLearning
---

##### kNN (1.6)
Simply classifying the class of the point depending on the *majority vote of the k nearest neighbors* to it.
The kNN has probabilistic formulation as follows:
at fixed k and data (x)
$$ P(y|x,D) = fraction\ of\ pts\ x_i\ in\ N_k(x)\ s.t.\ y_i = y $$
$$ y = argmax(P(y|x,D))$$
## External notes
[https://www.elastic.co/what-is/knn]
#### Summary

The kNN is works on **assumption** *the similar points are near each other*, at the classification the algorithm tends to use the majority vote while at regression it uses the average of the k nearest values of the point.

This algorithm relies heavily on memory, due to inference happening at the query phase not training one.

For bi-class problems we use majority voting while for mutli-class ones we use plurality voting.

##### kNN Distance Metrics
* Euclidean: measures straight line between query and other points
* Manhattan: measures the absolute value between two points
* Hamming: works more with boolean and strings, it measures the distance between two equal length strings, useful for error detection and correction codes
##### Choosing k values
Determining the best k value should include some experiment to find the lowest error possible.

* Low values makes prediction unstable: it will make the model fit too closely to the original data (*overfitting*)
* High values result in noise: accuracy will go higher but it will lead to lower complexity which gives *underfitting*

it advised to use odd number of neighbors, to avoid ties (50/50)s 

Start with sqrt(N) as an initial k value
