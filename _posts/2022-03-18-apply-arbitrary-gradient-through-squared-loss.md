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

Author: [Zhongyuan Zhao](https://zhongyuanzhao.com)

## TL;DR
Sometimes, especially in reinforcement learning, you have a non-differentiable loss/objective function with regard to (w.r.t.) the final or intermediate output $\mathbf{y}$ of your downstream machine learning pipeline. 
For example, your custom gradient, $\mathbf{\delta} = \nabla_{\mathbf{y}}l_{b}(\mathbf{y}, r)$, may depend on the feedback $r$ from the environment or some blackbox process, whereas the automatic differentiation in *Tensorflow* and *PyTorch* will just generates zero gradient.
A quick trick to apply artibrary gradient $\mathbf{\delta}$ to your backpropagation pipeline is through squared loss:
<p>
  \begin{equation*}
  l(\mathbf{y},\tilde{\mathbf{y}},\mathbf{\delta}) = \frac{1}{2} \lVert\mathbf{y} - (\tilde{\mathbf{y}} + \mathbf{\delta})\rVert_{2}^{2}   
  = \frac{1}{2} \sum_{k=1}^{n}\left[\mathbf{y}_{k} - (\tilde{\mathbf{y}}_{k} + \mathbf{\delta}_{k})\right]^2\;. 
  \end{equation*}
</p>
If your code is based on the computational graph in *Tensorflow 1*, this trick can save you lots of trouble and burden in migrating source code to *Tensorflow 2* for slower eager execution, or to *PyTorch* for customized autograd.

## A primer

In machine learning (ML), the parameters of an algorithm or artificial neural network (ANN) are learned through gradient descent. 
Given the input data $\mathbf{X}$ and label $\mathbf{y}^*$, the ML algorithm or ANN outputs estimate as $\mathbf{y}=f(\mathbf{X};\mathbb{\Theta})$.
Here we denote a matrix by a bold upper case letter, such as $\mathbf{X}$, a vector by bold lower case letter, such as $\mathbf{y}$, and the $k$th element in vector $\mathbf{y}$ by subscript $k$ as $\mathbf{y}_{k}$. 
The ML algorithm or ANN is denoted by a paramterized function $f(\mathbf{X};\mathbb{\Theta})$, where $\mathbb{\Theta}$ is the set of parameters to be learned (optimized).

A loss/cost function is a function the output, the label, and/or the parameters, denoted as $l(\mathbf{y}, \mathbf{y}^*, \mathbb{\Theta})$, which is the objective to be minimized through training (optimization). 
If you read to here, you probably have already learned a few most commonly used loss functions, such as [cross entropy](https://en.wikipedia.org/wiki/Cross_entropy) for classfication, [mean-squared-error](https://en.wikipedia.org/wiki/Mean_squared_error) for regression, and [$L^1$ and $L^2$ norm](https://towardsdatascience.com/intuitions-on-l1-and-l2-regularisation-235f2db4c261) for regularization. 
The gradient is typically generated as the derivatives of the loss function with regard to the parameters.
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

## The limitation of automatic differentiation

The gradient in \eqref{eq:gradient} has two components: the derivative of the loss function w.r.t. the output $\mathbf{y}$, $\frac{\partial l(\mathbf{y}, \mathbf{y}^{*}, \mathbb{\Theta})}{\partial \mathbf{y}}$, and the derivative of the output $\mathbf{y}$ w.r.t. the parameters $\mathbb{\Theta}$, $\frac{\partial \mathbf{y}}{\partial \mathbb{\Theta}}$. 
In most supervised and unsupervised learning, the loss function $l(\cdot)$ and the machine learning pipeline $f(\cdot;\mathbb{\Theta})$ are both differentiable, which allows the backpropagation of the gradient being carried out by the [automatic differentiation](https://en.wikipedia.org/wiki/Automatic_differentiation) mechanism built in _Tensorflow_ and _PyTorch_.

However, in reinforcement learning, especially in the development of new approaches, you often end up with a differentiable ML pipeline $f(\cdot;\mathbb{\Theta})$ and a non-differentiable loss/objective function, denoted as $l_{b}(\mathbf{y}, r)$, where $r$ is the observed feedback from the environment. 
This is because in reinforcement learning, your objective is often to maximize or minimize certain performance metric that  does not have an analytical expression but can only be observed from the interaction between the actions of the agent (your output $\mathbf{y}$) and the environment.

If you are working on some customized or non-differentiable loss/objective function for your ML problem, you may find it quite burdensome to go beyond the most commonly used set of pre-defined loss functions in *Tensorflow* and *PyTorch*. In *Tensorflow 2*, you need to learn the topic of [advanced automatic differentiation](https://www.tensorflow.org/guide/advanced_autodiff) and work with the `tf.GradientTape` API and `apply_gradients` function. In *PyTorch*, you need to [define new autograd functions](https://pytorch.org/tutorials/beginner/examples_autograd/polynomial_custom_function.html). 

## Apply custom gradient through squared Loss

Let's say you have worked out a way to approximate (or guess) the gradient of a blackbox loss or objective function. You prefer to implement your method with the package of *numpy* rather than the built-in functions of *Tensorflow* or *PyTorch*. The former may be more efficient in runtime and more comprehensive in functionality than the latter.

In your reinforcement learning or customized learning setting, you collected experience tuples of state (input data), action (output), and reward, $<\mathbf{X}^{(t)}, \tilde{\mathbf{y}}^{(t)}, r^{(t)}>$ for $t=0,\dots,T$, and then compute (or guess) the derivative of your loss/objective w.r.t. the action (output) as $\mathbf{\delta} = l_{b}(\tilde{\mathbf{y}}, r)$.
Note that due to exploration, the actual action $\tilde{\mathbf{y}}^{(t)}$ does not necessarily equal to the output of $\mathbf{y}^{(t)}=f(\mathbf{X}^{(t)};\mathbb{\Theta})$.
Instead of packing your gradient for `apply_gradient`, you can simply use the following squared loss (or `tf.compat.v1.losses.mean_squared_error`) to apply gradient $\mathbb{\delta}^{(t)}$ to the backpropagation: 

<p>
  \begin{equation}
  l(\mathbf{y},\tilde{\mathbf{y}},\mathbf{\delta}) = \frac{1}{2} \lVert\mathbf{y} - (\tilde{\mathbf{y}} + \mathbf{\delta})\rVert_{2}^{2}   
  = \frac{1}{2} \sum_{k=1}^{n}\left[\mathbf{y}_{k} - (\tilde{\mathbf{y}}_{k} + \mathbf{\delta}_{k})\right]^2\;. \label{eq:loss}
  \end{equation}
</p>

This is because in the case of exploiation, where $\tilde{\mathbf{y}}^{(t)}=\mathbf{y}^{(t)}=f(\mathbf{X}^{(t)};\mathbb{\Theta})$, we have
<p>
  \begin{equation}
  \frac{\partial l(\mathbf{y},\tilde{\mathbf{y}},\mathbf{\delta})}{\partial \mathbf{y}_k} = \mathbf{y}_{k} - (\tilde{\mathbf{y}}_{k} + \mathbf{\delta}_{k})=\mathbf{\delta}\;. \label{eq:proof}
  \end{equation}
</p>

## Open question

Would \eqref{eq:loss} work for the case of exploration, where $\tilde{\mathbf{y}}^{(t)}\neq\mathbf{y}^{(t)}=f(\mathbf{X}^{(t)};\mathbb{\Theta})$? Honestly, I don't know. Maybe we can just try \eqref{eq:loss} or scale $\mathbf{\delta}$ in \eqref{eq:loss} by a small constant $0<\varepsilon<1$.
