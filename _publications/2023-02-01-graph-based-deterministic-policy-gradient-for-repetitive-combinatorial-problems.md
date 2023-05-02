---
title: "Graph-based Deterministic Policy Gradient for Repetitive Combinatorial Optimization Problems"
category: 'conference'
collection: publications
permalink: /publications/2023-02-01-graph-based-deterministic-policy-gradient-for-rcop.html
excerpt: ''
date: 2023-02-01
venue: 'ICLR 2023'
paperurl: 'https://openreview.net/forum?id=yHIIM9BgOo'
citation: 'Zhongyuan Zhao, Ananthram Swami, Santiago Segarra, &quot; Graph-based Deterministic Policy Gradient for Repetitive Combinatorial Optimization Problems,&quot; <i>The 11th International Conference on Learning Representations (ICLR) 2023</i>, pp. 1-21.'
---


- The manuscript <https://openreview.net/forum?id=yHIIM9BgOo> (camera ready version uploaded on March 1st, 2023)
- Source code <https://github.com/XzrTGMu/twin-nphard>
- ICLR presentation [video](https://youtu.be/fK9zqsjNqvg), [slides](/files/GDPG-Twin-ICLR-2023-ID4014.pdf), [poster](/files/GDPG-Twin-ICLR-2023-ID4014.pdf)

<iframe width="560" height="315" src="https://www.youtube.com/embed/fK9zqsjNqvg" title="ICLR 2023 ID4014 presentation" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

## TL;DR:
A general learning framework is proposed to learn reusable node or edge representations that can reduce the optimality gap of fast heuristics for repetitive combinatorial optimization problems.

## Abstract:
We propose an actor-critic framework for graph-based machine learning pipelines with non-differentiable blocks, and apply it to repetitive combinatorial optimization problems (COPs) under hard constraints. Repetitive COP refers to problems to be solved repeatedly on graphs of the same or slowly changing topology but rapidly changing node or edge weights. Compared to one-shot COPs, repetitive COPs often rely on fast heuristics to solve one instance of the problem before the next one arrives, at the cost of a relatively large optimality gap. Through numerical experiments on several discrete optimization problems, we show that our approach can learn reusable node or edge representations to reduce the optimality gap of fast heuristics for independent repetitive COPs, and can optimize the long-term objectives for repetitive COPs embedded in graph-based Markov decision processes. Source code at https://github.com/XzrTGMu/twin-nphard 


## A brief introduction
In this paper, we develop a novel reinforcement learning framework, called graph-based deterministic policy gradient (GDPG), for discrete optimization problems in network settings, in which fast and/or distributed solutions are required or preferred. The novelty of this learning framework lies in the design of the downstream pipeline for inference and the introduction of a neural twin for back-propagation. Our downstream pipeline is quite different from popular centralized learning frameworks, such as Q-learning and Monte-Carlo tree search, in the sense that our policy network contains a non-differentiable component to support fast and/or distributed discrete operations. In order to train the non-differentiable policy network, we further introduce the idea of a neural twin of the non-differentiable policy network to build the critic network.

We then applied GDPG framework for two types of repetitive combinatorial optimization problems (R-COP): 1) R-COP with independent instances, and 2) R-COP embedded in a graph-based Markov decision process. We define the R-COP as a series of instances of a certain type of combinatorial optimization problem that share the same underlying graph/network topology but have different node/edge weights. R-COP is quite common in engineering systems but receives less attention than standalone COP, in which each instance is solved individually. Applications of R-COP include scheduling of links and jobs, routing for packets and vehicles, multi-object tracking in computer vision, etc. A common trait of R-COP in real-world applications is that they need to be solved repeatedly under stringent runtime (e.g., tens of milliseconds) and/or in a fully distributed manner. Existing machine learning approaches to standalone COP could not meet these practical requirements, since they are generally formulated in a centralized and sequential manner. Moreover, non-learnable conventional distributed algorithms could only address the first type of R-COP. The significance of this paper is that our GDPG framework can improve the quality of solutions for R-COPs with independent instances, and more importantly, it opens the door of addressing R-COPs embedded in graph-based Markov decision processes.

What is the significance of distributed solutions? In networked systems, especially when the multi-hop networks, distributed solutions are almost always preferred over centralized ones, because distributed solutions do not require the full network state to make decisions whereas the centralized ones do. This allows distributed solutions to be easily scaled up to larger networks. In addition, distributed solutions are free from single-point-of-failure due to the absence of a centralized server/base-station. As a result, despite their generally larger suboptimality gaps, distributed systems are more popular than centralized systems in the real-world. For example, Wi-Fi carries more Internet traffics than cellular networks despite that Wi-Fi protocol is less efficient in utilizing the radio spectrum. But the decentralized/distributed nature of Wi-Fi protocol makes it virtually free to everyone with very little maintenance compared to cellular data services. An intelligent distributed system can empower many exciting applications, such as 5G/6G wireless networks, robotic swarm, drone fleet, Internet-of-Things, smart transportation, smart grids, inventory management and logistic networks, and many other networked cyber-physical systems.