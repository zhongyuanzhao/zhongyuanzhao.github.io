---
title: '"Actor-Twin Framework for Task Graph Scheduling" accepted to Adaptive and Learning Agents Workshop at AAMAS 2025.'
date: 2025-04-02
collection: news
permalink: /news/2025/04/actor-twin-framework-for-task-graph-scheduling-accepted-to-ala25/
tags:
  - cloud computing 
  - edge computing 
  - computation offloading
  - task graph scheduling
  - news
---

Narjes Nourzad, Jared Coleman, Zhongyuan Zhao, Bhaskar Krishnamachari, Gunjan Verma, Santiago Segarra, “Actor-Twin Framework for Task Graph Scheduling”, accepted to Adaptive and Learning Agents Workshop at 24th International Conference on Autonomous Agents and Multiagent Systems (AAMAS), 2025.

- Paper <https://openreview.net/forum?id=DxpdovAY8Y> 

## Abstract

Task graph scheduling involves efficiently assigning computational tasks to available processors while ensuring the correctness of the result. As this problem is NP-hard and not polynomial-time approximable, traditional scheduling relies on heuristics. Although these methods can be effective, they often lack efficiency and fall short in generalizing well across different graph sizes and structures. Moreover, they are incompatible with optimization techniques that rely on backpropagation, limiting their adaptability to modern gradient-based approaches. In this paper, we present a novel Actor-Twin framework that integrates Multi-Branch Graph Convolutional Networks (MB-GCNs) with an Actor-Critic approach to overcome the nondifferentiable nature of heuristic-based scheduling. The heart of our framework is the Actor-Twin Scheduler (ACTS) module, which generates a task score via the MB-GCN actor that is subsequently used by a heuristic for scheduling. To facilitate gradient-based training of the actor, we incorporate a differentiable twin component that approximates heuristic decisions. We also introduce a systematic graph representation for task-server assignments that is compatible with gradient-based optimization. Experimental results show that Actor-Twin consistently outperforms traditional heuristic scheduling approaches in both average and variance of makespan

