### ANN (Artificial Neuron Network)

#### Perceptron Model Theory

    1. Dendrites > Neucleus > Axon <=> Inputs > Fn(X) > Output
    2. X as Tensor(n-dimensional matrix)

```
Ex: y = x1 + x2 => y = x1w1 + x2w2 (With Adjusted Weight) => y is affected by weight **w** <br>
    Note: If **w** is 0, bias **b** is added to the inputs => **Input has to overcome bias** <br>
Ex: y = (x1w1 + b) + (x2w2 + b)
```

**Generalization of Perceptron**

> $$ \hat{y} = \sum\_{i=1}^nx_iw_i + b_i $$
