---
layout: post
title: "Deep Learning With PyTorch, Part 2: Fundamentals"
---
<head>
  <link rel="stylesheet" href="../assets/css/blogstyles.css">
</head>

# Deep Learning With PyTorch

## Part 3: Basic PyTorch Workflow

### THIS PAGE IS STILL UNDER CONSTRUCTION


Utilizing a GPU (if you’ve got one)
* Device agnostic code

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