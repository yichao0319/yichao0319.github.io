---
layout: project
title: Unlocking Bluetooth Direction-Finding for All Devices -- Bridging the Gap
description: Bridge represents a pivotal step towards universal indoor localization. By elegantly solving compatibility issues without altering existing devices, Bridge democratizes the high-precision capabilities of BLE 5.1 direction finding, making advanced localization widely accessible. Its innovative nesting packets, precise AoA estimation via overhearing, and scalable deployment position it as a significant advancement in Bluetooth-based technologies. Bridge exemplifies a compelling vision where legacy devices seamlessly integrate into modern localization infrastructures, offering industries and consumers enhanced accuracy, reduced costs, and effortless upgrades to their localization capabilitie.
img: assets/img/projects/project-bridge-cover.png
importance: 2025
category: research
date: 2025-05-10
show: true

authors:
  - name: Runting Zhang
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yijie Li
    url: ""
    affiliations:
      name: National University of Singapore
  - name: Dian Ding
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yi-Chao Chen
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yida Wang
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Dongyao Chen
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Jingxian Wang
    url: ""
    affiliations:
      name: National University of Singapore
  - name: Jiadi Yu
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Ling Ma
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Guangtao Xue
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University

---

## Abstract

Bluetooth Low Energy (BLE) direction-finding significantly improves localization precision, yet billions of legacy Bluetooth devices remain unsupported due to hardware limitations. We introduce **Bridge**, a novel system leveraging an additional trigger node to extend BLE direction-finding compatibility universally without modifying existing devices. Utilizing innovative nesting packets and precise angle-of-arrival estimation via signal overhearing, Bridge achieves remarkable localization accuracy comparable to native BLE 5.1 systems. Extensive evaluations in diverse real-world environments demonstrate Bridge’s practical applicability, showcasing its potential to revolutionize indoor localization technology.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-bridge-cover.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1 Bridge introduces an additional trigger node (Trigger) to make BLE direction-finding features compatible with all Bluetooth devices, overcoming existing hardware limitations.
</div>


## Introduction to Bluetooth Direction-Finding

Bluetooth Low Energy (BLE) direction-finding is a powerful technology enabling devices to pinpoint locations with high precision. Released with Bluetooth version 5.1, this feature uses Angle of Arrival (AoA) estimation, significantly enhancing localization accuracy in various applications such as logistics, retail, healthcare, and smart industries. Despite its potential, a substantial challenge persists: billions of legacy Bluetooth devices (around $68\%$ of all Bluetooth devices) remain incompatible due to hardware and firmware constraints.

## Bridge: A Universal Solution

The paper "Bridge: Enabling BLE Direction Finding Feature Compatible with All Bluetooth Devices" addresses this limitation by introducing an innovative system named Bridge. The Bridge solution employs a dedicated trigger node (Trigger) acting as a bridge between unsupported Bluetooth devices and locators. As depicted in `Fig. 1`, the Trigger synchronizes communication, enabling standard BLE 5.1 locators to recognize and localize even legacy devices.

### Technical Challenges and Innovations

The critical challenge for Bridge was enabling direction-finding without modifying the existing hardware or firmware of Bluetooth devices. The authors solved this with the introduction of a "nesting packet," which simultaneously transmits data intended for both the locator and the target device. `Fig. 2` illustrates the systematic flow, demonstrating how the nesting packet facilitates this dual communication.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-bridge-02.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 2  Overview of Bridge system components, showing interaction between Trigger, locator, target device, and the localization server.
</div>

Further, precise AoA estimation through "overhearing" introduced unique challenges—namely uncertain arrival times and unstable signal phases. As presented in `Fig. 3`, the solution involved intricate packet synchronization and temporal adjustments ensuring the target device’s packets precisely overlap with the locator’s AoA sampling window.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-bridge-03.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 3 Packet flow design showing how nesting packets facilitate synchronization and precise overhearing for AoA estimation.
</div>

## Performance and Practical Implications

Experimental evaluations revealed impressive outcomes. The Bridge system achieved an average localization accuracy of $33.4cm$, nearly matching standard BLE 5.1 localization systems. It successfully extended compatibility to ten diverse Bluetooth devices, highlighting its universal applicability and practical impact in everyday scenarios, including smartphones, remote controls, and wearable devices (`Fig. 4`).

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-bridge-04.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 4 Implementation of Bridge showcasing different types of Bluetooth devices used in the evaluation.
</div>

The real-world test environments (`Fig. 5`) demonstrated that Bridge works reliably across varied conditions—from open spaces to crowded indoor environments—thus solidifying its practical utility.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-bridge-05.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 5 Experiment environments illustrating diverse real-world scenarios.
</div>

***

## Publications

<div hidden>
{% cite zhang-mobicom25 %}
</div>



