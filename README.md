### ANN (Artificial Neuron Network)

#### Perceptron Model Theory

    1. Dendrites > Neucleus > Axon <=> Inputs > Fn(X) > Output
    2. X as Tensor(n-dimensional matrix)

```
Ex: y = x1 + x2 => y = x1w1 + x2w2 (With Adjusted Weight) => y is affected by weight w
    Note: If w is 0, bias b is added to the inputs => Input has to overcome bias
Ex: y = (x1w1 + b) + (x2w2 + b)
```

**Generalization of Perceptron**

> $$ \hat{y} = \sum_{i=1}^nx_iw_i + b_i $$

#### Neural Network

    1. Connect Layers of Perceptrons => Multi-Layer Perceptron Model**
    2. Perceptron Output as Another Perceptron Input
    3. Input Layer => Hidden Layer => Output Layer(One or more Neuron)
    4. Nerual Network can approximate any function

> Universal Approximation Theorem: https://en.wikipedia.org/wiki/Universal_approximation_theorem <br>
> Foundation of UAT: https://en.wikipedia.org/wiki/Hilbert%27s_thirteenth_problem

#### Activation Function

> $$ x*w + b, z = x*w + b $$

    1. Pass z through activation function to limit its value
       - Step Function (Classification) => Too Strong => 0 or 1
       - Sigmoid Function => Smooth [0, 1]
       - Hyperbolic Tangent => [-1, 1]
       - Rectified Linear Unit(ReLU) => max(0, z) => Good for vanishing gradient

**Sigmoid Function**

> $$ f(z) = \frac{1}{1 + e^{(-z)}}$$
**Hyperbolic Tangent**
> $$ cosh x = \frac{e^{(x)} + e^{(-x)}}{2} $$
> $$ sinh x = \frac{e^{(x)} - e^{(-x)}}{2} $$
> $$ tanh x = \frac{sinh x}{cosh x} $$

> Activation Function: https://en.wikipedia.org/wiki/Activation_function

#### Multi-Class Classification

    1. Mutually Exclusive Class => One Class Per Data
       - Photo with only grayscale or full-color
       - Note: Use One-Hot Encoding => ["Red", "Blue", "Green"] => Dummy Matrix
       - Softmax Function
    2. Non-Exclusive Class => Multiple Class Per Data
       - Photo with various tags

**Softmax Function**

- Calculate probabilities distribution over K different events
- Sum of all probabilites is 1 
> $$ \sigma(z)_i = \frac{e^{z*i}}{\sum_{i=1}^Ke^{z_i} } $$
