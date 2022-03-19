---
title: 'Apply Arbitrary Custom Gradient Through Squared Loss'
date: 2022-03-18
permalink: /posts/2022/03/apply-arbitrary-gradient-through-squared-loss/
tags:
  - deep learning
  - gradient descent
  - custom gradient
  - squared loss
---

By [Zhongyuan Zhao](https://zhongyuanzhao.com)

## TL;DR
Sometimes, especially in reinforcement learning, you have a non-differentiable loss/objective function with regard to (w.r.t.) the final or intermediate output $\mathbf{y}$ of the downstream machine learning (ML) pipeline. 
For example, a custom gradient, $\mathbf{\delta} = \nabla_{\mathbf{y}}l_{b}(\mathbf{y}, r)$, may depend on the feedback $r$ from the environment or some blackbox process, in which the automatic differentiation in *Tensorflow* and *PyTorch* will just generates zero gradient.
A quick trick to apply artibrary gradient $\mathbf{\delta}$ in backpropagation is using squared loss:
<p>
  \begin{equation*}
  l(\mathbf{y},\tilde{\mathbf{y}},\mathbf{\delta}) = \frac{1}{2} \lVert\mathbf{y} - (\tilde{\mathbf{y}} + \mathbf{\delta})\rVert_{2}^{2}   
  = \frac{1}{2} \sum_{k=1}^{n}\left[\mathbf{y}_{k} - (\tilde{\mathbf{y}}_{k} + \mathbf{\delta}_{k})\right]^2\;. 
  \end{equation*}
</p>
If your code is developed in *Tensorflow 1* (with sessions and computational graph), this trick can save you lots of trouble and burden in migrating to *Tensorflow 2* for slower eager execution, or to *PyTorch* for customized autograd.

## A primer on gradient descent

Given the input data $\mathbf{X}$ and label $\mathbf{y}^*$, the ML algorithm or artificial neural network (ANN) outputs prediction as $\mathbf{y}=f(\mathbf{X};\mathbb{\Theta})$.
Here, we denote a matrix by a bold upper case letter, such as $\mathbf{X}$, a vector by bold lower case letter, such as $\mathbf{y}$, and the $k$th element in vector $\mathbf{y}$ by subscript $k$ as $\mathbf{y}_{k}$. 
The ML algorithm or ANN is represented as a paramterized function $f(\mathbf{X};\mathbb{\Theta})$, where $\mathbb{\Theta}$ is the set of parameters.
The training of the parameters is carried out by an optimizer, which iteratively update the parameters through gradient descent in the direction of minimizing a loss function.

The loss function of the prediction, the label, and/or the set of parameters, denoted as $l(\mathbf{y}, \mathbf{y}^*, \mathbb{\Theta})$, is the objective function to be minimized in training (optimization). 
You probably have already learned several commonly used loss functions, such as [cross entropy](https://en.wikipedia.org/wiki/Cross_entropy) for classfication, [mean-squared-error](https://en.wikipedia.org/wiki/Mean_squared_error) for regression, and [$L^1$ and $L^2$ norm](https://towardsdatascience.com/intuitions-on-l1-and-l2-regularisation-235f2db4c261) for regularization. 
The gradient is typically generated as the derivatives of the loss function w.r.t. the parameters.
Following the [chain rule](https://en.wikipedia.org/wiki/Chain_rule), the gradient can be denoted as: 
<p>
  \begin{equation}
  \nabla_{\mathbb{\Theta}} l(\mathbf{y}, \mathbf{y}^*, \mathbb{\Theta}) = \frac{\partial l(\mathbf{y}, \mathbf{y}^*, \mathbb{\Theta})}{\partial \mathbf{y}} \frac{\partial \mathbf{y}}{\partial \mathbb{\Theta}}. \label{eq:gradient}
  \end{equation}
</p>
During training, the parameters are updated as:
<p>
  \begin{equation}
  \mathbb{\Theta} \leftarrow \mathbb{\Theta} - \alpha\nabla_{\mathbb{\Theta}} l(\mathbf{y}, \mathbf{y}^*, \mathbb{\Theta}),  \label{eq:gd}
  \end{equation}
</p>
where $0<\alpha<1$ is the learning rate.

##  Limitations of default automatic differentiation

The gradient in \eqref{eq:gradient} has two components: the derivative of the loss function w.r.t. the output $\mathbf{y}$, $\frac{\partial l(\mathbf{y}, \mathbf{y}^{*}, \mathbb{\Theta})}{\partial \mathbf{y}}$, and the derivative of the output $\mathbf{y}$ w.r.t. the parameters $\mathbb{\Theta}$, $\frac{\partial \mathbf{y}}{\partial \mathbb{\Theta}}$. 
In most supervised and unsupervised learning, the loss function $l(\cdot)$ and the machine learning pipeline $f(\cdot;\mathbb{\Theta})$ are both differentiable, which allows the backpropagation of the gradient being carried out by the [automatic differentiation](https://en.wikipedia.org/wiki/Automatic_differentiation) mechanism built in _Tensorflow_ and _PyTorch_.

However, in reinforcement learning, especially in the development of new approaches, you may end up with a differentiable ML pipeline $f(\cdot;\mathbb{\Theta})$ and a non-differentiable loss/objective function, denoted as $l_{b}(\mathbf{y}, r)$, where $r$ is the observed feedback from the environment. 
This is because in reinforcement learning, the objective is often to maximize or minimize certain performance metric that  does not have an analytical expression but can only be observed from the interaction between the actions of the agent (prediction $\mathbf{y}$) and the environment.

If your ML problem requires a customized or non-differentiable loss/objective function, it is quite burdensome to go beyond the set of commonly used loss functions built in *Tensorflow* and *PyTorch*. 
In *Tensorflow 2*, you need to learn the topic of [advanced automatic differentiation](https://www.tensorflow.org/guide/advanced_autodiff) and work with the `tf.GradientTape` API and `apply_gradients` function. 
In *PyTorch*, you need to [define new autograd functions](https://pytorch.org/tutorials/beginner/examples_autograd/polynomial_custom_function.html). 
You need first convert your data to tensor and then perform operations on the tensors based on the built-in functions in _Tensorflow_ or _PyTorch_.

## Apply custom gradient through squared Loss

Let's say you have worked out a formula to approximate (or guess) the gradient of a blackbox loss or objective function w.r.t. the prediction--the major effort of developing some new ML idea. 
You may prefer to implement that formula with the numerical packages like *numpy* and *scipy* rather than the built-in functions of *Tensorflow* or *PyTorch*, since the former may have better performance and/or functionality than the latter, or the former makes debugging much easier.


In a reinforcement learning or customized learning setting, you first collect the experience tuples of state (input data), action (prediction), and reward, $<\mathbf{X}^{(t)}, \tilde{\mathbf{y}}^{(t)}, r^{(t)}>$ for $t=0,\dots,T$, and then compute (or guess) the derivative of your loss/objective function w.r.t. the action (prediction) as $\mathbf{\delta} = l_{b}(\tilde{\mathbf{y}}, r)$.
Note that with exploration, the actual prediction $\tilde{\mathbf{y}}^{(t)}$ does not necessarily equal to the output $\mathbf{y}^{(t)}=f(\mathbf{X}^{(t)};\mathbb{\Theta})$.
Instead of implementing your gradient estimation entirely in Tensorflow or PyTorch, you can first compute the gradient $\mathbb{\delta}^{(t)}$ with whatever packages you like, then convert it into a tensor and apply it to the backpropagation through an off-the-shelf optimizer and the built-in [mean squared loss](https://www.tensorflow.org/api_docs/python/tf/keras/losses/MeanSquaredError) or the following squared loss: 

<p>
  \begin{equation}
  l_{s}(\mathbf{y},\tilde{\mathbf{y}},\mathbf{\delta}) = \frac{1}{2} \lVert\mathbf{y} - (\tilde{\mathbf{y}} + \mathbf{\delta})\rVert_{2}^{2}   
  = \frac{1}{2} \sum_{k=1}^{n}\left[\mathbf{y}_{k} - (\tilde{\mathbf{y}}_{k} + \mathbf{\delta}_{k})\right]^2\;. \label{eq:loss}
  \end{equation}
</p>

This is because in the case of exploiation, where $\tilde{\mathbf{y}}^{(t)}=\mathbf{y}^{(t)}=f(\mathbf{X}^{(t)};\mathbb{\Theta})$, we have
<p>
  \begin{equation}
  \frac{\partial l_{s}(\mathbf{y},\tilde{\mathbf{y}},\mathbf{\delta})}{\partial \mathbf{y}_k} = \mathbf{y}_{k} - (\tilde{\mathbf{y}}_{k} + \mathbf{\delta}_{k})=\mathbf{\delta}_{k}\;. \label{eq:proof}
  \end{equation}
</p>

The difference between squared loss and mean-squared-error loss is just a constant factor of $2/n$, which can be compensated by setting a larger or smaller learning rate $\alpha$.

## Open questions

1. Would \eqref{eq:loss} work in the case of exploration, where $\tilde{\mathbf{y}}^{(t)}\neq\mathbf{y}^{(t)}=f(\mathbf{X}^{(t)};\mathbb{\Theta})$? 

Honestly, I don't know. 
Maybe just try \eqref{eq:loss} directly or scale $\mathbf{\delta}$ in \eqref{eq:loss} by a small constant $0<\varepsilon<1$. 
We could also first run the forward pass to compute $\mathbf{y}^{(t)}=f(\mathbf{X}^{(t)};\mathbb{\Theta})$, then replace $\tilde{\mathbf{y}}$ in \eqref{eq:loss} to $\mathbf{y}^{(t)}$. In this case, we apply the gradient of another point $\tilde{\mathbf{y}}^{(t)}$ to the current point $\mathbf{y}^{(t)}$.
In stochastic gradient descent, the estimated gradient is quite noisy anyway.
