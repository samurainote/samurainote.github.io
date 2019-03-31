---
title:  "Understanding Core Philosophy of Tensorflow "
date:   2019-2-6
layout: single
author_profile: true
comments: true
tags:
---

![keras](/pics/Tensorflow/tensorflow.png)

**Why do you need to read this?**

By using Tensorflow, you can easily implement Deep Learning Tasks in real industry, even on your own computer.

For instance, Speech Recognition, Natural Language Processing (translation), Google search engine (image search / web search optimization), Google photo (face recognition / subject recognition), Gmail (mail classification), Inbox (mail automatic reply sentence creation The core technology that supports most of Google's services, including YouTube, advertising, etc.

**Contents**

1. [What is TensorFlow?](#SC)
2. [Pros and Cons of TensorFlow](#DS)
3. [WorkFlow of TensorFlow](#VO)

## <a name="SC" ></a>1. What is TensorFlow?

What is TensorFlow?

- Tensor: N-dimensional array
  - Vector: 1 dimension
  - Matrix: 2 dimensions

- Flow: data flow computation framework (like MapReduce)

- TensorFlow: a data flow based numerical computation framework
  - Best suited for Machine Learning and Deep Learning
  - Or any other HPC (High Performance Computing) applications

![flow](/pics/Tensorflow/flow.jpg)

## <a name="DS"></a>2. Pros and Cons of TensorFlow

- Pros
  1. TensorFlow can meet the needs of systems capable of constructing and training neural networks.
  2. TensorFlow works faster because it is written by the Python API, which is on top of the C / C ++ engine.
  3. Distributed processing enables TensorFlow to handle large amounts of data such as big data.
  4. TensorFlow can use for not only deep learning, but reinforcement learning and other machine learning algorithms.
  5. It's OOS, completely FREE!

- Cons
  1. It's relatively slow because it's written on Python.
  2. Hard to use for enterprise product because of no commercial support

## <a name="VO" ></a>3. WorkFlow of TensorFlow

0. Data Preparation

1. Modeling
    - X: Define Placeholder
    - W: Define Variable
    - α: Define Activation Fanction
    - y: Define Neural Network

2. Loss Function
    - Define Error Function: tf.reduce_mean() ..
    - Define Validation Metrics: accuracy, confusion matrix..
    - Selection of Optimization Algorithm for Gradient Descent: tf.train.MomentumOptimizer()

3. Training
    - Set a session: tf.Session()
