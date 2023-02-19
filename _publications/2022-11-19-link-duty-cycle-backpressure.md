---
title: "Delay-aware Backpressure Routing Using Graph Neural Networks"
category: 'conference'
collection: publications
permalink: /publications/2022-11-19-link-duty-cycle-backpressure.html
excerpt: 'Backpressure routing algorithm based on shortest path bias is augmented with Graph Convolutional Networks, which predict a delay-aware per-hop distance based on link duty cycle in scheduling. Our approach can improve the delay performance of backpressure routing at low signaling overhead. '
date: 2022-11-19
venue: 'arXiv'
paperurl: 'https://arxiv.org/pdf/2211.10748.pdf'
citation: 'Zhongyuan Zhao, Bojan Radojičić, Gunjan Verma, Ananthram Swami, Santiago Segarra, &quot; Delay-aware Backpressure Routing Using Graph Neural Networks,&quot; accepted to <i>IEEE ICASSP 2023</i>, arXiv 2211.10748 .'
---

Abstract
===
We propose a throughput-optimal biased backpressure (BP) algorithm for routing, where the bias is learned through a graph neural network that seeks to minimize end-to-end delay. Classical BP routing provides a simple yet powerful distributed solution for resource allocation in wireless multi-hop networks but has poor delay performance. A low-cost approach to improve this delay performance is to favor shorter paths by incorporating pre-defined biases in the BP computation, such as a bias based on the shortest path (hop) distance to the destination. In this work, we improve upon the widely-used metric of hop distance (and its variants) for the shortest path bias by introducing a bias based on the link duty cycle, which we predict using a graph convolutional neural network. Numerical results show that our approach can improve the delay performance compared to classical BP and existing BP alternatives based on pre-defined bias while being adaptive to interference density. In terms of complexity, our distributed implementation only introduces a one-time overhead (linear in the number of devices in the network) compared to classical BP, and a constant overhead compared to the lowest-complexity existing bias-based BP algorithms.

_Key words_: Backpressure routing; graph neural network; scheduling duty cycle; independent set; bias, shortest path


A brief intro
===

<figure>
<img src="/images/bias_backpressure_routes_visualization.png" alt="Biased Backpressure Routes" style="width:300px" class="center">
</figure>


Backpressure routing is a fully distributed packet routing algorithm for wireless multihop networks. It has a mechanism that drives data packets to explore every possible route in the network to their destination(s) just like water going through a network of pipes. This feature allows backpressure routing to stabilize the queues on each wireless devices -- meaning that the length of queues will not grow infinitely -- as long as the traffic load of the data flows are within the capacity of the network. This property is called throughput optimal. In contrast, some table-driven routing schemes may suffer from exploding queues when too many data flows go through the same critical node.

However, the classical backpressure routing is known to have poor delay performance in light-to-medium traffic load. Specifically, it exhibits undesirable characteristics such as slow startup, random walk, and the last packet problem, just like what happens when water flow through a flat floor -- it stays on the floor when there is not enough water to push them forward. 

To make the water to flow to the sink in the bathroom quickly, we can make the floor slightly sloping to the sink. The same idea also applies to backpressure routing, where pre-built biases, such as the shortest path distance toward the sink node, are added to nodes in the network. The most widely used distance metric is hop distance (counts). 

In this work, we propose a different distance metric that can better estimate the delay performance than the hop distance, by incorporating the link duty cycle in scheduling. The link duty cycle measures the proportion of time a link is activated, which is hard to predict through conventional algorithms. We train a graph neural network defined on the conflict graph of the wireless networks to predict the link duty cycle, which subsequently improves the pre-built shortest path distance biases, and can adapt to different network densities. 



The preprint is available at <https://arxiv.org/pdf/2211.10748.pdf>

The source code will soon be available at <https://github.com/zhongyuanzhao/biasBP> 


[Bojan Radojičić](https://www.linkedin.com/in/radojicicbojan/), a student from University of Novi Sad, Serbia, has contributed to the project, especially the source code, during his visit to Rice University.
