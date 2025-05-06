---
title: '"Sparsity-enhanced Lagrangian Relaxation for Computation Offloading at the Edge" submitted to ACM Mobihoc 2025.'
date: 2025-04-08
collection: news
permalink: /news/2025/04/serl-for-edge-computing-submitted-to-mobihoc25/
tags:
  - iterative convex relaxation
  - computation offloading
  - multi-hop networks
  - joint offloading and routing
  - news
---

Negar Erfaniantaghvayi, Zhongyuan Zhao, Kevin Chan, Ananthram Swami, Santiago Segarra, “Sparsity-enhanced Lagrangian Relaxation for Computation Offloading at the Edge”, submitted to ACM Mobihoc 2025.

## Abstract

This paper introduces a novel computational approach for offloading sensor data processing tasks to servers in edge networks for better accuracy and makespan. 
A task is assigned with one of several offloading options, each comprises a server, a route for uploading data to the server, and a service profile that specifies the  performance and resource consumption at the server and in the network.
This offline offloading and routing problem is formulated as mixed integer programming (MIP), which is non-convex and HP-hard due to the discrete decision variables associated to the offloading options.
The novelty of our approach is to transform this non-convex problem into iterative convex optimization by relaxing integer decision variables into continuous space,  
combining primal-dual optimization for penalizing constraint violations and reweighted $L_1$-minimization for promoting solution sparsity, which achieves better convergence through a smoother path in a continuous search space. 
Compared to existing greedy heuristics, our approach can achieve a better Pareto frontier in accuracy and latency, scales better to larger problem instances, and can achieve a 7.72--9.17$\times$ reduction in  computational overhead of scheduling compared to the optimal solver in hierarchically organized edge networks with 300 nodes and 50--100 tasks.

- Preprint <https://arxiv.org/pdf/2505.00848>
- Source code available soon 
