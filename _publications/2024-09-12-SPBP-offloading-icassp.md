---
title: "Joint Task Offloading and Routing in Wireless Multi-hop Networks Using Biased Backpressure Algorithm"
category: 'conference'
collection: publications
permalink: /publications/2024-09-12-SPBP-offloading-icassp.html
excerpt: 'A new formulation of computation offloading in wireless multi-hop networks that can simultaneously achieve task offloading, load balancing, routing, and scheduling under a unified biased Backpressure routing and scheduling framework.'
date: 2024-09-12
venue: 'IEEE ICASSP 2025'
paperurl: 'https://arxiv.org/pdf/2412.15385'
citation: 'Zhongyuan Zhao, Jake Perazzone, Gunjan Verma, Kevin Chan, Ananthram Swami, and Santiago Segarra, &quot; Joint Task Offloading and Routing in Wireless Multi-hop Networks Using Biased Backpressure Algorithm,&quot; <i>IEEE ICASSP 2025</i>, accepted for publication'
---

## Abstract

A significant challenge for computation offloading in wireless multi-hop networks is the complex interaction among traffic flows in the presence of interference.
Existing approaches often ignore these key effects and/or rely on outdated queueing and channel state information.
To fill these gaps, we reformulate joint offloading and routing as a routing problem on an extended graph with physical and virtual links.
We adopt the state-of-the-art shortest path-biased Backpressure routing algorithm, 
which allows the destination and the route of a job to be dynamically adjusted at every time step based on network-wide long-term information and real-time states of local neighborhoods.
In large networks, our approach achieves smaller makespan than existing approaches, such as separated Backpressure offloading and joint offloading and routing based on linear programming. 

## Resources

- Preprint available <https://arxiv.org/pdf/2412.15385>
- Source code available soon at <https://github.com/zhongyuanzhao/edgeSPBP>

Related papers (biased Backpressure routing)
- ["Biased Backpressure Routing using Link Features and Graph Neural Networks"](/publications/2024-03-20-biased-BP-using-link-features-and-gnn.html) 
- [Delay-aware Backpressure Routing using Graph Neural Networks](/publications/2022-11-19-link-duty-cycle-backpressure.html)
- [Enhanced Backpressure Routing with Wireless Link Features](/publications/2023-09-26-enhanced-sp-backpressure.html)
