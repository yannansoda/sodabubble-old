
# Bias-Variance trade-off
-> Inderfitting - [[Overfitting]] issues

# Bias & Variance in ML
### Regularization influences bias-variance trade-off
check [[Cost Functions#Cost function with regularization]] and [[Regularization]]

![](/assets/images/bias-variance-1.png)


![](/assets/images/bias-variance-4.png)
### learning curves
![](/assets/images/bias-variance-2.png)
![](/assets/images/bias-variance-3.png)
increasing training set size can...
- lower cross validation error, if a learning algorithm suffers from high variance
- not help anything, if a learning algorithm suffers from high bias

### How to fix
- High bias
	- try getting additional features
	- try adding polynomial features
	- try decreasing [[regularization]] parameter $\lambda$
- High variance
	- get more training examples
	- try smaller sets of features
	- try increasing [[regularization]] parameter $\lambda$
