---
layout: page
title: From RNN to Transformers
subtitle: LLM series
comments: true
tags: [DL]
---
What is a Neural Network:
It is a mathematical abstraction that aims to mimic a biological brain. It is a type of artificial intelligence and can be used to learn from data and perform tasks such as classification, image recognition, regression... A neural network consists of a interconnected nodes organised into layers. There is the input layer that recevies the raw data such as an image, text or numerical values. Then are the hidden layers which are responsible for learning and processing information. And finaly there is the output layer which ouputs the networks task result. During training a neural network adjust his internal parameters such as weights and biases through backpropagation. This process involves comparing the model prediciton with the actual value and minimize this difference by updating the weights. The objective is to optimize the network ability to generalize to new unseen data

Why the need for attention mechanism in Recurrent Neural Networks?
Recurrent Neural Networks are sequential therefore are very computationaly heavy. They are also prone to gradient vanishing/exploding problems. Activation functions such as ReLu is usually used to cope with this issue. LSTM (Long Short Term Memory) introduces a memory cell (to forget some information) to capture long term dependencies. A lot of information escape some of the processing and allow information to be retained for longer sequencies. Still above the order of 100 of words become problematic. Also LSTM are even slower. LSTM are also sequentials (futur state depends on past state) and can't take advantage of nowadays GPUs that need parallel computation. 

Freezing a layer
Freezing a layer can be especialy useful when doing transfer learning of finetuning. For example if you have an image recognition neural network and you want to adapt it to a specific cats and dogs classification task. Then you might wat to freeze the the first layers that are convolutional and capture information such as edges and texture, you end up only retraning the task specific part of the neural network. In the case of LLMs you might just want to train a classification layer at the end of the network. This will both make the re-training faster and reduce overfitting. 

### Transformers
The input data can be put in parallel. All the words are passed simultaneously and words embedding are computed simultaneously.
Transformers also need a positional encoder (know the position of the word in the sentence)
Attention: What part of the input should I focus on?