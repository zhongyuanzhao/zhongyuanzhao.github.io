---
title: "Actor-Twin Framework for Task Graph Scheduling"
category: 'conference'
collection: publications
permalink: /publications/2025-04-02-actor-twin-framework-for-task-graph-scheduling.html
excerpt: 'The Actor-Twin framework leverages an actor-critic-based multi-branch GCN architecture with a twin mechanism to improve task scheduling efficiency by reducing makespan in complex and dynamic environments.'
date: 2025-04-02
venue: 'Adaptive and Learning Agents (ALA) Workshop, AAMAS 2025'
paperurl: 'https://openreview.net/pdf?id=DxpdovAY8Y'
citation: 'Narjes Nourzad, Jared Coleman, Zhongyuan Zhao, Bhaskar Krishnamachari, Gunjan Verma, and Santiago Segarra, &quot; Actor-Twin Framework for Task Graph Scheduling,&quot; <i>The Seventeenth Workshop on Adaptive and Learning Agents, AAMAS 2025</i>, pp 1-10, April 2025'
---


- Paper url <https://openreview.net/forum?id=DxpdovAY8Y>

## Abstract

Task graph scheduling involves efficiently assigning computational tasks to available processors while ensuring the correctness of the result. As this problem is NP-hard and not polynomial-time approximable, traditional scheduling relies on heuristics. Although these methods can be effective, they often lack efficiency and fall short in generalizing well across different graph sizes and structures. Moreover, they are incompatible with optimization techniques that rely on backpropagation, limiting their adaptability to modern gradient-based approaches. In this paper, we present a novel Actor-Twin framework that integrates Multi-Branch Graph Convolutional Networks (MB-GCNs) with an Actor-Critic approach to overcome the nondifferentiable nature of heuristic-based scheduling. The heart of our framework is the Actor-Twin Scheduler (ACTS) module, which generates a task score via the MB-GCN actor that is subsequently used by a heuristic for scheduling. To facilitate gradient-based training of the actor, we incorporate a differentiable twin component that approximates heuristic decisions. We also introduce a systematic graph representation for task-server assignments that is compatible with gradient-based optimization. Experimental results show that Actor-Twin consistently outperforms traditional heuristic scheduling approaches in both average and variance of makespan



```bibtex
@inproceedings{
nourzad2025actortwin,
title={Actor-Twin Framework for Task Graph Scheduling},
author={Narjes Nourzad and Jared Coleman and Zhongyuan Zhao and Bhaskar Krishnamachari and Gunjan Verma and Santiago Segarra},
booktitle={The Seventeenth Workshop on Adaptive and Learning Agents},
year={2025},
url={https://openreview.net/forum?id=DxpdovAY8Y}
}
```
