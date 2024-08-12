---
layout: post
title: "Deep Learning With PyTorch, Part 1: A Gentle Introduction"
---
<head>
  <link rel="stylesheet" href="../assets/css/blogstyles.css">
</head>

# Deep Learning With PyTorch

## Part 1: A Gentle Introduction

With all the media coverage of ChatGPT and other large language models, you're probably aware that the field of artificial intelligence is red hot these days. Indeed, the initial release and subsequent success of ChatGPT nearly two years ago sent shockwaves through the AI community and brought the technology to fore of public discussion. 

But just how do these technologies work? After all, hasn't AI been a topic of research and discussion for decades? Why has it just now come into prominence? 

There are several major factors driving the success of modern AI models like ChatGPT. First, the internet and age of information has given rise to enormous amounts of data, an essential ingredient for model training. Second, modern advances in computing architecture (e.g., distributed computing) and hardware (e.g., GPUs) have made it possible to train larger and more complex models. The final driver, and the topic of this and several future posts, is the maturation of the field of <i>deep learning.</i>


#### What is Deep Learning?
At a high level, deep learning is a machine learning technique that was inspired by the structure of neurons in the brain. Deep learning models are composed of layers of connected artificial neurons, mimicking how neurons connect and fire together in the brain. For this reason, deep learning networks are also referred to as neural networks. The term "deep" comes from when there are at least two layers within the network, but modern deep neural networks (DNNs) can have dozens or even hundreds of layers. 

<figure>  
  <img class="center" src="../assets/img/blog/pytorch/dnn.png" alt="Example DNN">
  <figcaption>Example Deep Neural Network</figcaption>
</figure>


The above description of DNNs might sound too abstract to be helpful. However, the abstract nature of DNNs is exactly what makes them so powerful. It's up to us as designers to create the DNN best suited to the problem we are trying to solve. Depending on the application, one could choose completely different components of underlying architecture (e.g., Attention, GANs, CNNs, LSTMs). Indeed, if you could open up and look inside a popular AI application like ChatGPT or Dall-E you would see a composition of these components. 


#### Why PyTorch?
[PyTorch](https://pytorch.org/) is an open source deep learning framework created by the folks over at Facebook (Meta). In recent years it has grown in popularity both in industry and academia due to its flexibility, readability, and behind-the-scenes optimization. Check out the trends over at [paperswithcode](https://paperswithcode.com/trends) to get an idea of just how popular PyTorch has become! It's used at Facebook, Microsoft, Tesla, and OpenAI to name a few. For this reason, PyTorch is an excellent framework in which to learn the basics of deep learning. 

<figure>  
  <img src="../assets/img/blog/pytorch/pytorch-trends.png" alt="pytorch trends">
  <figcaption>PyTorch Trends (Aug 2024)</figcaption>
</figure>



#### Join Me!
As I explore and learn the rich PyTorch ecosystem! Over a series of blog posts I will write about the fundamentals of PyTorch, some principles of deep learning and machine learning, and how to apply PyTorch to solve some common ML problems. 


### [Continue Reading Part 2: PyTorch Fundamentals](pytorch-fundamentals)