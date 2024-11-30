---
title: '"Fully Distributed Online Training of Graph Neural Networks in Networked Systems" submitted to IEEE ICMLCN 2025.'
date: 2024-11-28
collection: news
permalink: /news/2024/11/distributed-online-training-gnn-icmlcn25/
tags:
  - graph neural networks
  - Distributed optimization
  - wireless networks
  - distributed gradient descent
  - networked systems
  - news
---

Our paper ["Fully Distributed Online Training of Graph Neural Networks in Networked Systems"]() was submitted to [IEEE ICMLCN 2025](https://icmlcn2025.ieee-icmlcn.org/), the first author is [Rostyslav Olshevskyi](https://www.linkedin.com/in/rostyslav-olshevskyi-20665b197/?originalSubdomain=de), whom I co-advise with [Santiago Segarra](https://segarra.rice.edu/). This is also the first paper submitted by Rostyslav Olshevskyi on his PhD program at Rice University.


- Preprint available soon
- Source code available soon

## Abstract

Graph neural networks (GNNs) are powerful tools for developing scalable, decentralized artificial intelligence in large-scale networked systems, such as wireless networks, power grids, and transportation networks. 
Currently, GNNs in networked systems mostly follow a paradigm of 'centralized training, distributed execution', which limits their adaptability and slows down their development cycles. 
In this work, we fill this gap for the first time by developing a communication-efficient, fully distributed online training approach for GNNs applied to large networked systems.
For a mini-batch with $B$ samples, our approach of training an $L$-layer GNN only adds $L$ rounds of message passing to the $LB$ rounds required by GNN inference, with doubled message sizes.
Through numerical experiments in graph-based node regression, power allocation, and link scheduling in wireless networks, we demonstrate the effectiveness of our approach in training GNNs under supervised, unsupervised, and reinforcement learning paradigms. 

