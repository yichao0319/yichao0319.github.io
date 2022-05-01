---
layout: project
title: Knocking-based Object Identification
description: We propose a novel hierarchical coding scheme named as OnionCode to support dynamic range of channel capacity in one-to-many OCC scenario.
img: assets/img/project-knockid-cover.png
importance: 2020
category: research
date: 2020-01-31
show: false

authors:
  - name: Yezhou Wang
    url: "yezhouwang@sjtu.edu.cn"
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Runting Zhang
    url: "johnson_zrt@sjtu.edu.cn"
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Haonan Wu
    url: "haonanwu@sjtu.edu.cn"
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Guangtao Xue
    url: "gt_xue@sjtu.edu.cn"
    affiliations:
      name: Shanghai Jiao Tong University
    
---

## Abstract

With the popularization of smart homes, the number of intelligent home appliances boosts dramatically, leading to an increasing cost for users to identify certain device. One existing method takes advantage of the tags sold online, but it requires the mobile phone to support NFC and other related functions. Previous papers also proposed the feasible method supported by percussion sound. This intuitive method, however, requires large amounts of data re-collection in actual use, because the sound contains less characteristic information, as well as getting affected by user’s different tapping points and the assembly environment. Meanwhile, according to our experiments, re-training is necessary when the way of holding a mobile phone or the phone itself changes, resulting in excessively high usage costs. In this paper, for the first time, we introduce the method of acoustic simulation into the field of human-computer interaction for tap recognition. With tap recognition, the system can achieve extremely high accuracy with only the data of a single tap, which greatly reduces the use costs. In addition, the model copes well with changes in assembly and support, and performs greatly by different people with different mobile phones with a sharing function. Also, our method of simulation can be used to identify the tapping position, which provides a new idea of human-computer interaction.


***

## Usage Flow


<div class="row justify-content-sm-center">
    <div class="col-sm-5 mt-3 mt-md-0">
        {% include figure.html path="assets/img/project-knockid-usage.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
  Fig. 1 (a) The user loads the 3D model into the system; (b) The system automatically separate the model into components to which the user can bind customized functions; (c) The system instructs the user to knock on specific locations for registration.
</div>


In registration stage, a user need to load the 3D model of the objects he/she wants to identify. After loading, our system automatically separate the model into components to which the user can bind customized functions. Then the user knock at the object for several times to provide real world training data. Our system train a recognition model using the data provided by the user and the simulated sound using the 3D model.

Then, when the user knock at an object, the trained model can identify which object the user is knocking at and do some custom function such as turning on the smart device knocked at.


***

## System Overview

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.html path="assets/img/project-knockid-overview.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
  Fig. 2 System Overview.
</div>

In this section, we provide an overview of the proposed KnockID system. Similar to the previous acoustic-based object identification system such as [1], KnockID identifies the target objects by analyzing the unique acoustic feature excited by the smartphone-object collision. KnockID introduces sound synthesis technique as a data augmentation method into the training process, in order to offload the unfriendly process of data collection from users, which greatly extends the friendliness and usability of the whole system. To unleash the power of sound synthesis, we utilize the concept of few-shot learning and domain adaptation from the state-of-the-art deep learning method and design a two-stage pipeline as shown in Fig. 2. 

The sound simulator takes the object's 3D model and material-related parameters as inputs, and generates synthetic sound for the off-line and on-line training. In this paper, the domain of the data depends on the way it is generated and we define that the synthetic sound and the actual sound correspond to the target domain and the source domain respectively.

KnockID initializes with the off-line stage to generate a pre-trained model meeting the following two requirements: cross-domain feature extraction and sound similarity measurement, to cope with the aforementioned challenges of domain mismatch and unseen objects. Specifically, we first collect enough actual knocking samples manually and synthesize the corresponding sounds to build a pair-wise training set. After pre-processing, the extracted spectrogram is fed into the carefully designed neural network, and the multi-objective loss function forces the network to learn to measure the similarity between training samples while extracting domain-independent features. The off-line stage is usually termed as pre-training in few-shot learning and the purpose is to provide a baseline model with preliminary identification capability which will be further fine-tuned in the following on-line stage.

***

## Result

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/project-knockid-result.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
  Fig. 3 (a) The effects of phone on KnockID’s classification performance; (b) KnockID versus Knocker at the same user collected dataset size.
</div>

The result shows that using acoustic simulation to generate data, the system has high robustness and performs well on different mobile phones and with the enlarged dataset, our algorithm can still achieve 90.2% for training with only 3 taps, compared to only 19.8% accuracy for the original method.

***

## Reference

[1] Taesik Gong, Hyunsung Cho, Bowon Lee, and Sung-Ju Lee. Knocker: Vibroacoustic-based object recognition with smartphones. Proceedings of the ACM on Interactive, Mobile, Wearable and Ubiquitous Technologies, 3(3):1–21, 2019.

