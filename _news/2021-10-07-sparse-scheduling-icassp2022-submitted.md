---
title: '"Distributed Link Sparsification for Scalable Scheduling Using Graph Neural Networks" submitted to ICASSP 2022.'
date: 2021-10-07
collection: news
permalink: /news/2021/10/sparse-scheduling-submitted-to-icassp-2022/
tags:
  - wirless ad-hoc networks
  - graph neural networks
  - wireless multi-hop networks
  - link scheduling
  - massive access
  - news
---

If you ever being in a crowded café or stadium, you may have experienced slow or broken Internet even with full signal on your smartphone or laptop. 
This phenomenon boils down to a small scheduling overhead for every connection to the network.
This overhead is not a big deal in wired networks, but for wireless networks, the per-connection overhead is typically proportional to the number of devices sharing the medium.
That means you can not get 1/N share of the total bandwidth in wireless networks, where N is the number of active users. 
In fact, if you keep increasing the number of wireless devices, the overhead will eventually take up all the spectrum, and the network is congested at the air-interface. 
That's a big problem.
 
Now, imagine that there are 10 million wireless connections per $km^2$ by 2030, mostly from Internet-of-Things (IoT) devices, nothing could get through the network even if their total traffic demand is theoretically well below the bandwidth of the network.
This is one of the biggest challenges for 5G and beyond wireless networks, termed as 'massive access' or 'massive connectivity'. (ref. [Chen 2021])
 
In this submitted manuscript, we come up with a scalable scheduling scheme with reduced overhead for wireless multihop networks.
Generally, our solution can reduce the overhead by two orders of magnitude while retain almost $70\%$ of the network capacity, and is applicable to both synchronized and random access networks.
Wireless multihop networks are infrastructureless, self-organized wireless networks, which have been used for wireless networks in harsh/hostile environments, e.g. military communications, disaster relief, environmental and border monitoring.
In the future wireless ecosystem, wireless multihop networks will also play a bigger role, e.g., to support IoT, connected vehicles, drones, wireless backhaul for 5G and beyond (small cells, mmWave, satellite constellation). (ref. [Akyildiz 2022])

The highlight of this work is the methodology of using Graph Neural Networks to generate node embeddings for localized decision functions. This idea can be traced back to Jürgen Schmidhuber's paper in 1991 in which a slow neural network generates weights for a fast neural network (ref. [FWP0]). Checkout his recent post [26 March 1991: Neural nets learn to program neural nets with fast weights—like today's Transformer variants. 2021: New stuff!](https://people.idsia.ch/~juergen/fast-weight-programmer-1991-transformer.html). 

The preprint and source code will hopefully be online soon. Thanks for the help of my co-authors, Gunjan Verma, Ananthram Swami, and Santiago Segarra, to put this together. 

---
- [Chen 2021] X. Chen, D. W. K. Ng, W. Yu, E. G. Larsson, N. Al-Dhahir,and R. Schober, “Massive access for 5g and beyond,”IEEE Journal of Selected Areas in Communications, vol. 39, no. 3, pp. 615–637, 2021.
- [Akyildiz 2022] I. F. Akyildiz, A. Kak, and S. Nie, “6G and beyond: The future of  wireless  communications  systems,” IEEE  Access,  vol.  8,pp. 133995–134030, 2020.
- [FWP0] J.  Schmidhuber. Learning to control fast-weight memories: An alternative to recurrent nets. Technical Report FKI-147-91, Institut für Informatik, Technische Universität München, 26 March 1991. [PDF](https://people.idsia.ch/~juergen/FKI-147-91ocr.pdf). 