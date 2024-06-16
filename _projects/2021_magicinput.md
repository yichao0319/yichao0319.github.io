---
layout: project
title: Magic Finger Input System
description: We propose a training-free text input system called MagicInput that support multiple languages using acoustic-based 1D finger tracking technology. An artificial dataset (called TrackMNIST) simulated from MNISTseries datasets is utilized to satisfy the various users' writing characteristics.
img: assets/img/project-magicinput-cover.png
importance: 2021.1
category: research
date: 2021-05-18
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
  - name: Qi Ye
    url: ""
    affiliations: 
      name: Shanghai Jiao Tong University
  - name: Guangtao Xue
    url: "https://www.cs.sjtu.edu.cn/~xue-gt/"
    affiliations:
      name: Shanghai Jiao Tong University

---


## Abstract

Text input systems based on device-free finger tracking technologies have attracted considerable attention in the use scenarios of mobile and the Internet-of-Things (IoT) devices. Issues pertaining to 2D tracking have prompted interest in using 1D finger trajectories for the recognition of handwritten letters. Nonetheless, 1D tracking imposes two major challenges, (i) Trajectory information loss from 2D to 1D; and (ii) Inter-user diversity in writing traits. These challenges could possibly be overcome by collecting a large training dataset for every user; however, this would impose an unacceptable burden on users. This paper presents a text input system with multi-language support without training using acoustic-based 1D finger tracking technology. We developed a novel data augmentation scheme, in which the handwritten image dataset MNISTs are used to create artificial datasets (called TrackMNISTs). We compensate for the trajectory information loss of 1D by creating personal dataset (from TrackMNIST) to match the writing habits of individual users. The proposed data augmentation mechanism is also applicable to multilingual letter recognition. In experiments, MagicInput achieved outstanding classification accuracy on unseen users, 10 digits (98.3%), 26 uppercase/lowercase English letters (97.8%/95.3%), 49 Japanese characters (91.4%), and the 30 commonly used Chinese characters (93.8%).

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/project-magicinput-cover.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


***

## Publication

<div hidden>
{% cite pan-ipsn21 %}
</div>

