
### Cost functions
A cost function determines the "cost" (or penalty) of estimating $\hat{x}$ when the true or correct quantity is really $x$.
This is essentially the cost of the error between the true stimulus value: $x$ and our estimate: $\hat x$.

### Forms of cost functions
Note that the error can be defined in different ways:

$$\begin{eqnarray}
\textrm{Mean Squared Error} &=& (x - \hat{x})^2 \\ 
\textrm{Absolute Error} &=& \big|x - \hat{x}\big| \\ 
\textrm{Zero-One Loss} &=& \begin{cases}
                            0,& \text{if } x = \hat{x} \\
                            1,              & \text{otherwise}
                            \end{cases}
\end{eqnarray}
$$
> In ML, Mean Squared Error is commonly used as the cost function, but with an extra division by 2, which "is just meant to make later partial derivation in gradient descent neater" :
$$
J(\theta) = \frac{1}{2m} \sum ^m (\hat{x_i} - x_i)^2
$$

### Loss for logistic regression
> MSE is not proper because the cost function would not be convex 

- cost function $J(\theta)$  $$
J(\theta) = \frac{1}{m} \sum ^m L (f(x_i), y_i)
$$
with lost function $L(f(x_i), y_i)$
$$
 y_i = 1: L = -log(f(x_i))
$$
$$
 y_i = 0: L = -log(1 - f(x_i))
$$
Combined the above formula together, we get the simplified cost function for logistic regression:
$$
 L = -y_i log(f(x_i)) - (1-y_i)log(1 - f(x_i))
$$
then the cost function with full form (also used in [[Maximum likelihood estimation]] for logistic regression):
$$
J(\theta) = \frac{1}{m} \sum ^m ( -y_i log(f(x_i)) - (1-y_i)log(1 - f(x_i)))
$$
### Cost function with regularization
When you choose regularization, a regularization term will be added to the cost function.
for linear regression:
$$
J(\theta) = \frac{1}{2m} \sum_i ^m (\hat{x_i} - x_i)^2 + \frac{\lambda}{2m} \sum_j^n \theta_j ^ 2 
$$
for logistic regression:
$$
J(\theta) = \frac{1}{m} \sum ^m ( -y_i log(f(x_i)) - (1-y_i)log(1 - f(x_i))) + \frac{\lambda}{2m} \sum_j^n \theta_j ^ 2 
$$
where $j$ represents the $j$th feature. 
Increasing the regularization parameter $\lambda$ ($\lambda$ >0) reduces overfitting by reducing the size of the parameters.  For some parameters that are near zero, this reduces the effect of the associated features.

### Expected loss function
A posterior distribution tells us about the confidence or credibility we assign to different choices. A cost function describes the penalty we incur when choosing an incorrect option. These concepts can be combined into an *expected loss* function. 

Expected loss is defined as:

$$

\mathbb{E} \ [\text{Loss} | \ \hat{x}\ ] = \ \int L\ [\ \hat{x},x\ ] \ \odot p(x|\ \tilde{x}) dx

$$

where $L\ [ \ \hat{x}, x\ ]$ is the loss function, $p(x|\ \tilde{x})$ is the posterior, and $\ \odot$ represents the [Hadamard Product](https://en.wikipedia.org/wiki/Hadamard\_product\_(matrices)) (i.e., elementwise multiplication), and $\ \mathbb{E}\ [\ \text{Loss} | \ \hat{x}\ ]$ is the expected loss.

```
- The posterior's mean minimizes the mean-squared error.
- The posterior's median minimizes the absolute error.
- The posterior's mode minimizes the zero-one loss.
```