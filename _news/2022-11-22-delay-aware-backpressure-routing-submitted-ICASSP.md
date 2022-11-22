---
title: '"Delay-aware Backpressure Routing Using Graph Neural Networks" submitted to ICASSP 2023, preprint available at arXiv.'
date: 2022-11-22
collection: news
permalink: /news/2022/11/delay-aware-backpressure-routing-submitted-ICASSP/
tags:
  - backpressure routing
  - graph convolutional networks
  - wireless multi-hop networks
  - link duty cycle
  - news
---

Backpressure routing is a fully distributed packet routing algorithm for wireless multihop networks. It has a mechanism that drives data packets to explore every possible route in the network to their destination(s) just like water going through a network of pipes. This feature allows backpressure routing to stabilize the queues on each wireless devices -- meaning that the length of queues will not grow infinitely -- as long as the traffic load of the data flows are within the capacity of the network. This property is called throughput optimal. In contrast, some table-driven routing schemes may suffer from exploding queues when too many data flows go through the same critical node.

However, the classical backpressure routing is known to have poor delay performance in light-to-medium traffic load. Specifically, it exhibits undesirable characteristics such as slow startup, random walk, and the last packet problem, just like what happens when water flow through a flat floor -- it stays on the floor when there is not enough water to push them forward. 

To make the water to flow to the sink in the bathroom quickly, we can make the floor slightly sloping to the sink. The same idea also applies to backpressure routing, where pre-built biases, such as the shortest path distance toward the sink node, are added to nodes in the network. The most widely used distance metric is hop distance (counts). 

In this work, we propose a different distance metric that can better estimate the delay performance than the hop distance, by incorporating the link duty cycle in scheduling. The link duty cycle measures the proportion of time a link is activated, which is hard to predict through conventional algorithms. We train a graph neural network defined on the conflict graph of the wireless networks to predict the link duty cycle, which subsequently improves the pre-built shortest path distance biases, and can adapt to different network densities. 



The preprint is available at <https://arxiv.org/pdf/2211.10748.pdf>

The source code will soon be available at <https://github.com/zhongyuanzhao/biasBP> 


[Bojan Radojičić](https://www.linkedin.com/in/radojicicbojan/), an student from University of Novi Sad, Serbia, has contributed to the project, especially the source code, during his visit to Rice University.
