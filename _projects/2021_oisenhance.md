---
layout: project
title: Optical Image Stabilization -- Unlocking Hidden Potentials of Your Smartphone Camera
description: Optical Image Stabilization (OIS), initially designed to reduce camera shake and enhance photo clarity, can now revolutionize how we interact with everyday technology. By controlling OIS in innovative ways, we unlock capabilities such as precise depth sensing and image super-resolution, significantly enhancing smartphone photography and enabling new applications without additional hardware.
img: assets/img/projects/project-oisenhance-cover.png
importance: 2021.9
category: research
date: 2022-03-26
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
  - name: Feitong Tan
    url: ""
    affiliations:
      name: Simon Fraser University
  - name: Guangtao Xue
    url: "https://www.cs.sjtu.edu.cn/~xue-gt/"
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Wenhao Li
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Gaoang Huang
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Qingyang Li
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Xiaoyu Ji
    url: "https://sites.google.com/site/xiaoyuijh/home"
    affiliations: 
      name: Zhejiang University
  - name: Lili Qiu
    url: "https://www.cs.utexas.edu/~lili/"
    affiliations:
      name: University of Texas at Austin


---

## Abstract

Optical Image Stabilization (OIS), initially designed to reduce camera shake and enhance photo clarity, can now revolutionize how we interact with everyday technology. By controlling OIS in innovative ways, we unlock capabilities such as precise depth sensing and image super-resolution, significantly enhancing smartphone photography and enabling new applications without additional hardware.

## What is OIS?

Optical Image Stabilization (OIS) is a common feature in modern smartphones, designed to compensate for hand movements during photography, reducing blurriness in captured images. It achieves this by physically moving the camera lens slightly to counteract motion detected by built-in sensors. `Fig. 1` illustrates the lens-shift OIS architecture, where the camera lens position is dynamically adjusted based on gyroscope readings.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-oisenhance-cover.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-oisenhance-docam-01.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
Fig. 1  Optical Image Stabilization (OIS) and the working principle.
</div>



## Benefits of Controlling OIS

If we can actively control OIS, we go beyond reducing blur to precisely manipulate the lens movements, enabling novel functionalities like depth measurement and high-resolution imaging, without the need for specialized hardware such as multiple lenses or dedicated depth sensors.


---

## Super Resolution Imaging with OIS (OISSR)

While standard smartphone cameras face resolution limits due to hardware constraints, the **OISSR** system overcomes these by leveraging precise lens movements enabled by OIS. As shown in `Fig. 2`, by acoustically injecting signals into the built-in gyroscope, OISSR finely controls lens positioning, allowing multiple low-resolution captures to align precisely and combine into a high-resolution image.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-oisenhance-oissr-01.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
Fig. 2  OISSR applies acoustic injection to alter the built-in MEMS gyroscope readings to control the lens motion in OIS-supported cameras and further enables the sub-pixel alignments of multiple frames to facilitate merging into a super-resolution image. 
</div>

We sought to control the MEMS gyroscope readings for the reason that: the acoustic sinusoidal signals that can control gyroscope readings should be close to resonance frequency of the sensing mass, which mainly ranges from $18kHz$ to $30kHz$ and is friendly and inaudible to human ears. By contrast, the acoustic signals required to affect accelerome ters would be well within the audible range ($2kHz$-$10kHz$), which brings acoustic noise to the human ear. A Xiaomi 10Ultra is used as a test device here. We first identify the resonance frequency (i.e., around $18.79kHz$) of the built-in MEMS gyroscope via frequency sweeping. We then use the built-in speaker to play a .wav file of a sinusoidal acoustic signals with the same resonance frequency of the MEMS gyroscope. Android APIs are used to collect 6-axis IMU readings at a sampling rate of 200 𝐻𝑧, and the offset angles calculated from the 3-axis gyroscope readings (actual angular velocity). The lens position is then controlled by the OIS module with these offset angles as shown in `Fig. 3`.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-oisenhance-oissr-02.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
Fig. 3  Corresponding results with a stationary Xiaomi10 Ultra smartphone (fixed on the tripod) under the effects of acoustic signals (start at $0.5$ seconds) with frequencies of $18795Hz$ that played by the built-in speaker.
</div>


The system captures multiple frames while the lens is subtly moved, creating different pixel alignments. These frames are then merged using advanced algorithms to produce enhanced images with superior clarity and detail. The results, shown in `Fig. 4`, clearly demonstrate the significant quality enhancement achieved by OISSR, producing sharp, detailed images that far exceed typical camera capabilities. OISSR achieves remarkable improvements in clarity, enhancing resolution by a factor of four and dramatically reducing noise, making it highly effective in everyday scenarios such as detailed landscape photography and clear textual documentation.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-oisenhance-oissr-03.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
Fig. 4  Visual comparison of standard vs. OISSR-enhanced images.
</div>


---

## Depth Sensing with OIS-controlled Lens Motion (DoCam)

Smartphones typically rely on specialized sensors for 3D measurements, but these have limitations such as sensitivity to ambient light and limited operational range. The **DoCam** system cleverly exploits controlled OIS lens movements, transforming a regular RGB camera into an effective depth-sensing device. The system modulates the smartphone's built-in MEMS gyroscope via acoustic signals, controlling the lens position for precise depth reconstruction.

The key innovation is a Structure from OIS-controlled Motion (SfOM) algorithm, enhancing traditional 3D reconstruction by accurately estimating the camera's position and depth map using minimal lens movement. This precise lens control significantly improves the accuracy of depth sensing, offering a robust solution for applications like augmented reality and secure facial recognition. The DoCam system demonstrates exceptional performance, as shown in `Fig. 5`, providing accurate depth maps suitable for both indoor and outdoor environments, vastly improving the capabilities of standard smartphone cameras without additional hardware.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-oisenhance-docam-02.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
Fig. 5  End-to-end dense depth map comparison of our proposed DoCam and other depth estimation systems.
</div>


---

## Demo Video

<div class="embed-responsive embed-responsive-16by9">
  <iframe class="embed-responsive-item" width="560" height="315"
    src="https://www.youtube.com/embed/IZ1_tr5mquQ?si=1U65045dewqq1QNl" frameborder="0"
    allowfullscreen=""></iframe>
</div>

---

## Publication

<div hidden>
{% cite pan-mm22 %}
{% cite pan-mobicom22 %}
{% cite lu-sensys24 %}
</div>


