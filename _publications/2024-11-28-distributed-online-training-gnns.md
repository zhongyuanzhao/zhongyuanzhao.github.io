---
title: "Fully Distributed Online Training of Graph Neural Networks in Networked Systems"
category: 'preprint'
collection: publications
permalink: /publications/2024-11-28-distributed-online-training-gnns.html
excerpt: 'This work fills the gap in distributed online training of graph neural networks applied in networked systems, which previously rely on the paradigm of "centralized offline training with distributed execution".'
date: 2024-11-28
venue: 'IEEE ICMLCN 2025'
paperurl: 'https://arxiv.org/pdf/2412.06105'
citation: 'Rostyslav Olshevskyi, Zhongyuan Zhao, Kevin Chan, Gunjan Verma, Ananthram Swami, and Santiago Segarra, &quot; Fully Distributed Online Training of Graph Neural Networks in Networked Systems,&quot; <i>IEEE International Conference on Machine Learning for Communicatio and Networking (ICMLCN) 2025</i>, under review'
---


- Preprint available <https://arxiv.org/pdf/2412.06105>
- Source code available soon

## Abstract

Graph neural networks (GNNs) are powerful tools for developing scalable, decentralized artificial intelligence in large-scale networked systems, such as wireless networks, power grids, and transportation networks. 
Currently, GNNs in networked systems mostly follow a paradigm of 'centralized training, distributed execution', which limits their adaptability and slows down their development cycles. 
In this work, we fill this gap for the first time by developing a communication-efficient, fully distributed online training approach for GNNs applied to large networked systems.
For a mini-batch with $B$ samples, our approach of training an $L$-layer GNN only adds $L$ rounds of message passing to the $LB$ rounds required by GNN inference, with doubled message sizes.
Through numerical experiments in graph-based node regression, power allocation, and link scheduling in wireless networks, we demonstrate the effectiveness of our approach in training GNNs under supervised, unsupervised, and reinforcement learning paradigms. 

