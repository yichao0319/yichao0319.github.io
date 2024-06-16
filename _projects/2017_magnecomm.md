---
layout: project
title: Near-filed communication via EM side-channel
description: A novel near-filed communication that utilizes EMI signals emitted from CPUs to transmit data and magnetometers on mobile devices to receive data.
img: assets/img/project-magnecomm-cover.png
importance: 2017
category: research
date: 2017-10-16
show: true

authors:
  - name: Hao Pan
    url: "https://haopan.netlify.app/"
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yi-Chao Chen
    url: "https://yichao0319.github.io/"
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Guangtao Xue
    url: "https://www.cs.sjtu.edu.cn/~xue-gt/"
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Xiaoyu Ji
    url: "https://sites.google.com/site/xiaoyuijh/home"
    affiliations: 
      name: Zhejiang University

---


## Abstract

Near-field communication (NFC) plays a crucial role in the operation of mobile devices to enhance applications such as payment, social networks, private communication, gaming, and etc. Despite of the convenience, existing NFC standards like ISO-13157 require additional hardware (e.g., loop antenna and dedicated chip) and thereby hindering their wide-scale applications. In this work, we seek to propose a novel near-field communication protocol, MagneComm, which utilizes Magnetic Induction (MI) signals emitted from CPUs and captured by magnetometers on mobile devices for communication. Since CPUs and magnetometers are readily available components in mobile devices, MagneComm eliminates the requirement for special hardware and complements existing near-field communication protocols by providing additional bandwidth. We systematically analyze the characteristics of magnetic signals of CPUs and facilitate MagneComm with one-way communication, full-duplex communication, and multi-transmitter schemes in accordance with the hardware availability on devices. We prototype MagneComm on both laptops and smartphones. Extensive evaluation results show that MagneComm achieves up to 110 bps within 10 cm.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project-magnecomm-cover.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>



***

## Publication

<div hidden>
{% cite pan-mobicom17 %}
{% cite xue-tmc21 -f journal %}
</div>


