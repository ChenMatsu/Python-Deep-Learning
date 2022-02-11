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

#### Cost Function and Gradient Descent

    1. Cost Function (a.k.a Loss Function) must be an average so it can output a single value

**Quadratic Cost Function**

> $$ C = \frac{1}{2n}\sum\_{x}||y(x) - a^L(x)|| $$

    1. Calculate Difference between Real Value y(x) against Predicted Value a(x)
    2. Punish Large Errors

> $$ C(W, B, S^r, E^r) $$

    1. W => Neural Network's Weights
       - Minimize overall loss => Figure out which w results in the minimum of C(w)
    2. B => Neural Network's Biases
       - W and B are encoded inside a(x)
    3. S => Input of a Single Training Sample
    4. E => Desired Output of the Input Training Sample

---

    1. Derivative is not enough for Neural Network => Gradient Descent(Derivative)
       - Step Size => Learning Rate 
    2. Adaptive Gradient Descent => Start from Large Step, then Smaller Step
       - Adam 

> $$ \triangledown C(w_1, w_2, ..., w_n) $$

**Classification Problem**
    1. Cross Entropy Loss Function => Predict Probability Distribution for Classes

**Binary Cross Entropy**
> $$ -(ylog(p) + (1 - y)log(1-p)) $$ 

**N-Cross Entropy**
> $$ -\sum_{c=1}^My_{(o, c)}log(p_{o, c}) $$

#### BackPropagation
    1. Use gradient to go back through network
```
L-n <=> L-(n-1) <=> ... <=> L-2 <=> L-1 <=> L
```

> $$ Z^L = W^La^{L-1} + b^L $$
> $$ a^L = \sigma(z^L) $$
> $$ c_0(...) = (a^L - y)^2 

> $$ \begin{bmatrix} 1 \\ 2   \end{bmatrix}  \odot \begin{bmatrix} 3 \\ 4   \end{bmatrix} = \begin{bmatrix} 3 \\ 8   \end{bmatrix}  $$

> $$ \delta^L = \triangledown_aC\odot\sigma^{'}(z^L)$$
> $$ \triangledown_aC = (a^L-y) $$
> $$ \delta^l = (w^{l+1})^T\delta^{l+1} \odot\sigma^{'}(z^l)$$