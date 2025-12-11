---
title: 'Our work on Differentiable Digital Twin of Distributed Link Scheduling presented at Asilomar 2025'
date: 2025-10-27
collection: news
permalink: /news/2025/10/differentiable-digital-twin-presented-at-Asilomar/
tags:
  - link scheduling
  - gradient-based network optimization
  - wireless multi-hop networks
  - digital twin
  - news
---

### A Differentiable Digital Twin of Distributed Link Scheduling for Contention-Aware Networking
*(Zhongyuan Zhao<sup>†</sup>, Yujun Ming<sup>†</sup>, Kevin Chan, Ananthram Swami, Santiago Segarra)*  
<sup>†</sup>Equal contribution

Presented at the **Asilomar Conference on Signals, Systems, and Computers**, Pacific Grove, CA, October 2025.

---

We presented our latest work on building an **analytical and differentiable digital twin** of distributed medium access control (MAC) based on randomized contention — a mechanism widely used in **Wi-Fi, mobile ad-hoc networks, wireless mesh networks**, and in emerging **6G scenarios** such as wireless backhaul and spectrum sharing.  

The purpose of this digital twin is to enable **gradient-based optimization** for wireless networking.  
While **network flow optimization** is well understood in wired networks — for example through efficient algorithms for [*minimum-cost flow*](https://en.wikipedia.org/wiki/Minimum-cost_flow_problem) — it becomes far more complex in wireless systems, where **links contend for transmission in a shared medium**.  
Here, **link capacity and cost** depend not only on the physical-layer data rate but also on the **traffic loads and activity of other links** across the network.  

Traditional methods rely heavily on **trial-and-error** for routing and on **packet-level simulation** for network analysis, both of which are slow and provide limited analytical insight.

Our analytical **digital twin** models **contention behavior** as a graph-based function, capturing the resulting **effective link capacity** through *link scheduling duty cycles*.
This enables **fast prediction of congestion** across the network, as illustrated below.

<div align="center">
  <img src="/images/asilomar2025_dt_diagram.png" alt="Analytical Digital Twin concept diagram" width="600">
  <br><em>Figure 1. The differentiable digital twin models link contention and effective capacity to forecast congestion.</em>
</div>

The proposed model runs **over 1000× faster** than simulation (reducing runtime from minutes to tens of milliseconds) and allows us to apply **gradient-based optimization** to improve **link scheduling priorities**, **routing**, and **load-balancing** decisions — effectively mitigating congestion and expanding network capacity.  
Moreover, it can be implemented in a **fully distributed manner**, making it suitable for integration into next-generation network protocols.


In the example below, congestion is mitigated by optimizing the link-level contention aggressiveness in a network of 50 transceivers and 8 flows, while keeping all routing paths fixed.

<div align="center">
  <img src="/images/50node-network-8-flows.png" alt="A test instance with 8 flows on a network of 50 nodes" width="300">
  <br><em>Figure 2. A test instance with 8 flows on a network of 50 nodes.</em>
</div>

<div align="center">
  <img src="/images/asilomar2025_link_priority_optimization.png" alt="Congestion mitigation through link-priority optimization" width="600">
  <br><em>Figure 3. Gradient-based optimization of link scheduling priorities (<i>z</i> in Figure 1, representing the contending aggressiveness policy) mitigates congestion.</em>
</div>

This approach provides a **scalable analytical foundation** for **next-generation, self-organizing wireless networks**, paving the way for smarter network protocols and new methods of network flow optimization.  

**Preprint will be released soon.**

- Code <https://github.com/JoieMing/luby-ndt/>