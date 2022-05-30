---
title: 'A Gentle Introduction to Distributed Link Scheduling in Self-organizing Wireless Networks: Part I'
date: 2022-05-29
permalink: /posts/2022/05/distributed-link-scheduling-part1/
tags:
  - wireless multihop networks
  - graph neural networks
  - link scheduling
  - orthogonal access
---

**Author: [Zhongyuan Zhao](https://zhongyuanzhao.com)**

As you came across this article, chances are that you are interested in wireless networks and/or machine learning.
This post is about using machine learning to improve wireless networks, especially when both of them run in fully distributed manners. In the first part, I will introduce the basic idea of self-organizing networks so that you could better understand the prerequisites of this work, such as why distributed solutions are emphasized.

## 1. What is self-organizing?

<figure>
<img src="https://i.imgur.com/zDyr3N4.jpg" alt="a busy cafe" style="width:600px" class="center">
<figcaption align = "center"><b>Fig.1 - As a social species, humans are self-organizing in public.</b> Source: <a href="https://upserve.com/restaurant-insider/keeping-restaurant-guests-happy-during-long-line-season1/">Upserve</a></figcaption>
</figure>



Imagining you and your friends are sitting in a crowded coffee shop, chatting on your favorite topics, with music and other ongoing conversations in the background. As humans, we can automatically perform such tasks without even noticing about it. But if you think about it, in order to have a meaningful conversation with others, we need to at least speak the same language and follow the same social rules of conversation. The importance of language is obvious, but the rules of conversation that we follow implicitly are often overlooked.

Social norm is the way we self-organize as a social species. We can form and maintain orders in public without an organizer giving us instructions at each moment. For example, in a conversation, we follow cultural rules to signal the other party when we are about to start or end a sentence, as well as to control  our volume in public spaces. Another example is our traffic system. As a driver, we have to follow traffic rules to avoid accidents, including signaling others before making turns or slowing down, controlling our speed, and monitoring the surroundings. Of course, we have to follow the signals of traffic lights and/or police at busy intersections. But in general, traffic system is mostly self-organized.

Wireless networks are analogous to the coffee shop scenario, where wireless devices talk to each other in the presence of background noise (music) and interferences (distractions from other conversations). **Roughly speaking, wireless communications deal with the language and attention between two devices, whereas wireless networking is about the social norms or rules.** However, wireless devices are dumb and can only act on what they are programmed to do. It may be too hard, too costly, or even unnecessary to program wireless devices to be self-organizing, especially in a busy and crowded environment.

## 2. What is (not) a self-organizing network?

Many engineering systems are organized top-down. For example, in railway systems and cellular networks, the physical and data traffics flow in pre-planned networks, following the instructions of dedicated schedulers. Without the infrastructure, the physical or data payloads can not move on their own. However, as long as the infrastructure is in place and functions properly, the entire system can be very efficient in resource utilization. Think about the average labor and energy costs of moving a passenger for 1 km by train and by cars. 

The infrastructure of the 5th generation (5G) cellular networks is called cloud radio access network (Cloud-RAN), as illustrated in Fig. 2. Cloud-RAN comprises base-stations connected to the telecommunication network and the Internet through wired/wireless fronthaul and backhaul networks. Each base-station provides network connectivity to mobile devices in a macro or small cell (see Fig. 2). Cellular network operators carefully plan and layout these cells in a market based on factors like population density and terrain, to optimize the coverage, bandwidth, cost, and flexibility of their cellular networks. This process is called _network optimization_.

<figure>
<img src="/images/5g_metis.jpeg" alt="infrastructure-based networks" style="width:600px" class="center">
<figcaption align = "center"><b>Fig.2 - Infrastructure-based network: 5G cloud radio access network (Cloud-RAN).</b></figcaption>
</figure>

To maximize the resource utilization in networks, such as bandwidth and energy, a cellular base-station schedules the transmission of mobile devices attached to it, and manages their radio parameters as well. 
To do so, cellular base-station is equipped with descent real-time computing power, dedicated backhaul network, and high performance radio transceivers.
To run a cellular network, it requires a huge upfront investment and years of construction, as well as continuous maintenance and upgrading. 

Unlike the cellular network, Wi-Fi networks are organized bottom-up. Anyone can install a Wi-Fi router (access point) at home.
The medium access control (MAC, or media access control) of Wi-Fi is self-organized, meaning that a Wi-Fi access point does not schedule transmissions or manage the parameters of the mobile devices attached to it. 
When a Wi-Fi device has data packets to transmit, it first listens to the medium (wireless channel) for a brief time, if there is no conversation in the background, it then starts transmission, otherwise it waits for a while and then tries again. 
The self-organizing feature of Wi-Fi makes a Wi-Fi access point a 1000 time cheaper than a cellular base-station, and that's why Wi-Fi is so successful. In fact, it is estimated that as of 2022, 51% of Internet traffic goes through Wi-Fi, while only 19.6% of that goes through cellular networks. [[Cisco VNI report, 2017-2022](https://twiki.cern.ch/twiki/pub/HEPIX/TechwatchNetwork/HtwNetworkDocuments/white-paper-c11-741490.pdf), Fig. 22] 
Even cellular network operators install Wi-Fi access points at hot spots to offload traffic from cellular networks.

However, the listen-before-talk approach used in Wi-Fi MAC only works for small networks. 
A Wi-Fi hot spot can be congested when there are lots of Wi-Fi devices around, not because their total demand of bandwidth exceed the capacity of the Wi-Fi access point, but too many collisions over-the-air. 
You may have experienced such congestions at café, hotel, or library.


## 3. Why self-organizing wireless networks?

In general, self-organizing wireless networks are more flexible but less efficient than planned infrastructure.
In many cases, having greater flexibility not only makes economic sense, but is also technically sound. 
The traditional examples are _wireless ad-hoc networks_ and _wireless sensor networks_ operating in harsh or hostile environments, such as battlefield (Fig. 1), disaster area, and remote locations, where the network infrastructure is infeasible. 

<figure>
<img src="/images/adhoc_military.png" alt="military ad-hoc networks" style="width:600px" class="center">
<figcaption align = "center"><b>Fig.1 - Wireless multihop networks: mobile ad hoc networks in military communications.</b></figcaption>
</figure>

In cellular and Wi-Fi networks, user devices are connected to wired infrastructure (Internet) via the base-station or access point in a single hop.
However, in wireless ad hoc networks, the sender and recipient of data packages are typically connected by other user devices over multiple hops. As a result, wireless ad hoc networks belong to _wireless multihop networks_, where 'hop' is only for wireless connections.

<figure>
<img src="/images/WMN_applications.png" alt="vehicles, drone fleets, drone bs, CubeSat" style="width:100%">
<figcaption align = "center"><b>Fig.3 - Applications of wireless multihop networks: (top left) vehicular communications, (top right) drone-assisted communications, (bottom left) drone swarm (bottom right) CubeSat constellation</b></figcaption>
</figure>


Wireless multihop networks are playing a bigger role in many emerging civilian applications, such as smart vehicles, drone fleets, the Internet of Things (IoT), and wireless backhaul networks for small cells, and drone and CubeSat-assisted wireless networks in 5G and beyond [Akyildiz 2022], as illustrated in Fig. 3.
For example, the exchange of safety-critical information (or control messages) among traveling vehicles (drones), as shown in upper left (bottom left) of Fig. 3, requires ultra-low latency and seamless network coverage. 
To meet such requirements, it is better to establish a direct connection between the neighboring vehicles (drones) rather than placing a base-station in the middle. 

In 5G and beyond, wireless multihop networks can also be the wireless backhaul network that connects the base-stations in small cells or carried by drones and CubeSats to the Internet (Fig. 3 right). 
Small cells are for highly populated hotspots, such as central business districts, schools, and residential areas (see Fig. 2), whereas drone and CubeSats-assisted wireless networks are for temporary hotspots and non-terrestrial communications (such as ocean, airplane, mountains, desert).
For small cells, wireless backhaul can avoid the high cost and inconvenience of installing wired backhaul.
For drone and CubeSat-assisted networks, wireless backhaul is the only option. [Akyildiz 2022]

Wireless multihop networks might help address the challenge of massive access [Chen 2021] in Internet of Things (IoT). 
In the future, the popularity of IoT devices could lead to very high connectivity density, e.g. 10 million wireless connections per $km^2$ by 2030 [Chen 2021], they need periodically send small payloads to its controller.
Although the real bandwidth required by these payloads is not high, the overheads of handshaking and authorization generated by these IoT devices under existing cellular architecture could consume all the bandwidth, jamming the entire network.
If these IoT devices can form self-organizing networks, the situation could be significantly improved.


## 4. Synchronization

Besides infrastructure, another dimension of the organization in wireless networks is synchronization.
In general, both infrastructure and synchronization can improve the resource efficiency and performance, at the cost of reduced flexibility.
We can further categorize wireless networks based on these two dimensions, as shown in the following table. 

|     | synchronized | random access |
|-----|--------------|---------------|
|Infrastructure | Cellular, 5G networks | Wi-Fi |
|Ad hoc | Vehicular/Flying/Tactical Ad-hoc Networks | Wireless Ad hoc / Sensor Networks| 

In synchronized networks, wireless devices are synchronized to the same clock, such as GPS signal, which enables them to communicate on accurately defined time slots without colliding with each other. 
Therefore, synchronized networks can achieve better performance in throughput, mobility, and resource efficiency. 
In random access networks, there is an additional overhead to establish a link between unsynchronized devices, which
limits the performance and resource efficiency. However, without the need of synchronization, it is very easy for devices in random access networks to self-organize. As a result, random access networks can offer greater flexibility, lower energy consumption, and lower cost of device. 

It should be noted that random access and synchronization are necessary for communications. In cellular protocols, there is a dedicated random access channel that allows new devices to join the network. In Wi-Fi and other random access networks, the receiver needs to synchronize itself to the transmitter in order to decode the data. 


## 5. Summary

In this part, I introduced the concept of self-organizing wireless networks, and its applications. The takeaway is that self-organizing wireless networks and infrastructure-based wireless networks have different priorities: the former emphasizes flexibility and reliability, the latter is primarily focused on performance and resource efficiency.
Therefore, the technical solutions for self-organizing wireless networks need to be infrastructureless, meaning that it should be implemented in a distributed manner. 
In the next part, I will introduce some basic networking solutions in wireless multihop networks, and how to use machine learning to improve them.  

## References

- [Chen 2021] X. Chen, D. W. K. Ng, W. Yu, E. G. Larsson, N. Al-Dhahir,and R. Schober, “Massive access for 5g and beyond,”IEEE Journal of Selected Areas in Communications, vol. 39, no. 3, pp. 615–637, 2021.
- [Akyildiz 2022] I. F. Akyildiz, A. Kak, and S. Nie, “6G and beyond: The future of  wireless  communications  systems,” IEEE  Access,  vol.  8,pp. 133995–134030, 2020.




