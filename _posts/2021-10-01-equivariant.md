---
layout: post
title: Unsupervised Learning with Equivariant Imaging
date: 2021-10-01 11:12:00-0400
description: an introduction to unsupervised learning to solve inverse problems
tags: formatting math
categories: deep-learning
---
Inverse problems are ubiquitous in signal and image processing. In most applications, we need to reconstruct an underlying signal $x\in\mathbb{R}^{n}$, from some measurements $y\in\mathbb{R}^{m}$, that is, invert the forward measurement process, $$y = Ax+n$$ where $n$ represents some noise and $A$ is the forward operator. Due to the ill-posed nature of $A$ (we generally have $m<n$) and noise, there are multiple possible solutions $x$ for a given $y$. Fortunately, the set of plausible (natural) signals $x$ lie in a small low-dimensional set $\mathcal{X}$ of the whole of $\mathbb{R}^{n}$, so we can have a unique $x$ for a given $y$.</p>


The traditional approach is to build a mathematical model to describe $\mathcal{X}$ leveraging some prior knowledge about the underlying signals (e.g. natural images can be described as piecewise smooth). However, this a hard task which is problem-dependent and it is generally a loose description of the true $\mathcal{X}$.


In recent years, an alternative approach is to learn inverse mapping from $y\mapsto x$ directly from training data, bypassing the need to design a prior model. Fuelled by the powerful learning bias of deep convolutional neural networks (interest readers can have a look at my previous post about understanding this implicit bias), the goal is to learn a function $x=f(y)$ from training pairs $(x_i,y_i)$. The fundamental limitation of this approach is that in many real world applications we can only access $y$. Training only with the $y_i$ (enforcing measurement consistency) accounts to finding an $f$ such that $y=A f(y)$. Unfortunately this is doomed to fail, as there are infinite possible functions $f$ that can fit the measurements perfectly well! This is because any $f$ can output any value in the nullspace of $A$ and still achieve measurement consistency. In other words, this fundamental limitation is a chicken-and-egg problem:  we cannot learn to solve an inverse problem without solving it first to obtain the ground-truth training data!


In this paper, we show that this problem can be overcome by adding a small assumption to the underlying set of signals $\mathcal{X}$: invariance. It is well-known that most natural signals posses some kind of invariance. For example, images are generally invariant to shifts or rotations. Hence, the whole sensing process $x = (f \circ A) (x)$ is necessarily an equivariant function, that is, given a transformation $T_g$ (e.g. a shift), we have that $$T_gx = (f\circ A) (T_gx)$$. The invariance gives us information of the nullspace of A, which boils down to the following observation: $$y=Ax = AT_g x'  = A_g x'$$ which just relies on the fact that $x'= T_gx$ is another valid signal. Hence we can see beyond the range space of $A$, as we have an implicit access to multiple different operators  $A_g = AT_g$ for all possible transformations $T_1,\dots,T_{G}$. 


We show that this invariance constraint on $(f\circ A)$ can be easily incorporated as an additional loss term when training a deep network. Our experiments show that for the computed tomography and inpaiting problems,  the equivariant learning approach (only having access to measurements $y_i$) performs as well as the fully supervised case i.e. having training pairs with ground-truth data $(x_i,y_i)$, by-passing the fundamental limitation of learning to solve inverse problems. 