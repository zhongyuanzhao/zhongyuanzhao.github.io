---
title: "Delay-Oriented Distributed Scheduling using Graph Neural Networks"
category: 'preprint'
collection: publications
permalink: /publications/2021-10-07-delay-oriented-distributed-scheduling-using-gcn.html
excerpt: ''
date: 2021-10-07
venue: 'arXiv'
paperurl: 'https://arxiv.org/abs/2111.07017'
citation: 'Zhongyuan Zhao, Gunjan Verma, Ananthram Swami, Santiago Segarra, &quot; Delay-Oriented Distributed Scheduling Using Graph Neural Networks,&quot; submitted to <i>IEEE ICASSP 2022</i>, arXiv: 2111.07017'
---


## Abstract

In wireless multi-hop networks, delay is an important metric for many applications. However, the max-weight scheduling algorithms in the literature typically focus on instantaneous optimality, in which the schedule is selected by solving a maximum weighted independent set (MWIS) problem on the interference graph at each time slot. These myopic policies perform poorly in delay-oriented scheduling, in which the dependency between the current backlogs of the network and the schedule of the previous time slot needs to be considered. To address this issue, we propose a delay-oriented distributed scheduler based on graph convolutional networks (GCNs). In a nutshell, a trainable GCN module generates node embeddings that capture the network topology as well as multi-step lookahead backlogs, before calling a distributed greedy MWIS solver. In small- to medium-sized wireless networks with heterogeneous transmit power, where a few central links have many interfering neighbors, our proposed distributed scheduler can outperform the myopic schedulers based on greedy and instantaneously optimal MWIS solvers, with good generalizability across graph models and minimal increase in communication complexity.


Preprint [arXiv: 2111.07017](https://arxiv.org/pdf/2111.07017)

Related conference publication: [Distributed scheduling using graph neural networks](/publications/2021-01-30-DGCN.html)


