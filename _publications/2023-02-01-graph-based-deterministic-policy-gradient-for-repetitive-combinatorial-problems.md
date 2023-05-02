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


