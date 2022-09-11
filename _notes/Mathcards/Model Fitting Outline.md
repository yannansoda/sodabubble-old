1. draft & implement model
	- linear/logistic regression: [[Regression]]
	- ...
- 2. estimate parameters of the model
	- optimal parameters minimize the cost function 
		- cost function = averaged loss (+ regularization components) [[Cost Functions]]
		- the minimum of the cost function is found with gradient descent 
		- the loss/cost function can have different forms, e.g. [[Cost Functions#Loss for logistic regression]]
		- [[Maximum likelihood estimation]] is also a form of cost function..?
	- overfitting vs. underfitting <= [[Bias-Variance Tradeoff]]
		- 3 methods to address [[overfitting]] 
			- increase data size 
			- feature selection: decrease # of variables
			- [[regularization]] 
		