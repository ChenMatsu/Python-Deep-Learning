### PyTorch Basics

#### Tensor Basics
- torch.from_numpy() / torch.as_tensor() => Address Reference
- torch.tensor() => Value Reference
  - tensor() => Int Type
  - Tensor() => Float Type
  - empty() => Create Tensor 
  - zero() => Zero Tensor
  - ones() => One's Tensor
  - arange(start, end, step) 
  - linspace(start, end, elements)
  - type() => Convert dtype
  - rand(row, col)
  - randn(row, col)
  - randint(low, high, size)
  - rand_like() => Generate certain shape tensor
  - manual_seed() => Generate random seed
  - view() => View in certain shape => -1 turn to infer
  - add()
    - _: Reassign
  - mul()
  - mm() / a @  b=> Matrix Multiplication
  - norm()
  - numel()
    
