---
layout: project
title: Utilizing Acoustic-based Imaging for Issuing Contact-Free Silent Speech Commands
description: A silent speech interface based on acoustic signals.
img: assets/img/project-endophasia-cover.png
importance: 2019
category: research
date: 2019-01-30
show: true

authors:
  - name: Yongzhao Zhang
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Wei-Hsiang Huang
    affiliations:
      name: National Chiao Tung University
  - name: Chi-Yun Yang
    affiliations:
      name: National Chiao Tung University
  - name: Wen-Ping Wang
    affiliations:
      name: National Chiao Tung University
  - name: Yi-Chao Chen
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Chuang-Wen You
    affiliations:
      name: National Taiwan University
  - name: Da-Yuan Huang
    affiliations:
      name: National Chiao Tung University
  - name: Guangtao Xue
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Jiadi Yu
    affiliations:
      name: Shanghai Jiao Tong University

---


## Abstract

Using silent speech to issue commands has received growing attention, as users can utilize existing command sets from voice-based interfaces without attracting other people’s attention. Such interaction maintains privacy and social acceptance from others. However, current solutions for recognizing silent speech mainly rely on camera-based data or attaching sensors to the throat. Camera-based solutions require 5.82 times larger power consumption or have potential privacy issues; attaching sensors to the throat is not practical for commercial-off-the-shell (COTS) devices because additional sensors are required. In this paper, we propose a sensing technique that only needs a microphone and a speaker on COTS devices, which not only consumes little power but also has fewer privacy concerns. By deconstructing the received acoustic signals, a 2D motion profile can be generated. We propose a classifier based on convolutional neural networks (CNN) to identify the corresponding silent command from the 2D motion profiles. The proposed classifier can adapt to users and is robust when tested by environmental factors. Our evaluation shows that the system achieves 92.5% accuracy in classifying 20 commands.

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.html path="assets/img/project-endophasia-use_case.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
  Fig. 1 Use case of Endophasia.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/project-endophasia-images.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
  Fig. 2 Example of reconstructed acoustic images of various silent commands.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.html path="assets/img/project-endophasia-system.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
  Fig. 3 System flow and the proposed training model.
</div>


***

## Demo Video



***

## Publication

<div hidden>
{% cite zhang-imwut20 -f journal %}
</div>


