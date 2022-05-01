---
layout: project
title: Nonlinearity of Spatial Frequency in Light and Its Applications
description: We model the nonlinear interaction between Color Filter Array and screens, and build applications inlcluding the novel optical encryption method for QR codes on top of our model.
img: assets/img/project-moire-cover.png
importance: 2021.2
category: research
date: 2019-10-21
show: true

authors:
  - name: Hao Pan
    url: https://haopan.netlify.app/
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yi-Chao Chen
    url: "https://yichao0319.github.io"
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Lanqing Yang
    url: 
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Guangtao Xue
    url: 
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Chuang-Wen You
    url: 
    affiliations:
      name: National Taiwan University
  - name: Xiaoyu Ji
    url: 
    affiliations:
      name: Zhejiang University
  - name: Yushi Cheng
    url: 
    affiliations:
      name: Zhejiang University
  - name: Lixu Wang
    url: 
    affiliations:
      name: Zhejiang University
  - name: Qi Pang
    url: 
    affiliations:
      name: Zhejiang University
  - name: Wenyuan Xu
    url: 
    affiliations:
      name: Zhejiang University

---

## Summary

Spatial frequency is a characteristic of any structure that is periodic across its position in space. In this project, we consider a bi-dimensional (2D) spatial structure with curvilinear pattern. When two spatial patterns overlap, the nonlinear optical interaction between the patterns creates an additional visible layer (referred to as a Moiré pattern) over the original patterns. Figure 1 shows two examples of the nonlinear phenomenon during the interacton between two patterns with different spatial frequencies. 
Digital camera depends on the color filter array (CFA) to capture the RGB color information of the scene, and Bayer CFA is the most common filter deployed on the smartphone cameras. When capturing a picture of a screen, the pixels of the screen LCD/OLED sensors projected onto camera form a spatial pattern layer with spatial frequency f1, and the CFA forms the other layer with frequency f2. When the camera is positioned at an appropriate position to the screen, the difference between spatial frequencies (f1 - f2) caused by nonlinear phoenomenon (also called Moiré effect) falls within an observable frequency range, such that the nonlinear optical interaction appears as a rippled image. 

In this project, we propose mQRCode, which exploits nonlinearities in the spatial frequency of light rays to camouflage QR codes from the communication channel. When a QR code is generated, mQRCode encrypts it within a pattern that is regarded as noise (from the perspective of the human visual system) using a designated spatial frequency. Only when the targeted camera in a designated position , the original QR code is revealed in form of a Moiré pattern. From any other position, only the camouflaged QR code can be seen.

We also propose mID, a new watermark-like technique that can create a carefully crafted Moiré pattern on the photo when it is taken towards the screen. We design patterns that appear to be natural yet can be linked to the identity of the leaker. The results show that Moiré patterns are ideal for photo forensics because they are optical phenomena naturally generated during the process of photographing screens and are observed regularly in photos of digital screens.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/nonlinearity.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1 Two examples of the nonlinearity of spatial frequency in light.
</div>

***

## mQRCode

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/mqrcode.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 2 (a) In mobile payment scenarios, the cashier is the target receiver and the surrounding attackers are the illegal receivers. (b) The traditional QR code image can be obtained by both the cashier and the attackers, while the Moiré QR code is highly secure and cannot be spied out by attackers.
</div>

Quick response (QR) codes are becoming pervasive due to their rapid readability and the popularity of smartphones with built-in cameras. QR codes are also gaining importance in the retail sector as a convenient mobile payment method. However, researchers have concerns regarding the security of QR codes, which leave users susceptible to financial loss or private information leakage. In this study, we address this issue by developing a novel QR code (called mQRCode), which exploits patterns presenting a specific spatial frequency as a form of camouflage. When the targeted receiver holds a camera in a designated position (e.g., directly in front at a distance of 30 cm from the camouflaged QR code), the original QR code is revealed in form of a Moiré pattern. From any other position, only the camouflaged QR code can be seen. In experiments, the decryption rate of mQRCode was > 98.6% within 10.2 frames via a multi-frame decryption method. The decryption rate for cameras positioned 20° off axis or > 10cm away from the designated location dropped to 0%, indicating that mQRCode is robust against attacks. 

***

## mID

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/mid.jpg" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 3 An illustration of mID for screen photo forensics. The identity (ID) of an adversary is embedded on the screen by subtly manipulating what is being displayed and can be recovered later by analyzing the Moiré patterns on the screen photos.
</div>

Cyber-theft of trade secrets has become a serious business threat. Digital watermarking is a popular technique to assist in identifying the source of the file leakage, whereby a unique watermark for each insider is hidden in sensitive files. However, malicious insiders may use their smartphones to photograph the secret file displayed on screens to remove the embedded hidden digital watermarks due to the optical noises introduced during photographing. To identify the leakage source despite such screen-photo-based leakage attacks, we leverage Moiré pattern, an optical phenomenon resulted from the optical interaction between electronic screens and cameras. As such, we present mID, a new watermark-like technique that can create a carefully crafted Moiré pattern on the photo when it is taken towards the screen. We design patterns that appear to be natural yet can be linked to the identity of the leaker. We implemented mID and evaluate it with 5 display devices and 6 smartphones from various manufacturers and models. The results demonstrate that mID can achieve an average bit error rate (BER) of 0.6% and can successfully identify an ID with an average accuracy of 96%, with little influence from the type of display devices, cameras, IDs, and ambient lights.

***

## Demo Video

This demo video shows how an Moiré code is naturally revealed when the receiver (camera) is put precisely at the designated position, and the Moiré code images captured from any other positions are unable to make out the intended original QR code information.

<!-- <iframe height=498 width=510 src="https://youtu.be/D10J7WCik8U"> -->

<div class="embed-responsive embed-responsive-16by9">
  <iframe class="embed-responsive-item" width="560" height="315"
    src="https://www.youtube.com/embed/D10J7WCik8U" frameborder="0"
    allowfullscreen=""></iframe>
</div>


***

## Publication

<div hidden>
{% cite cheng-security21  %}
{% cite pan-mobicom19  %}
{% cite pan-wintech19 -f poster %}
{% cite pan-mobicom19-poster -f poster %}
{% cite pan-ubicomp18 -f poster %}
{% cite pan2018secure -f poster %}
</div>


