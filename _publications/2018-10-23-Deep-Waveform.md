---
title: "Deep-Waveform: A Learned OFDM Receiver Based on Deep Complex-Valued Convolutional Networks"
category: 'journal'
collection: publications
permalink: /publications/2018-10-23-Deep-Waveform.html
excerpt: 'This paper is about using complex valued deep neuron networks to implement the lower physical layer of OFDM-based wireless communications. It demonstrates that complex neuron networks could learn the complex waveform used in modern wireless network, and outperforms analytical channel estimation approach in Rayleigh fading under certain conditions.'
date: 2021-06-07
venue: 'IEEE Journal on Selected Areas in Communications'
paperurl: 'https://doi.org/10.1109/JSAC.2021.3087241'
citation: 'Zhongyuan Zhao, Mehmet C. Vuran, Fujuan Guo, and Stephen Scott, &quot;Deep-Waveform: A Learned OFDM Receiver Based on Deep Complex-Valued Convolutional Networks,&quot; in IEEE Journal on Selected Areas in Communications, vol. 39, no. 8, pp. 2407-2420, Aug. 2021, doi: 10.1109/JSAC.2021.3087241.'
---
Abstract
===
The (inverse) discrete Fourier transform (DFT/ IDFT) is often perceived as essential to orthogonal frequency-division multiplexing (OFDM) systems. In this paper, a deep complex-valued convolutional network (DCCN) is developed to recover bits from time-domain OFDM signals without relying on any explicit DFT/IDFT. The DCCN can exploit the cyclic prefix (CP) of OFDM waveform for increased SNR by replacing DFT with a learned linear transform, and has the advantage of combining CP-exploitation, channel estimation, and intersymbol interference (ISI) mitigation, with a complexity of O(N^2) . Numerical tests show that the DCCN receiver can outperform the legacy channel estimators based on ideal and approximate linear minimum mean square error (LMMSE) estimation and a conventional CP-enhanced technique in Rayleigh fading channels with various delay spreads and mobility. The proposed approach benefits from the expressive nature of complex-valued neural networks, which, however, currently lack support from popular deep learning platforms. In response, guidelines of exact and approximate implementations of a complex-valued convolutional layer are provided for the design and analysis of convolutional networks for wireless PHY. Furthermore, a suite of novel training techniques are developed to improve the convergence and generalizability of the trained model in fading channels. This work demonstrates the capability of deep neural networks in processing OFDM waveforms and the results suggest that the FFT processor in OFDM receivers can be replaced by a hardware AI accelerator.

_Keywords_: Wireless Communications, Physical Layer, Deep Learning, Artificial Neuron Networks, OFDM, Modulation

- [Full paper on IEEEXplore](https://doi.org/10.1109/JSAC.2021.3087241)
- [Preprint](https://arxiv.org/abs/1810.07181)
- [Source code](https://github.com/zhongyuanzhao/dl_ofdm).

History: first appear in Arxiv on Oct. 2018, submitted to IEEE JSAC on Dec. 2020, published in IEEE JSAC on June 2021.

The majority of this work was completed during the Ph.D. studies of the author Zhongyuan Zhao at UNL. This work was supported by the NSF under Grant CNS-1731833.

Zhongyuan Zhao, Mehmet C. Vuran, Fujuan Guo, and Stephen Scott, "Deep-Waveform: A Learned OFDM Receiver Based on Deep Complex-Valued Convolutional Networks," in IEEE Journal on Selected Areas in Communications, vol. 39, no. 8, pp. 2407-2420, Aug. 2021, doi: 10.1109/JSAC.2021.3087241.