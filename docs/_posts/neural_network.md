---
title: 机器学习
date: 2021-02-07 14:27:48
updated: 2021-02-07 14:27:48
description: 关于机器学习的笔记
category: 机器学习
---

## 改的一个例子
```py
import numpy as np

x = [[ True, True, True, True,False],
 [False,False,False, True, True],
 [ True, True,False,False,False],
 [False,False,False,False, True],
 [ True, True,False, True, True],
 [ True, True, True,False, True],
 [False, True, True, True, True],
 [False, True, True, True,False],
 [ True,False,False,False, True],
 [False,False,False,False,False],
 [False, True, True, True,False],
 [ True, True,False, True,False],
 [False, True,False,False,False],
 [ True, True,False,False,False],
 [ True,False,False,False, True],
 [False, True,False, True, True],
 [ True,False, True, True,False],
 [ True, True, True, True, True],
 [ True, True, True, True,False],
 [ True, True, True, True, True],
 [ True, True, True,False,False],
 [False,False,False,False, True],
 [False, True, True,False,False],
 [ True,False, True, True, True],
 [ True, True, True,False, True],
 [False, True, True,False,False],
 [ True,False,False,False, True],
 [False, True,False, True,False],
 [False,False, True,False,False],
 [False, True, True, True,False],
 [False,False,False,False,False],
 [ True,False, True, True, True],
 [ True,False,False, True,False],
 [False,False,False,False, True],
 [False, True,False,False,False],
 [False, True,False,False,False],
 [False,False,False,False, True],
 [False,False,False, True, True],
 [ True,False,False,False,False],
 [ True,False, True,False,False],
 [False, True, True,False,False],
 [False,False,False,False, True],
 [ True,False, True, True,False],
 [False, True, True,False, True],
 [ True,False, True, True, True],
 [ True,False,False,False,False],
 [ True, True,False, True, True],
 [False, True,False,False, True],
 [False,False,False,False,False],
 [ True, True, True,False,False],
 [False,False, True, True, True],
 [False,False, True, True, True],
 [False,False,False,False,False],
 [ True, True, True,False,False],
 [ True,False,False, True,False],
 [ True,False, True,False, True],
 [ True, True,False,False,False],
 [False, True,False, True, True],
 [ True,False, True, True,False],
 [ True, True, True, True, True],
 [ True, True, True, True,False],
 [ True, True,False, True, True],
 [ True, True, True, True,False],
 [False, True,False,False,False],
 [False,False,False, True, True],
 [False, True, True, True, True],
 [ True,False, True,False,False],
 [False,False, True, True, True],
 [False,False, True, True,False],
 [False, True, True,False,False],
 [False,False,False,False, True],
 [False, True,False,False,False],
 [False, True, True,False, True],
 [False,False, True, True,False],
 [False, True, True, True, True],
 [ True, True,False, True,False],
 [ True, True,False,False, True],
 [False, True, True, True,False],
 [False, True,False, True, True],
 [ True, True,False,False, True],
 [False,False,False,False, True],
 [False,False, True, True,False],
 [ True,False,False,False, True],
 [False, True,False,False, True],
 [False,False,False,False, True],
 [False, True, True,False,False],
 [ True, True,False,False, True],
 [False,False, True,False, True],
 [False,False, True,False,False],
 [False,False, True, True,False],
 [ True,False,False, True, True],
 [ True,False,False, True, True],
 [False,False, True,False,False],
 [False, True,False, True, True],
 [ True, True, True, True, True],
 [False,False,False, True, True],
 [False,False,False,False,False],
 [False,False, True, True, True],
 [False, True,False,False, True],
 [ True, True,False,False, True]]
y = [True, False, True, False, False, False, False, True, False, False, True, True, True, True, False, False, True, False, True, False, True, False, True, False, False, True, False, True, False, True, False, False, True, False, True, True, False, False, True, True, True, False, True, False, False, True, False, False, False, True, False, False, False, True, True, False, True, False, True, False, True, False, True, True, False, False, True, False, False, True, False, True, False, False, False, True, False, True, False, False, False, False, False, False, False, True, False, False, False, False, False, False, False, False, False, False, False, False, False, False]


class NeuralNetwork():

  def __init__(self):
    self.theta = 2 * np.random.random((5,1)) - 1
  
  def sigmoid(self, x):
    return 1 / (1 + np.exp(-x))

  def sigmoid_derivative(self, x):
    return x * (1 - x)

  def think(self, inputs):
        inputs = inputs.astype(float)
        output = self.sigmoid(np.dot(inputs, self.theta))
        return output


  def train(self, inputs, outputs, times):
    for i in range(times):
      output = self.think(inputs)
      error = outputs - output
      adjustment = np.dot(inputs.T, error * self.sigmoid_derivative(output))
      self.theta += adjustment

net = NeuralNetwork()
net.train(np.array(x).reshape(-1,5), np.array(y).reshape(-1,1), 100)
a = np.array([1,1,0,1,0])
b = np.array([1,1,0,0,1])
print(net.think(a))
print(net.think(b))
```


## 其它网址

### 需要翻墙
[Neural Networks, Manifolds, and Topology](http://colah.github.io/posts/2014-03-NN-Manifolds-Topology/)
[DeepLearning.AI](https://www.deeplearning.ai/)

### 直接访问
[机器学习速成课程](https://developers.google.cn/machine-learning/crash-course)
[反向传播算法](https://google-developers.gonglchuangl.net/machine-learning/crash-course/backprop-scroll)