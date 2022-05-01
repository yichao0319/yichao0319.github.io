---
layout: project
title: Applications of OIS beyond Image Stabilization
description: We explore the method to control optical image stabilization (OIS) module of phone camera without additional hardware and develop applications including depth maps and super-resolution images.
img: assets/img/project-oisenhance-cover.jpg
importance: 2021.9
category: research
date: 2022-03-26
show: false

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


## Summary

Smartphones are widely used for photography due to their portability and convenience. It’s reported that 90.9% of all photos are taken with smartphones in 2021, and a growing number of professional photographers are adopting mobile cameras as one of their primary photographic tools. To accommodate the diverse needs from casual photos of everyday life to professional photos, smartphone manufacturers have been enhancing phone cameras by installing more lenses, image sensors with larger and higher resolutions, depth sensors, etc. Upgrades to camera hardware have further facilitated new applications, including depth maps, 3D modeling, augmented reality, etc.; however, upgrades have also significantly increased the cost of smartphones. In this project, we show that, without adding additional hardware, we can enhance the functionality of existing smartphone cameras by controlling the Optical Image Stabilization (OIS) module.


***

## OISSR

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/project-oissr.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1 Top sub-figures show the original image captured by the Xiaomi 11Pro camera, whereas the bottom sub-figures show the super-resolution results obtained using the OISSR system.
</div>

We sought to develop a robust optical image stabilization based super resolution method (called OISSR) for use on smartphone cameras with OIS modules. After delving into the working principle of OIS, acoustic injection is used to alter the readings from the built-in MEMS gyroscope to control the lens motion in the OIS module (note that the image sensor is fixed). We employ a priori knowledge of the induced lens motion to facilitate optical flow estimation with sub-pixel accuracy, and the output high-precision pixel alignment vectors are utilized to merge the multiple frames to reconstruct the final super resolution image. Extensive experiments on a OISSR prototype implemented on a Xiaomi 10Ultra smartphone demonstrate the high performance and effectiveness of the proposed system in obtaining the quadruple enhanced resolution imaging.



***

## DoCam

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/project-docam.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 2 Structure from OIS-controlled Motion (SfOM) algorithm is proposed to recover the accurate camera poses, and high quality dense depth map can be estimate.
</div>

We dig into the potential of the existing OIS techniques in depth sensing and propose DoCam, the first work that utilizes the OIS-controlled lens motion to perceive metric depth of scene. We develop a unified framework by which to estimate accurate camera poses from image sequences with a micro-scale stereo baseline for use in high-quality depth estimation. Specifically, the bundle adjustment is reformulated by applying constraints on the multi-view geometry and the OIS controlling signal. Thus, our system is able to achieve high-quality depth estimation without additional camera movement, making it particularly suitable for scenarios where the camera is fixed and requiring surrounding 3D information.


## Demo Video

<div class="embed-responsive embed-responsive-16by9">
  <iframe class="embed-responsive-item" width="560" height="315"
    src="https://www.youtube.com/embed/IZ1_tr5mquQ" frameborder="0"
    allowfullscreen=""></iframe>
</div>


