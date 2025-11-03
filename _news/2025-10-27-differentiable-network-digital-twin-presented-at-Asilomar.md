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
*(Zhongyuan Zhao, Yujun Ming, Kevin Chan, Ananthram Swami, Santiago Segarra)*  
Presented at the **Asilomar Conference on Signals, Systems, and Computers**, Pacific Grove, CA, October 2025.

---

We presented our latest work on building an **analytical and differentiable digital twin** of randomized link scheduling — a core challenge in distributed and self-organizing wireless networks.

Randomized contention is widely used in systems such as **Wi-Fi, mobile ad-hoc networks, wireless mesh networks**, and in emerging **6G scenarios** like wireless backhaul and spectrum sharing.  
While **network flow optimization** is well understood in wired networks, e.g., through efficient algorithms for *minimum-cost flow* problems — it becomes far more complex in wireless systems, where **links contend for transmission in shared medium**.  
In this setting, **link capacity and cost** depend not only on transmission data rate of the physical layer but also on **traffic loads of all links in the network**.  

Traditional wireless optimization relies heavily on **trial-and-error tuning or packet-level simulation**, which are slow and offer limited analytical insight.

Our analytical **digital twin** directly models the **contention behavior** and resulting **effective link capacity** through *link scheduling duty cycles*, which can be viewed as a graph-based function.  
This enables **fast prediction of congestion** across the network, as illustrated below.

<div align="center">
<img src="/images/asilomar2025_dt_diagram.png" alt="Analytical Digital Twin concept diagram" width="80%">
<br><em>Figure 1. The differentiable digital twin models link contention and effective capacity to forecast congestion.</em>
</div>

The proposed model runs **over 1000× faster** than simulation (from minutes to tens of milliseconds) and allows us to apply **gradient-based optimization** to improve **link scheduling priorities**, **routing**, and **load balancing** decisions—effectively mitigating congestion and expanding network capacity.

<div align="center">
<img src="/images/asilomar2025_link_priority.png" alt="Congestion mitigation through link-priority optimization" width="80%">
<br><em>Figure 2. A test instance with 8 flows on a network of 50 nodes.</em>
</div>

<div align="center">
<img src="/images/asilomar2025_link_priority_optimization.png" alt="Congestion mitigation through link-priority optimization" width="80%">
<br><em>Figure 3. Gradient-based optimization of link priorities (contending aggressiveness) for congestion migitation.</em>
</div>

This approach offers a scalable analytical foundation for **next-generation, self-organizing wireless networks**, bridging classical optimization and modern differentiable modeling.  

**Preprint and code will be released soon.**
