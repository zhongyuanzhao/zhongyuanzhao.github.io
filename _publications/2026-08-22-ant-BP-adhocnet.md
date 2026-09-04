---
title: "Ant Backpressure Routing for Dynamic Wireless Multi-hop Networks with Mixed Traffic Patterns"
category: 'preprint'
collection: manuscripts
permalink: /publications/2026-08-22-ant-BP-adhocnet.html
excerpt: 'A periodic, fully distributed routing scheme that uses virtual shortest path-biased Backpressure to learn pheromone-based forwarding policies for practical per-neighbor FIFO architectures.'
date: 2026-08-22
venue: 'Ad Hoc Networks'
paperurl: ''
citation: 'Negar Erfaniantaghvayi, Zhongyuan Zhao, Kevin Chan, Ananthram Swami, Santiago Segarra, &quot;Ant Backpressure Routing for Dynamic Wireless Multi-hop Networks with Mixed Traffic Patterns,&quot; <i>Ad Hoc Networks</i>, revised manuscript under review.'
---

This manuscript is an extended journal version of our IEEE MILCOM 2024 conference paper, ["Ant Backpressure Routing for Wireless Multi-hop Networks with Mixed Traffic Patterns"](/publications/2024-08-22-ant-SPBP-milcom.html). The revised manuscript is currently under review following a major-revision decision.

- Source code will be available soon at <https://github.com/Negar-Erfanian/AntBP>


## Abstract

Backpressure (BP) routing and its shortest-path biased variant (SP-BP) provide powerful congestion-aware multipath resource allocation for wireless multi-hop networks, but they rely on per-commodity queueing and slot-by-slot control that may be difficult to realize under practical or legacy forwarding architectures. Moreover, even state-of-the-art SP-BP still suffers from the last-packet problem when short-lived traffic coexists with streaming flows.
To address these limitations, we propose Ant Backpressure (Ant-BP), a periodic and fully distributed routing scheme that decouples route learning from packet forwarding. Ant-BP uses virtual SP-BP to construct pheromone-based forwarding probabilities, while actual packets are forwarded through per-neighbor first-in-first-out (FIFO) queues with probabilistic next-hop selection. This architecture enables link-capacity sharing across commodities, mitigates starvation of short-lived traffic, and extends the benefits of SP-BP to network architectures based on per-neighbor FIFO forwarding. Through periodic virtual updates, Ant-BP also adapts to transient link failures and mobility-induced topology changes. 
Our theoretical analysis and simulations show that, compared with conventional ant colony optimization (ACO) routing, virtual SP-BP enables Ant-BP to establish higher-quality forwarding policies with lower overhead. As a result, Ant-BP improves latency and delivery ratio over SP-BP and ACO-based baselines under mixed streaming and bursty traffic, achieves throughput comparable to SP-BP at low and medium traffic load, and remains robust to mismatched virtual-traffic assumptions, transient link failures, and node mobility.


_Key words_: Wireless multi-hop networks, Backpressure routing, Max-Weight scheduling, Ant colony optimization

 
