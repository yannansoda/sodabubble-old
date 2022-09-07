# Tools to assess goodness of fit
## Maximum Likelihood
see [[Maximum likelihood estimation]]

## Akaike Information Criterion (AIC)
$$
AIC = 2k - 2ln(L)
$$
 where $k$ is the number of estimated parameters in the model and $L$ is the maximum value of the likelihood function for the model.
 
 Given a set of candidate models for the data, the preferred model is the one with the minimum AIC value. 
 Thus, AIC rewards goodness of fit (as assessed by the likelihood function), but it also includes a penalty that is an increasing function of the number of estimated parameters. The penalty discourages overfitting, which is desired because increasing the number of parameters in the model almost always improves the goodness of the fit.


# However, overfitting can occur...
There are common tools to address overfitting: 
### Collect more data (or training examples)
### Feature selection: select features to include/exclude
### Regularization == => reduce overfitting during estimation
Regularization lets you keep all of your features, but they just prevents the features from having an overly large effect, which is what sometimes can cause overfitting. 
- In ML framework: [[Data Preprocessing#Regularization]] 
- In Bayesian framework
	- A regularizing prior is a "skeptical" prior, which means it slows down the rate of the model in learning from the data.
	- Multilevel models can be regarded as adaptive regularization, where the model itself tries to learn how skeptical it should be.
	- It is a Bayesian method. It is the same device that non-Bayesian methods refer to as “penalized likelihood.”
## Estimates of out-of-sample accuracy => estimate the degree of overfitting
- **Cross-validation** => test the model’s predictive accuracy on another sample
	- It divides the sample in a number of chunks, called “folds.” The model is asked to predict each fold, after training on all the others.
	- It is extremely common to use the maximum number of folds, resulting in leaving out one unique observation in each fold. This is called **leave-one-out cross-validation.**
	- An improved cross-validation: **Pareto-smoothed importance sampling cross-validation (PSIS)**
- **Information criteria** => construct a theoretical estimate of the relative out-of-sample Kullback-Leibler Divergence ([[Infomation theory and Entropy#^aa57f9]])
	- [[#Akaike Information Criterion AIC]]
	- Deviance Information Criterion (DIC): a more general version of AIC
	- Widely Applicable Information Criterion (WAIC): even more general than AIC and DIC
	- WAIC PSIS
> BUT! Do not use predictive criteria to choose a causal estimate, because predictive criteria actually prefer confounds in [[Confounds in causal models#^b7b0a6]].

# Bia-Variance Trade-Off: underfitting/overfitting dichotomy
