---
layout: post
title: "Deep Learning With PyTorch, Part 2: Fundamentals"
---
<head>
  <link rel="stylesheet" href="../assets/css/blogstyles.css">
</head>

# Deep Learning With PyTorch

## Part 2: Fundamentals

#### What Is A Tensor?

Mathematically, a [tensor](https://en.wikipedia.org/wiki/Tensor) is an algebraic object that describes the relationship between its elements as it pertains to a vector space. That sounds like a lot, but it's actualy not so complicated. You can think of a tensor as an extension of a multidimensional array where each element within the array is a vector. 

If that's confusing and abstract, don't worry. We can leave the exact definition of a tensor to the mathematicians. The point is that tensors are similar to multidimensional arrays, but have a few extra perks that make them ideal for representing deep neural networks.

#### Tensors in PyTorch

A PyTorch tensor is very similar to NumPy array. They can hold similar data structures and even share the same syntax for indexing. However, PyTorch tensors come with a couple of crucial bonus features:
* **Device Flexibility**: Tensors can be moved easily between the CPU and GPU to optimize your workflow.
* **Autograd Support**: PyTorch tensors can automatically keep track of the operations performed on them, an essential feature for backpropagation.


### NOTE
<p class="center"><i>While I will include sample code snippets with this post, I will not include much output. This is on purpose! The best thing to learn quickly is to try these code snippets out for yourself and see what happens!</i></p>
<br>
<br>


#### Creating Tensors

Tensors can be made in multiple ways. Below are a few of the most common methods. Before we do anything, let's import the PyTorch library

```
import torch
```

##### Scalars

```
scalar = torch.tensor(7)
```

##### Vectors

```
vector = torch.tensor([7, 7])
```

##### Matrices
* Note that matrix variable names are capitalized by convention. 

```
MATRIX = torch.tensor([[7, 7],
                       [7, 7]])
```


##### Tensors of Ones, Zeros, & Random Values
We can make tensors filled with ones, zeros, or random values in a single line. All we need to do is pass in the dimensions we want of the output tensor.

```
ones = torch.ones(size=(3, 4))
zeros = torch.zeros(size=(1, 2, 3, 4))
random = torch.randn(size=(3, 20, 20))
```


##### Other Useful Methods - arange & like

```torch.arange(start, stop, step)``` - Create a tensor populated with values ranging from <i>start</i> to <i>stop</i> at incrememnts of size <i>step</i>

```torch.zeros_like(input=other_tensor)``` - Create a tensor of zeros (could be ones or randn) with the same shape as the input tensor




#### Working With Tensors

If tensors are going to do all the heavy lifting for our DNNs, then we better know how to work with them and how they can interact with each other. Here are some of the most common tensor operations, aggregations, and transformations. :

##### Common Operations
* Addition (`+`): 
  * Add a scalar to each element of a tensor or element-wise addition of two tensors of the same shape.
  * `A + B`
  * `A + c`
* Subtraction (`-`): 
  * Subtract a scalar from each element of a tensor or element-wise subtraction of two tensors of the same shape.
  * `A - B`
  * `A - c`
* Multiplication (`*`): 
  * Multiply each element of a tensor by a scalar or element-wise multiplication of two tensors of the same shape.
  * `A * B`
  * `A * c`
* Division (`/`): 
  * Divide each element of a tensor by a scalar or element-wise division of two tensors of the same shape.
  * `A / B`
  * `A / c`
* Matrix Multiplication (`@`): 
  * Matrix multiplication between two tensors with matching inner dimensions (i.e. `[m x n] @ [n x k]` )
  * `A @ B`
  * `torch.matmul(A, B)`

##### Aggregations
* Min
  * Return the minimum value in a tensor 
  * `tensor.min()`
* Max
  * Return the maximum value in a tensor 
  * `tensor.max()`
* Mean
  * Return the mean value of a tensor 
  * `tensor.mean()`
* Sum
  * Return the sum of values in a tensor 
  * `tensor.sum()`

##### Tensor Transformations
* Reshape
  * Reshape input tensor to specified new dimensions ()
  * `tensor.reshape(9, 1)`
* View
  * Similar to reshape, but **shares the same memory** as the original tensor ()
  * `tensor.view(9, 1)`
* Permute
  * Return a view of a tensor with dmensions permuted (swapped) in a certain way
  * `tensor.permute(2, 0, 1)` (dim0-> dim1, dim2-> dim0, dim1-> dim2)
* Stack
  * Combine multiple tensors along a specified dimension (default=0)
  * `torch.stack([tensor1, tensor2, tensor3])`
* Squeeze
  * Removes all dimensions of size 1 from the tensor
  * `tensor.squeeze()`
* Unsqueeze
  * Adds a dimension of size 1 to the tensor in specified index
  * `tensor.unsqueeze(dim=0)`




#### Indexing into Tensors

The creators of PyTorch worked hard to ensure that their library was easy to learn if you already are familiar with other technologies in the data work world. Luckily for us, that means that if you're comfortable slicing and dicing multidimensional arrays in NumPy, then you'll find the same syntax works for slicing and indexing into PyTorch Tensors.

Consider the following tensor:
```
A = [[1, 2, 3]
     [4, 5, 6]
     [7, 8, 9]]
```

* Indexing
  * `A[0] --> tensor([1, 2, 3])` 
  * `A[0][0] --> tensor(1)`
* Slicing
  * `A[1][0:2] --> tensor([4, 5])`



#### Thanks!

That's it for this whirlwind tour of the basic knowledge needed to work with tensors in PyTorch. For a deeper look, check out the [Official Documentation](https://pytorch.org/docs/stable/) and [ PyTorch Cheat Sheet](https://pytorch.org/tutorials/beginner/ptcheat.html). My writing here is meant as a primer to familiarize you with essential concepts. I encourage you now (and in the future) to always check the official resources to learn more! 


### [Continue Reading Part 3: Basic PyTorch Workflow ->](pytorch-workflow)

### [(<- Go Back to Part 1: A Gentle Introduction)](pytorch-introduction)