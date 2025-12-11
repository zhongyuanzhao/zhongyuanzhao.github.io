---
title: "Generalizing Biased Backpressure Routing and Scheduling to Wireless Multi-hop Networks with Advanced Air-interfaces"
category: 'preprint'
collection: manuscripts
permalink: /publications/2025-04-08-generalized-sp-bp-for-mimo-networks.html
excerpt: 'Generalize biased backpressure routing for multi-commodity link sharing and MaxWeight scheduling in MIMO networks.'
date: 2025-04-08
venue: 'arXiv'
paperurl: 'https://arxiv.org/pdf/2504.21721'
citation: 'Zhongyuan Zhao, Yujun Ming, Ananthram Swami, Kevin Chan, Fikadu Dagefu, Santiago Segarra, &quot; Generalizing Biased Backpressure Routing and Scheduling to Wireless Multi-hop Networks with Advanced Air-interfaces,&quot; <i>PrePrint arXiv: 2504.21721</i>, manuscript under preparation'
---


## Abstract

Backpressure (BP) routing and scheduling is a well-established resource allocation method for wireless multi-hop networks, known for its fully distributed operations and proven maximum queue stability. 
Recent advances in shortest path-biased BP routing (SP-BP) mitigate shortcomings such as slow startup and random walk, but exclusive link-level commodity selection still suffers from the last-packet problem and bandwidth underutilization. 
Moreover, classic BP routing implicitly assumes single-input-single-output (SISO) transceivers, which can lead to the same packets being scheduled on multiple outgoing links for multiple-input-multiple-output (MIMO) transceivers, causing detouring and looping in MIMO networks.
In this paper, we revisit the foundational Lyapunov drift theory underlying BP routing and demonstrate that exclusive commodity selection is unnecessary, and instead propose a Max-Utility link-sharing method. 
Additionally, we generalize MaxWeight scheduling to MIMO networks by introducing attributed capacity hypergraphs (ACH), an extension of traditional conflict graphs for SISO networks, and by incorporating backlog reassignment into scheduling iterations to prevent redundant packet routing. 
Numerical evaluations show that our approach substantially mitigates the last-packet problem in state-of-the-art (SOTA) SP-BP under lightweight traffic, and slightly expands the network capacity region for heavier traffic.

- Preprint <https://arxiv.org/pdf/2504.21721>
- Source code available soon 

This work is under preparation for a journal submission. The full version is under preparation for journal submission, and will include improved theoretical proof and extened experimental results over the PrePrint.

Another shorter version of it with improved theoretical proof was submitted to IEEE ICASSP 2026, <http://arxiv.org/abs/2512.09902>. 


Updated: 12/11/2025