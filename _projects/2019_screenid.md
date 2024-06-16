---
layout: project
title: Enhancing QRCode Security by Fingerprinting Screens
description: In ScreenID, PWM frequency of screens is exploited as the unique screen fingerprint and used to enhance the security of a QR code by identifying its authenticity.
img: assets/img/project-screenid-cover.png
importance: 2019
category: research
date: 2019-10-21
show: true

authors:
  - name: Yijie Li
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yi-Chao Chen
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Xiaoyu Ji
    affiliations:
      name: Zhejiang University
  - name: Hao Pan
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Lanqing Yang
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Guangtao Xue
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Jiadi Yu
    affiliations:
      name: Shanghai Jiao Tong University

---

## Abstract

Quick response (QR) codes have been widely used in mobile applications due 
to its convenience and the pervasive built-in cameras on smartphones. 
Recently, however, attacks against QR codes have been reported that 
attackers can capture a QR code of the victim and replay it to achieve a 
fraudulent transaction or intercept private information, just before the 
original QR code is scanned. 

In this study, we enhance the security of a QR 
code by identifying its authenticity. We propose ScreenID, which embeds 
a QR code with information of the screen which displays it, thereby the QR 
code can reveal whether it is reproduced by an adversary or not. In 
ScreenID,  PWM frequency of screens is exploited as the unique screen 
fingerprint. To improve the estimation accuracy of PWM frequency, 
ScreenID incorporates a model  for the interaction between the camera and 
screen in the temporal and spatial domains. Extensive experiments 
demonstrate that ScreenID can differentiate screens of different models, 
types, and manufacturers, thus improve the security of QR codes.


***

## Introduction

The QRCode system works in a straightforward way. As shown 
in the flowchart in `Fig.1`, payment transactions begin 
with the generation of a legal QR code, which includes the ID of the user in the application, e.g., the AliPay account, a time-stamp, and the secret transaction information in the form of an encrypted token. The user then presents the QR code to the cashier to have it scanned into the transaction system, together with other transaction information such as total amount and currency type. On the server side, the merchant extracts the token from QR code, obtains the user ID from the token and then accesses the database maintained by the company to retrieve the stored secret of the payer. This secret is then converted into a new token for verification. As long as the token is deemed valid, the transaction proceeds.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/project-screenid-authentication.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1 A flowchart of a typical QRCode system for mobile transaction.
</div>

However, the above-mentioned transaction process is far from secure. Recently, 
researchers have reported that a QRCode system is susceptible to the 
Synchronized Token Lifting and Spending (STLS) attack and other similar 
attacks [<sup>1</sup>](#refer-1). In this attack, the adversary first acquires an 
image of the QR code displayed on the victim's device, when the 
victim is showing the QR code to the cashier, then the adversary replays the stolen QR code for another transaction, which we call fraudulent 
transaction. To ensure the success of such an attack, the adversary should also 
finish the transaction before the legitimate scanning process from the cashier.

To address this issue, we sought to enhance the security of the QRCode system by 
identifying the authenticity of a QR code. We propose ScreenID, which embeds a 
QR code with information of the screen that is displaying it, thereby the 
generated QR code can reveal whether the screen is corresponding to it. In ScreenID, we utilize the pulse width modulation (PWM) frequency of screens as the unique screen fingerprint. PWM frequency makes a good candidate for screen fingerprint for the reason that it is adjusted to 
different value by screen manufacturers. Even for the same manufacture, the PWM 
frequency shows variances due to the variations in the manufacturing processes. 

`Fig.2(a)(c)(e)` shows the black and white bands caused by 
the interaction between LCD screen flicker and the rolling shutter. Note the 
lack of variation in the width and angle of the bands despite variations in the 
distance and angle between the camera and screen. This indicates the 
estimates of flicker frequency vary only as a function of rolling shutter 
speed. By contrast, the bands in `Fig.2(b)(d)(f)` from an OLED 
screen varied in terms of width and angle, depending on the position of the 
screen. This can be attributed to the fact that each pixel in an OLED screen is 
controlled by an LED light source and the PWM cycle of each row is 
asynchronous.

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.html path="assets/img/project-screenid-photo.png" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Fig. 2 Images of LCD and OLED screens captured using a camera. The position and direction of the screens were varied.
</div>

Therefore, the key idea of ScreenID is to model the screen-camera interaction in temporal as well as spatial domain. The system needs to parse out the PWM frequency of the screen from the captured picture regardless of any rotation angle and capturing distance. `Fig. 3` illustrates the architecture of ScreenID system, comprising two parts: encoding by the sender (smartphone screen) and decoding by the receiver (camera). For decoding process, the system first captured a single image to determine QR code position, then captured a video for real-time PWM frequency extraction. The frequency extraction process includes four steps: contour extraction, multi-frame concatenation, frequency extraction and verification.   

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.html path="assets/img/project-screenid-overview.png" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Fig. 3 overview of ScreenID system.
</div>


***

## Contribution

We verified the efficacy of a ScreenID prototype using 50 screens under a 
variety of camera settings and environmental conditions. The usability of the 
proposed system was also verified in experiments involving ten participants of 
various ages. We summarize the contribution as follows:

*  We demonstrated the feasibility of using PWM frequency of screens for 
  fingerprint, and the fingerprint can be embedded in to a QR code to check its 
  authenticity. From our dataset, $99.3\%$ pairwise frequency differences of 
  screens are larger than $0.1Hz$.  
*  We proposed ScreenID, which incurs no additional hardware for the QRCode system and has no requirements for user behavior. ScreenID can be implemented via a simple software update. 

*  We proposed to model the interaction between the camera and the 
  screen in both temporal and spatial domains and achieved high estimation 
  accuracy of PWM frequency, i.e., within $0.03Hz$

* We conducted exhaustive experiments and demonstrated the efficacy of the 
  ScreenID system under a variety of operating conditions. The evaluation shows 
  the identifiable success rate (i.e. True Positive Rate) is above $94.3\%$ and 
  the wrongly accepted rate (i.e. False Positive Rate) 
  against attack attempts is below $0.8\%$.


***

## Demo Video


<!-- The video of the pattern captured by the camera on the screen with different PWM frequencies:

<div class="embed-responsive embed-responsive-16by9">
  <iframe class="embed-responsive-item" width="560" height="315"
    src="https://www.youtube.com/embed/wyPaTBDwOvI" frameborder="0"
    allowfullscreen=""></iframe>
</div> -->

The video of the full presentation:

<div class="embed-responsive embed-responsive-16by9">
  <iframe class="embed-responsive-item" width="560" height="315"
    src="https://www.youtube.com/embed/wyPaTBDwOvI" frameborder="0"
    allowfullscreen=""></iframe>
</div>

***


## Reference

<div id="refer-1"></div>
[1] [Picking up my tab: Understanding and mitigating synchronized token lifting and spending in mobile payment](https://www.usenix.org/conference/usenixsecurity17/technical-sessions/presentation/bai)


***

## Publications

<div hidden>
{% cite li-infocom21 %}
</div>



