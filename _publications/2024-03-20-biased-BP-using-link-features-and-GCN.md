---
title: "Biased Backpressure Routing using Link Features and Graph Neural Networks"
category: 'preprint'
collection: publications
permalink: /publications/2024-03-20-biased-BP-using-link-features-and-gnn.html
excerpt: 'To improve the latency performance of Backpressure routing, we improve shortest path-biased Backpressure routing by introducing a new distance metric for shortest path, principled approaches for optimal bias scaling and bias maintenance, as well as a new delay-based backlog metric that can be integrated into biased Backpressure routing.'
date: 2024-03-20
venue: 'IEEE TWC'
paperurl: ''
citation: 'Zhongyuan Zhao, Bojan Radojičić, Gunjan Verma, Ananthram Swami, Santiago Segarra, &quot; Distributed Link Sparsification for Scalable Scheduling using Graph Neural Networks,&quot; <i>IEEE Transactions on Wireless Communications</i>, under review'
---

Related conference papers and code
- [Delay-aware Backpressure Routing using Graph Neural Networks](/publications/2022-11-19-link-duty-cycle-backpressure.html)
- [Enhanced Backpressure Routing with Wireless Link Features](/publications/2023-09-26-enhanced-sp-backpressure.html)
- Preprint and source code will be available soon


## Abstract

To reduce the latency of Backpressure (BP) routing in wireless multi-hop networks, we propose to enhance the existing shortest path-biased BP (SP-BP) and sojourn time-based backlog metrics, since they introduce no additional time step-wise signaling overhead to the basic BP.
Rather than relying on hop-distance, we introduce a new edge-weighted shortest path bias built on the scheduling duty cycle of wireless links, which can be predicted by a graph convolutional neural network based on the topology and traffic of wireless networks.
Additionally, we tackle three long-standing challenges associated with SP-BP: optimal bias scaling, efficient bias maintenance, and integration of delay awareness. 
Our proposed solutions inherit the throughput optimality of the basic BP, as well as its practical advantages of low complexity and fully distributed implementation. 
Our approaches rely on common link features and introduces only a one-time constant overhead to previous SP-BP schemes, or a one-time overhead linear in the network size to the basic BP.
Numerical experiments show that our solutions can effectively address the major drawbacks of slow startup, random walk, and the last packet problem in basic BP, improving the end-to-end delay of existing low-overhead BP algorithms under various settings of network traffic, interference, and mobility.

_Key words_:  Backpressure, MaxWeight scheduling, shortest path, queueing networks, last packet problem, graph neural networks.

