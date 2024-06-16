---
layout: project
title: Enabling Multi-priority Coding in LED-based Optical Camera Communications
description: We propose a novel hierarchical coding scheme named as OnionCode to support dynamic range of channel capacity in one-to-many OCC scenario.
img: assets/img/project-onioncode-cover.png
importance: 2121
category: research
date: 2021-10-21
show: true

authors:
  - name: Haonan Wu
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yi-Chao Chen
    url: "https://www.cs.sjtu.edu.cn/~yichao/pmwiki/pmwiki.php"
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Guangtao Xue
    url: "https://www.cs.sjtu.edu.cn/~xue-gt/"
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Guangtao Xue
    url: "https://www.cs.sjtu.edu.cn/~xue-gt/"
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yuehu Jiang
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Ming Wang
    affiliations:
      name: University of Illinois at Urbana-Champaign
  - name: Shiyou Qian
    url: "https://www.cs.sjtu.edu.cn/PeopleDetail.aspx?id=339"
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Jiadi Yu
    url: "https://www.cs.sjtu.edu.cn/~jdyu/"
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Pai-Yen Chen
    url: "https://paiyenchen.com/"
    affiliations:
      name: University of Illinois at Chicago
    
---

## Abstract

Optical camera communication (OCC) has attracted increasing attention recently thanks to the wide usage of LED and high-resolution cameras. The lens-image sensor structure enables the camera distinguish light from various source, which is ideal for spatial MIMO. Hence, OCC can be applied to several emerging application scenarios, such as vehicle and drone communications. However, distance is a major bottleneck for OCC system, because the increase in distance makes it difficult for the camera to distinguish adjacent LEDs, which we call LED spatial mixing. 

In this paper, we propose a novel hierarchical coding scheme named as OnionCode to support dynamic range of channel capacity in one-to-many OCC scenario. OnionCode adopts a multi-priority receiving scheme, i.e., the receivers can dynamically discard the low-priority bit streams according to the measured channel capacity. OnionCode achieves this based on a key insight that, the luminance level of a mix-LED is distinguishable. We prototype a LED-based OCC system to evaluate the efficacy of OnionCode and the results show that OnionCode achieves a higher coding efficiency and overall throughput compared with the existing hierarchical coding


***

## Introduction

LED spatial mixing can significantly impair the efficiency of OCC (Optical Camera Communication) one-to-many communications. As shown in `Fig. 1(a)`, if a camera (i.e., a receiver) is close to the transmitter, the LEDs can be clearly distinguished, resulting in higher channel capacity. As the distance increases, the channel capacity will decrease due to stronger spatial mixing. Thus, in a one-to-many communication, if the transmitter sends at the data rate of the nearest receiver, the more distant receiver affected by spatial mixing will not receive any data; on the other hand, if the transmitter limits the data rate according to the farthest receiver, it will waste part of the channel capacity of the closer receivers.

OnionCode adopts a multipriority receiving shown in `Fig. 1(b)`, i.e., a specific priority is assigned to the bit stream transmitted by each LED, and the remote receivers discard the low-priority streams layer by layer, because of which we name it as OnionCode. For example, a short-distance receiver (layer 1) can reserve all 4 streams without data rate loss, but a long-distance receiver (layer 4) cannot decode 3 low-priority streams due to severe mixing.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project-onioncode-cover.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1 OnionCode: (a) Multiple receivers at various distance can receive the bits transmitted by the transmitter simultaneously and the receiver cannot distinguish the luminance of each LED due to spatial mixing; (b) The receiver discards low-priority bit streams according to the mixing status.
</div>


For the ease of understanding, we depict the transmission model of OnionCode in `Fig. 2`. OnionCode assumes that a multi-priority bitstream (4 priority levels) is being sent by the transmitter. For each symbol period, we take one bit from each bit streams to form the sending bits $$ DT = 0101 $$. Then, $$ DT $$ is mapped through an encoding table $$ EnT $$ to the LED on/off states $$ LT = 1011 $$ (1 for on and 0 for off). The LED light passes through the optical channel and a receiver camera in layer 3 observes the LED state as $$ LR_3 = 1[011] $$, where '1' indicates that the first LED is independent and lit, and $$ '[011]' $$ indicates that the next three LEDs are mixed with two of them lit. The receiver decodes $$ LR_3 $$ according to a decoding table dedicated to layer 3 ($$ DeT_3 $$), and get the resultant bit $$ DR_3 = 01XX $$. The 'X' means that the corresponding bit stream is discarded due to low priority, and the receiver can receive the bit streams of highest and second highest priority. Next, we further explain the concepts and variable definitions mentioned above.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/project-onioncode-transmodel.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 2 Transmission model of OnionCode (L = 4).
</div>

The key design elements of ONOINCODE is the encoding/decoding tables mentioned above, welcom to read our paper for more details!


***

## Publication

<div hidden>
{% cite wu-infocom22 %}
</div>


