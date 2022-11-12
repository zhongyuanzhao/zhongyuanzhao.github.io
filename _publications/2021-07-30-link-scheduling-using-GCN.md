---
title: "Link Scheduling using Graph Neural Networks"
category: 'journal'
collection: publications
permalink: /publications/2021-07-30-link-scheduling-using-gcn.html
excerpt: 'We leverage the power of Graph Convolutional Networks in encoding topological information into node embeddings, to enhance the existing algorithmic frameworks of distributed greedy scheduler as well as centralized tree search for solving maximum weighted independent set (MWIS) problem in an efficient and approximate manner. This improves the performance of both distributed and centralized link scheduling in wireless multi-hop networks.'
date: 2021-07-30
venue: 'arXiv'
paperurl: 'https://arxiv.org/abs/2109.05536'
citation: 'Zhongyuan Zhao, Gunjan Verma, Chirag Rao, Ananthram Swami, Santiago Segarra, &quot; Link Scheduling Using Graph Neural Networks,&quot; accepted to <i>IEEE Transactions on Wireless Communications</i>, Preprint arXiv:2109.05536.'
---

Abstract
===
Efficient scheduling of transmissions is a key problem in wireless networks. 
The main challenge stems from the fact that optimal link scheduling involves solving a maximum weighted independent set (MWIS) problem, which is known to be NP-hard. 
In practical schedulers, centralized and distributed greedy heuristics are commonly used to approximately solve the MWIS problem.
However, these greedy heuristics mostly ignore important topological information of the wireless network.
To overcome this limitation, we propose fast heuristics based on graph convolutional networks (GCNs) that can be implemented in centralized and distributed manners.
Our centralized heuristic is based on tree search guided by a GCN and 1-step rollout.
In our distributed MWIS solver, a GCN generates topology-aware node embeddings that are combined with per-link utilities before invoking a distributed greedy solver. 
Moreover, a novel reinforcement learning scheme is developed to train the GCN in a non-differentiable pipeline.
Test results on medium-sized wireless networks show that our centralized heuristic can reach a near-optimal solution quickly, and our distributed heuristic based on a shallow GCN can reduce by nearly half the suboptimality gap of the distributed greedy solver with minimal increase in complexity. 
The proposed schedulers also exhibit good generalizability across graph and weight distributions.


_Key words_: MWIS; graph convolutional network; wireless networks; scheduling; reinforcement learning

Related conference publication: [Distributed scheduling using graph neural networks](/publications/2021-01-30-DGCN.html)

## Update (Nov 11, 2022)
The paper has been accepted to IEEE Transactions on Wireless Communications.

## Update (May 18, 2022)

We recently update the training method. Previously, we use a customized reinforcement learning scheme to train the graph convolutional networks in the downstream pipeline. Now, we reformulate the training of GCN to deterministic policy gradient, and use a proxy vector for credit assignment across nodes on the graph. It still falls in to the centralized training, distributed execution paradigm. But it turns an off policy to on policy. This new training scheme slightly improves the performance of deeper GCNs, but it is more theoretically sound. The detailed deduction is in the updated preprint, Section VI. 
