---
layout: post
title: "Deep Learning With PyTorch, Part 3: PyTorch Workflow"
---
<head>
  <link rel="stylesheet" href="../assets/css/blogstyles.css">
</head>

# Deep Learning With PyTorch

## Part 3: Basic PyTorch Workflow

### THIS PAGE IS STILL UNDER CONSTRUCTION

#### Overview

In this post we will go end-to-end on a very basic PyTorch neural network. We'll start by generating some sample data using the equation for a line (`y = m*x + b`). We will then build and train a neural network capable of learning the parameters of this equation. Once the model is trained, we will want to know how well it did, so we will evaluate its performance. Finally, we will save our trained model in case we need it in the future. 

Again, this is a very basic neural network, but it follows the same fundamental steps that we would use to train a neural network of any complexity. Those steps are:
1. Prepare and load data
2. Build and instantiate a model
3. Train your model
4. Evaluate your model using inference
5. Save your model


#### Device Agnostic Code: Utilizing a GPU (if you’ve got one)

One of the most convenient features of PyTorch is it's ability to easily execute the same code on a CPU or GPU. In other words, regardless of whether code was developed on a CPU or GPU, it can be executed on either backend! All we have to do is specify where PyTorch should do its work. 

When we instantiate data objects in PyTorch (like tensors) they are allocated memory on one of two devices: `cpu`, or `cuda`. `cuda` is a parallel computing API made by NVIDIA that allows programs to leverage GPUs for faster computation.  

We typically want to run our PyTorch code using a GPU if it's available. While this might not necessarily always be true, it is usually the case. 

Essential PyTorch Workflow

1. Data
2. Build a model
3. Model training
    1. Instantiate model
    2. Select loss function and optimizer
    3. Iterate over training data - epochs
    4. For each epoch
        1. Generate predictions by calling forward() on the NN
        2. Calculate the loss using the loss function from earlier
        3. Clear the gradients from the optimizer using .zero_grad()
        4. Call backward() on loss function to calculate gradients (back propagation)
        5. Call optimizer.step() to update network weights according to calculated gradients (gradient descent)
4. Inference and evaluation
5. Save a model


Simple Example - linear model