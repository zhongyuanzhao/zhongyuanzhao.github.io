---
title: "Link Scheduling using Graph Neural Networks"
category: 'preprint'
collection: publications
permalink: /publications/2021-07-30-link-scheduling-using-gcn.html
excerpt: 'We leverage the power of Graph Convolutional Networks in encoding topological information into node embeddings, to enhance the existing algorithmic frameworks of distributed greedy scheduler as well as centralized tree search for solving maximum weighted independent set (MWIS) problem in an efficient and approximate manner. This improves the performance of both distributed and centralized link scheduling in wireless multi-hop networks.'
date: 2021-07-30
venue: 'arXiv'
paperurl: 'https://arxiv.org/abs/2109.05536'
citation: 'Zhongyuan Zhao, Gunjan Verma, Chirag Rao, Ananthram Swami, Santiago Segarra, &quot; Link Scheduling Using Graph Neural Networks,&quot; submitted to <i>IEEE Journal of Selected Topics in Signal Processing</i>, Preprint arXiv:2109.05536.'
---

Abstract
===
Efficient scheduling of transmissions is a key problem in wireless networks. The main challenge stems from the fact that optimal link scheduling involves solving a maximum weighted independent set (MWIS) problem, which is known to be NP-hard. For practical link scheduling schemes, centralized and distributed greedy heuristics are commonly used to approximate the solution to the MWIS problem. However, these greedy schemes mostly ignore important topological information of the wireless network. To overcome this limitation, we propose fast heuristics based on graph convolutional networks (GCNs) that can be implemented in centralized and distributed manners. Our centralized MWIS solver is based on tree search guided by a trainable GCN module and 1-step rollout. In our distributed MWIS solver, a trainable GCN module learns topology-aware node embeddings that are combined with the network weights before calling a distributed greedy solver. Test results on medium-sized wireless networks show that a GCN-based centralized MWIS solver can reach a near-optimal solution quickly. Moreover, we demonstrate that a shallow GCN-based distributed MWIS scheduler can reduce by nearly half the suboptimality gap of the distributed greedy solver with minimal increase in complexity. The proposed scheduling solutions also exhibit good generalizability across graph and weight distributions.


_Key words_: Maximum weighted independent set; graph convolutional network; wireless network; scheduling

Related conference publication: [Distributed scheduling using graph neural networks](/publications/2021-01-30-DGCN.html)


