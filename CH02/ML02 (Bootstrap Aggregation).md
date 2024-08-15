---
tags:
  - MachineLearning
---
Bootstrap Aggregation is also know as *Bagging*, it basically makes the performance of classification and regression models better by decreasing their loss by factor.

###### Bagging for regression

Given dataset D $(X_1,Y,1)......(X_n,Y_n) \sim P$ , basically we approximate the P by resampling, by drawing n points uniformly from the dataset, usually called sampling with replacement.

Saying we had m number of samples stopping at $Y^{(m)}$ saying that our estimator of Y is $EY=y=f(x)$ then it is an unbiased estimator.

If we measured our error by the square distance from our actual value $(Y-y)^2$ then the Risk (Expected value of loss function) $E((Y-y)^2)$ is just a variance $\sigma^2(Y)$

By defining a new random variable Z that's going to be a function of each separate Y as an average of the Ys $Z = \frac{1}{m}{\sum^{m}_{i=1}}Y_i$ so basically the risk of Z will be $E((Z-y)^2) =\sigma^2(z)$ by substituting the z value and using variance properties we get that the risk will be $\frac{1}{m}\sigma^2(Y)$ which means we have decreased the risk by factor m.

but we can't increase the m too much because we have one dataset, but we can approximate P by the empirical distribution $(X_{i}^{(k)}, Y_{i}^{(k)}) \sim Uniform(D)$  and draw from it, instead of drawing from the real samples  

###### Bagging for classification
