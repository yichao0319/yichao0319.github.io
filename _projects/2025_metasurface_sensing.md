---
layout: project
title: Metasurface Sensing -- Programmable Physical Channels
description: A long-term research direction on using passive and adaptive metasurfaces as programmable physical channels. Instead of treating waves as fixed inputs to algorithms, this work co-designs surfaces, signals, optimization, and learning so commodity acoustic, RF, microwave, mmWave, GNSS, and wearable systems can sense, localize, communicate, image, and monitor health beyond their native hardware limits.
img: assets/img/projects/project-metasurface-sensing-cover.png
importance: 2025
category: research
date: 2025-06-24
show: true

---

## Overview

Metasurface Sensing is built around one systems idea: the physical channel does not have to be a passive nuisance that algorithms clean up afterward. By designing how a surface scatters, focuses, redirects, or filters waves, we can create more informative measurements before the signal ever reaches an antenna, microphone, radar, or wearable sensor.

This project treats metasurfaces as a programmable physical layer for sensing and interaction. The same design philosophy appears across acoustic sensing, acoustic imaging, indoor GNSS, microwave energy control, high-resolution mmWave imaging, and non-invasive wearable health sensing: co-design the wavefront, the measurement process, and the inference pipeline as one system.

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-metasurface-sensing-cover.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1  Metasurface Sensing studies programmable wavefronts across wearable RF sensing, indoor GNSS, microwave energy control, and acoustic interaction.
</div>

## Research Direction

The long-term goal is not a single metasurface device, but a design stack for wave-aware sensing systems. At the bottom is a surface whose geometry, material, placement, or tuning state shapes propagation. Above it are signal designs and optimization routines that decide what information should be exposed by the channel. At the top are reconstruction, localization, recognition, or health-inference models that turn the reshaped measurements into useful outputs.

This stack changes how we think about commodity hardware. Instead of adding more sensors, larger arrays, or mechanical scanning, the environment itself becomes part of the sensing front end. A passive panel can make weak GNSS signals easier to observe indoors; a surface inside a microwave cavity can guide energy toward desired regions; an acoustic or mmWave metasurface can create spatial diversity that a compact device would not otherwise have; a wearable RF metasurface can make subtle physiological changes easier to measure.

<div class="row justify-content-sm-center">
    <div class="col-sm-11 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-metasurface-sensing-cgmm-design.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 2  Wearable RF sensing uses a tunable metasurface and inverse design to amplify subtle physiological coupling effects.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-11 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-metasurface-sensing-cgmm-setup.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 3  A metasurface-enhanced wearable sensing setup shows how the physical interface, tissue target, and RF hardware are co-designed.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-11 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-metasurface-sensing-gpms-setup.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 4  Passive metasurfaces can reshape weak indoor GNSS propagation so commodity receivers observe more useful spatial structure.
</div>

## Technical Pillars

**Wavefront co-design.** We design surface structures together with the target task, rather than treating the surface as a fixed accessory. The desired outcome may be focusing, steering, mode conversion, spatial coding, or controlled energy distribution.

**Measurement-aware inference.** The algorithms are built with the altered physical channel in mind. Optimization and learning models exploit the extra diversity introduced by the metasurface, turning difficult inverse problems into more stable sensing pipelines.

**Deployable physical systems.** The work emphasizes practical setups: passive panels, adaptive surfaces, commodity microphones, radar modules, microwave ovens, indoor GNSS receivers, and wearable sensing hardware. The point is to make the physical layer more intelligent without relying on bulky infrastructure.

<div class="row justify-content-sm-center">
    <div class="col-sm-11 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-metasurface-sensing-microsurf-setup.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 5  A microwave metasurface setup demonstrates physical control of energy distribution in an everyday RF environment.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-metasurface-sensing-acoustic-setup.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 6  Acoustic metasurfaces provide a deployable way to steer and structure sound fields for sensing and interaction.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-10 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-metasurface-sensing-mimsid-setup.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 7  mmWave imaging uses a passive metasurface to create richer spatial measurements with compact radar hardware.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-11 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-metasurface-sensing-mimsid-diffusion.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 8  Diffusion-based reconstruction turns metasurface-coded measurements into higher-resolution mmWave images.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-11 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-metasurface-sensing-mimsid-results.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 9  Paper results illustrate how joint wavefront design and inference improve imaging quality over weaker physical baselines.
</div>

## Why It Matters

Many sensing systems fail not because the downstream model is weak, but because the raw measurements are under-informative. Metasurfaces offer a complementary path: improve the physics of the measurement itself, then let algorithms operate on signals that already contain richer spatial, spectral, or coupling structure.

The publications below are concrete instantiations of this broader direction across acoustic, RF, microwave, mmWave, GNSS, and wearable health systems.

***

## Publications

<div hidden>
{% cite pan-mobicom25 %}
{% cite wang-mobisys25 %}
{% cite song-mobicom24 %}
{% cite wang-mobicom24 %}
{% cite fu-mobisys24 %}
{% cite zhang-nsdi23 %}
</div>
