---
title: "Delay-Oriented Distributed Scheduling using Graph Neural Networks"
category: 'conference'
collection: publications
permalink: /publications/2021-10-07-delay-oriented-distributed-scheduling-using-gcn.html
excerpt: 'We develop a machine learning method to solve a series of dependent combinatorial optimization problems embedded in a Markov Decision Process. This formulation applies to many problems in wireless networking and operational research. So far, researchers can attack only one of them but their combination.'
date: 2022-05-07
venue: 'IEEE ICASSP 2022'
paperurl: 'https://doi.org/10.1109/ICASSP43922.2022.9746926'
citation: 'Zhongyuan Zhao, Gunjan Verma, Ananthram Swami, Santiago Segarra, &quot; Delay-Oriented Distributed Scheduling Using Graph Neural Networks,&quot; <i>IEEE ICASSP 2022</i>, pp. 8902-8906, doi: 10.1109/ICASSP43922.2022.9746926.'
---

We develop a machine learning method to solve a series of dependent combinatorial optimization problems embedded in a Markov Decision Process. This formulation applies to many problems in wireless networking and operational research. So far, researchers can attack only one of them, either a series of independent combinatorial problems or a Markov Decision Process without combinatorics in decision making. In addition, the generalizability of graph neural networks enables the trained pipeline to work for different/dynamic topologies without retraining.


<iframe width="560" height="315" src="https://www.youtube.com/embed/lZscLy16TFY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

- [IEEEXplore](https://doi.org/10.1109/ICASSP43922.2022.9746926)
- Preprint [arXiv: 2111.07017](https://arxiv.org/pdf/2111.07017)
- [Slides](/files/Zhao_DelayScheduling_ICASSP22.pdf) 
- [Source code](https://github.com/zhongyuanzhao/gcn-dql)
- Related conference paper [Distributed scheduling using graph neural networks](/publications/2021-01-30-DGCN.html)


## Abstract

In wireless multi-hop networks, delay is an important metric for many applications. However, the max-weight scheduling algorithms in the literature typically focus on instantaneous optimality, in which the schedule is selected by solving a maximum weighted independent set (MWIS) problem on the interference graph at each time slot. These myopic policies perform poorly in delay-oriented scheduling, in which the dependency between the current backlogs of the network and the schedule of the previous time slot needs to be considered. To address this issue, we propose a delay-oriented distributed scheduler based on graph convolutional networks (GCNs). In a nutshell, a trainable GCN module generates node embeddings that capture the network topology as well as multi-step lookahead backlogs, before calling a distributed greedy MWIS solver. In small- to medium-sized wireless networks with heterogeneous transmit power, where a few central links have many interfering neighbors, our proposed distributed scheduler can outperform the myopic schedulers based on greedy and instantaneously optimal MWIS solvers, with good generalizability across graph models and minimal increase in communication complexity.



