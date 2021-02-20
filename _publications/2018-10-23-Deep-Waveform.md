---
title: "Deep-Waveform: A Learned OFDM Receiver Based on Deep Complex Convolutional Networks"
category: 'preprint'
collection: publications
permalink: /publications/2018-10-23-Deep-Waveform.html
excerpt: 'This paper is about using complex valued deep neuron networks to implement the lower physical layer of OFDM-based wireless communications. It demonstrates that complex neuron networks could learn the complex waveform used in modern wireless network, and outperforms analytical channel estimation approach in Rayleigh fading under certain conditions.'
date: 2020-12-31
venue: 'Arxiv'
paperurl: 'https://arxiv.org/abs/1810.07181'
citation: 'Zhongyuan Zhao, Mehmet C. Vuran, Fujuan Guo, and Stephen Scott, &quot;Deep-Waveform: A Learned OFDM Receiver Based on Deep Complex Convolutional Networks,&quot; Arxiv preprint: 1810.07181'
---
Abstract
===
Recent work on deep learning for the physical layer (PHY) of wireless communications reveals the capabilities of deep neural networks in tasks like channel coding, modulation, and parametric estimation. However, it is unclear if deep neural networks could also learn the sophisticated waveforms in modern wireless communication systems, and potentially create new ones. In this paper, a Deep Complex Convolutional Network (DCCN) is developed to receive Orthogonal Frequency-Division Multiplexing (OFDM) signal from end to end without using explicit Discrete Fourier Transform (DFT), based on complex-valued neural networks and signal processing theory. The DCCN contains mostly linear-activated fully connected and convolutional layers, and is trained through two-stage transfer learning with an end-to-end loss function of bit-error-rate . Numerical experiments show that the DCCN receiver can learn the channel statistics, exploit redundancy in the cyclic prefix in OFDM waveform, and suppress intersymbol interference (ISI), thus achieve comparable and superior performance than the legacy receivers based on ideal Linear Minimum Mean Square Error (LMMSE) with prior channel knowledge and a conventional cyclic prefix-enhanced channel estimation in different Rayleigh fading channels, with a lower complexity of (N2). Moreover, the DCCN receiver generalizes well over multipath fading models with different Power-Delay Profiles. This work demonstrates the capability and synergistic advantage of deep neural networks in current and next-generation wireless communication systems.

_Keywords_: Wireless Communications, Physical Layer, Deep Learning, Artificial Neuron Networks, OFDM, Modulation

[Download paper here](https://arxiv.org/pdf/1810.07181.pdf)

History: first appear in Arxiv on Oct. 2018, submitted to IEEE JSAC Dec. 2020

Zhongyuan Zhao, Mehmet C. Vuran, Fujuan Guo, and Stephen Scott, "Deep-Waveform: A Learned OFDM Receiver Based on Deep Complex Convolutional Networks," Submitted to <i>IEEE Journal on Selected Areas in Communications</i> (under first revision), Dec. 2020, [Arxiv preprint: 1810.07181] [https://arxiv.org/abs/1810.07181](https://arxiv.org/abs/1810.07181)