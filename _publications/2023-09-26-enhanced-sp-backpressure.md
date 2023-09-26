---
title: "Enhanced Backpressure Routing with Wireless Link Features"
category: 'conference'
collection: publications
permalink: /publications/2023-09-26-enhanced-sp-backpressure.html
excerpt: 'The latency and practicality of Backpressure routing algorithm based on shortest path bias is improved with three components: optimal bias scaling, low-overhead bias maintenance, and a delay-aware backlog metric. '
date: 2023-09-26
venue: 'IEEE CAMSAP'
paperurl: ''
citation: 'Zhongyuan Zhao, Gunjan Verma, Ananthram Swami, Santiago Segarra, &quot; Enhanced Backpressure with Wireless Link Features,&quot; accepted to <i>IEEE CAMSAP 2023</i>.'
---


Abstract
===
Backpressure (BP) routing is a well-established framework for distributed routing and scheduling in wireless multi-hop networks. 
However, the basic BP scheme suffers from poor end-to-end delay due to the drawbacks of slow startup, random walk, and the last packet problem. 
Biased BP with shortest path awareness can address the first two drawbacks, and sojourn time-based backlog metrics have been proposed for the last packet problem. 
Furthermore, these BP variations require no additional signaling overhead in each time step compared to the basic BP. 
In this work, we further address three long-standing challenges associated with the aforementioned low-cost BP variations, including optimal scaling of the biases, bias maintenance under mobility, and incorporating sojourn time awareness into biased BP.
Our analysis and experimental results show that proper scaling of biases can be achieved with the help of common link features, which can effectively reduce end-to-end delay of BP by mitigating the random walk of packets under low-to-medium traffic, including the last packet scenario.
In addition, our low-overhead bias maintenance scheme is shown to be effective under mobility, and our bio-inspired sojourn time-aware backlog metric is demonstrated to be more efficient and effective for the last packet problem than existing approaches when incorporated into biased BP. 


_Key words_: Backpressure routing, resource allocation, shortest path distance, queue length, sojourn time, delay-aware routing


This paper is related to our recent paper ["Delay-aware Backpressure Routing Using Graph Neural Networks"](/publications/2022-11-19-link-duty-cycle-backpressure.html) published in IEEE ICASSP 2023.





