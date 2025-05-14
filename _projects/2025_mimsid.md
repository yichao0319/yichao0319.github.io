---
layout: project
title: MIMSID -- Revolutionizing mmWave Imaging with AI and Metasurface Technology
description: MIMSID is a novel technique for high-resolution millimeter-wave (mmWave) imaging. It utilizes a compact, off-the-shelf mmWave module and a specially designed passive metasurface, eliminating the need for mechanical movement and offering a portable solution. The system tackles the limitations of current mmWave hardware, such as a restricted number of antennas and the reliance on compressive sensing algorithms that assume data sparsity. By integrating an optimized metasurface with a diffusion-based neural network (Sig2Img Diffusion), MIMSID directly transforms mmWave signals into high-quality images. This approach not only enhances image resolution but also provides a robust alternative to traditional methods. Extensive experiments demonstrate MIMSID's ability to achieve sub-centimeter resolution imaging, significantly outperforming existing techniques.
img: assets/img/projects/project-mimsid-01.png
importance: 2025
category: research
date: 2025-05-01
show: true

authors:
  - name: Yida Wang
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yu Lu
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yuxuan Zhou
    url: ""
    affiliations:
      name: The Hong Kong University of Science and Technology
  - name: Yifei Shen
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Lili Qiu
    url: ""
    affiliations:
      name: Microsof Research Aisa
  - name: Zeyuan Lai
    url: ""
    affiliations:
      name: University of Science and Technology of China
  - name: Yi-Chao Chen
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Ha Pan
    url: ""
    affiliations:
      name: Microsof Research Aisa
  - name: Juntao Zhou
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Dian Ding
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Mei Wang
    url: ""
    affiliations:
      name: UT Austin
  - name: Guangtao Xue
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Qian Zhang
    url: ""
    affiliations:
      name: The Hong Kong University of Science and Technology
  

---

## Abstract

**Millimeter-wave (mmWave) imaging** is becoming increasingly important for applications requiring detailed imaging in obstructed or privacy-sensitive environments. Think of security checks, industrial inspections, or even medical examinations. However, current off-the-shelf mmWave radar systems often face a critical challenge: **limited imaging resolution**. This is primarily due to the restricted number of antennas they possess. Furthermore, many existing imaging algorithms depend on a technique called **compressive sensing**. While useful, compressive sensing assumes that the image data has a specific, sparse structure, which isn't always the case with real-world objects.

This project presents **MIMSID (Metasurface-based mmWave Imaging using Signal-to-Image Diffusion)**, a groundbreaking approach designed to overcome these hurdles. The core idea is twofold: first, to enhance the incoming mmWave signals using a custom-designed **passive metasurface**, and second, to reconstruct high-quality images from these signals using an advanced **artificial intelligence model based on diffusion techniques**.

## The Metasurface: Expanding the View

Imagine trying to see a detailed picture through a tiny pinhole – you wouldn't get much information. Standard mmWave radars face a similar problem due to their limited antenna arrays. To address this, MIMSID incorporates a **passive mmWave metasurface**. A metasurface is a specially engineered surface with tiny, sub-wavelength structures that can manipulate electromagnetic waves, like mmWaves, in precise ways. In this system, the metasurface is designed to effectively increase the "virtual" size of the antenna array, capturing more detailed information from the target.

The researchers meticulously designed the unit cells of the metasurface to achieve high signal penetration and precise phase control across the 77-81 GHz frequency band, which is crucial for automotive radar and other sensing applications. They then jointly optimized the metasurface's phase map (how it manipulates the waves) and the transmitter's signals (codewords) to maximize the quality of the data gathered for imaging.

`Fig. 1` shows the overall system architecture, where the target's reflected mmWave signals pass through the metasurface, are received by the mmWave module, and then processed by the Sig2Img Diffusion model to reconstruct the image.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-mimsid-01.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1  Illustration of MIMSID.
</div>

 
## Sig2Img Diffusion: From Signals to Sharp Images

Once the enhanced mmWave signals are captured, the next challenge is to convert them into a clear image. Traditional methods often struggle with noise or make assumptions about the image that don't always hold true. MIMSID employs a **novel signal-to-image diffusion model (Sig2Img Diffusion)**.

**Diffusion models** are a powerful class of generative AI that have shown remarkable success in creating highly realistic images from noise. The researchers adapted this concept for mmWave imaging. The Sig2Img Diffusion model learns the inherent characteristics of target images and uses the captured mmWave signals as a conditional guide to progressively refine a noisy initial guess into a high-resolution image. This process effectively sidesteps the limitations of compressive sensing by directly learning the relationship between the complex mmWave signals and the visual representation of the object. The paper also theoretically proves that these conditional diffusion models can be optimal estimators for such signal recovery problems. `Fig. 2` illustrates how the diffusion model iteratively refines the image using a UNet architecture conditioned on the signal, contrasting with the thresholding approach of compressive sensing.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-mimsid-02.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 2  Comparison of the proposed diffusion methods and conventional compressive sensing methods.
</div>


## Putting It All Together and Proving Its Worth

The MIMSID system involves several key steps:

1.  **Joint Optimization:** The metasurface design and transmitter codewords are optimized together to ensure the best possible signal quality for imaging.
2.  **Channel Estimation:** An efficient algorithm estimates the mmWave channel characteristics, allowing the system to adapt to changes over time and in different environments.
3.  **Image Reconstruction:** The trained Sig2Img Diffusion model takes the measured reflection signal and the estimated channel matrix to generate the final image.

Through extensive experiments, the researchers demonstrated that **MIMSID achieves sub-centimeter imaging resolution** (e.g., median RMSE of 0.061 on a 20cm x 20cm imaging plane with 1cm resolution). The optimized metasurface alone was shown to reduce reconstruction errors significantly, and the diffusion model further halved the errors compared to traditional ADMM-based methods. The system can accurately reconstruct images even when objects are occluded by materials like cloth or plastic and shows robustness across various environments. It also boasts fast imaging, capable of capturing a frame in milliseconds, making it suitable for imaging slowly moving objects.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-mimsid-03.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 3  Prototype.
</div>


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-mimsid-04.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 4  Overall performance examples.
</div>


## Impact and Future Directions

MIMSID represents a significant step forward in making **high-resolution mmWave imaging more accessible and effective**. Its compact, stationary design opens doors for deployment in space-constrained scenarios where traditional, bulky systems with mechanical scanning are impractical. Potential applications are vast, ranging from enhanced security screening and non-destructive industrial quality control to new forms of human-computer interaction.

While the system shows great promise, the authors acknowledge areas for future work, such as improving performance with low-reflectivity materials and further reducing recalibration costs for different imaging setups. Nevertheless, MIMSID's innovative combination of metasurface technology and advanced AI points towards a future where we can "see" the world around us with greater clarity using invisible mmWaves.

***

## Publications

<div hidden>
{% cite wang-mobisys25 %}
</div>

