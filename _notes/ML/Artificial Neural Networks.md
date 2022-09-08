[[_Machine Learning]]
# Basic working mechanism
![[Pasted image 20220403112540.png]]
# How it works
1. Randomly initialise the weights to small numbers close to 0 (but not 0).
2. Input the first observation of your dataset in the input layer, each feature in one input node.
3. **Forward-propagation**: from left to light, the neurons are activated in a way that the impact of each neuron's activation is limited by the weights. Propagate the activations until getting the predicted result y.
4. Compare the predicted result to the actual result. Measure the generated error.
5. **Back-propagation**: from right to left, the error is propagated. Update the weights according to how much they are responsible for the error. The learning rate decides by now much we update the weights.
6. Repeat Steps 1 to 5 and update the weights after each observation (**Reinforcement Learning**); OR: Repeat Steps 1 to 5 but update the weights only after a batch of observations (**Batch Learning**).
7. When the whole training set passed through the ANN, that makes an epoch. Redo more epochs. 

# Activation functions
### There are multiple forms
- sigmoid 
$$
\phi(x) = \frac{1}{1 + e ^ x}
$$
- Softmax
$$
 \text{Softmax}(x_{i}) = \frac{\exp(x_i)}{\sum_j \exp(x_j)}
$$
- rectifier (ReLU)
$$
\phi(x) = max(x, 0)
$$
- Linear activation function
$$
\phi(x) = ax + b
$$
- Hyperbolic Tangent (tanh)
$$
\phi(x) = \frac{1 - e^{-2x}}{1+e^{-2x}}
$$
> Different forms can be combined, e.g. using rectifier in the hidden layer and then sigmoid in output layer

### Which to choose depends on your problems:
- for the output layer:
	- binary classification -> sigmoid
	- multiclass classification -> Softmax
	- regression -> linear activation & ReLU
- for hidden layers: 
	- use default function (usually ReLU, because it is faster)
	- do not use linear activation

# Gradient Descent
-- to minimize cost function
## batch gradient descent vs. stochastic gradient descent
- different purposes: stochastic ones can avoid local minimum 
- different ways to update weights
![[Pasted image 20220403112012.png]]
