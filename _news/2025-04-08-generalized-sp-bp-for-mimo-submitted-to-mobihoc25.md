---
title: '"Generalizing Biased Backpressure Routing and Scheduling to Wireless Multi-hop Networks with Advanced Air-interfaces" submitted to ACM Mobihoc 2025.'
date: 2025-04-08
collection: news
permalink: /news/2025/04/generalized-sp-bp-for-mimo-submitted-to-mobihoc25/
tags:
  - biased backpressure routing
  - routing
  - scheduling
  - wireless multi-hop networks
  - MIMO networks
  - news
---

Zhongyuan Zhao, Yujun Ming, Ananthram Swami, Kevin Chan, Fikadu Dagefu, Santiago Segarra, “Generalizing Biased Backpressure Routing and Scheduling to Wireless Multi-hop Networks with Advanced Air-interfaces”, ACM Mobihoc 2025, submitted to.

## Abstract

Backpressure (BP) routing and scheduling is a well-established resource allocation method for wireless multi-hop networks, known for its fully distributed operations and proven maximum queue stability. 
Recent advances in shortest path-biased BP routing (SP-BP) mitigate shortcomings such as slow startup and random walk, but exclusive link-level commodity selection still suffers from the last-packet problem and bandwidth underutilization. 
Moreover, classic BP routing implicitly assumes single-input-single-output (SISO) transceivers, which can lead to the same packets being scheduled on multiple outgoing links for multiple-input-multiple-output (MIMO) transceivers, causing detouring and looping in MIMO networks.
In this paper, we revisit the foundational Lyapunov drift theory underlying BP routing and demonstrate that exclusive commodity selection is unnecessary, and instead propose a Max-Utility link-sharing method. 
Additionally, we generalize MaxWeight scheduling to MIMO networks by introducing attributed capacity hypergraphs (ACH), an extension of traditional conflict graphs for SISO networks, and by incorporating backlog reassignment into scheduling iterations to prevent redundant packet routing. 
Numerical evaluations show that our approach substantially mitigates the last-packet problem in state-of-the-art (SOTA) SP-BP under lightweight traffic, and slightly expands the network capacity region for heavier traffic.

- Preprint available soon
- Source code available soon 
