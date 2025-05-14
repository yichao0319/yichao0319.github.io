---
layout: project
title: Whispering Spaces -- Create Sound Out of Thin Air for a New Reality
description: Imagine walking through a museum, and instead of looking down at a map, a voice seems to emanate from the direction of the exhibit you're seeking, guiding you with a simple "Follow me!". This isn't science fiction; it's the world of **acoustic augmented reality (AAR)**, and a new technology called **VISAR** is making it possible without headphones or special gadgets. By cleverly using the way sound behaves in air, VISAR can create **virtual sound spots**—focused areas of sound—that seem to appear out of nowhere, offering a more natural and immersive way to interact with our surroundings. This breakthrough paves the way for intuitive navigation, especially for the visually impaired, and opens up exciting possibilities for how we experience information and entertainment, transforming everyday spaces into interactive soundscapes.
img: assets/img/projects/project-visar-cover.png
importance: 2025
category: research
date: 2025-04-01
show: true

authors:
  - name: Juntao Zhou
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Dian Ding
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yijie Li
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yu Lu
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yida Wang
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yongzhao Zhang
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yi-Chao Chen
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Guangtao Xue
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University

---

## Abstract
Augmented reality is increasingly shaping how we interact with the world by blending virtual content with our physical surroundings. While much focus has been on visual AR, **acoustic augmented reality (AAR)** offers a unique way to enhance our experiences through sound. Traditional AAR often relies on headphones and complex calculations to create spatial audio. This paper introduces **VISAR**, a system that projects **virtual sound spots** directly into the environment, device-free, by harnessing a phenomenon called **air nonlinearity**. VISAR can pinpoint where a user is and simultaneously generate these localized sound zones, all while minimizing sound leakage to unintended areas. It even includes a method for managing multiple sound spots for several users at once, reducing interference between them. Extensive testing shows VISAR's high accuracy in tracking and sound projection, highlighting its significant potential for AAR applications.

## What are Virtual Sound Sources and Why Are They Important?

Imagine sound that isn't coming from a visible speaker, but rather appears to originate from a specific point in space—this is the essence of a **virtual sound source**. Think of it like a tiny, invisible speaker that you can place anywhere. **Acoustic augmented reality (AAR)** aims to enrich our real-world environments with such virtual soundscapes, creating a more immersive and informative experience without needing to wear cumbersome devices.

Why is this important? Sound is a powerful medium for conveying information and atmosphere. It’s all around us and can provide **omnidirectional engagement**. Imagine receiving navigation cues that seem to come from the actual direction you need to turn, like a gentle voice guiding you through a busy airport (as illustrated conceptually in `Fig. 1`). Or picture a museum exhibit where information about an artifact whispers directly from the artifact itself, enhancing your understanding and engagement. For individuals with visual impairments, such technology could be life-changing, offering a new layer of spatial awareness and independence. Current methods often require headphones and rely on complex Head-Related Transfer Functions (HRTFs) to simulate 3D audio, which can be cumbersome and don't always feel natural. The ability to project sound sources directly into the environment, without needing the user to wear anything, opens up a more seamless and intuitive way to interact with augmented information.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-visar-cover.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1  Project virtual sound spot sources to realize direction guidance in AAR scenarios such as navigation.
</div>

The magic VISAR uses is **air nonlinearity**. Normally, when sound travels, it does so in a linear way. But when high-energy sound waves pass through the air, the air itself can behave nonlinearly. This means that if you send out specific high-frequency sounds (ultrasound, which humans can't hear), the air can cause them to interact and create new, audible sounds at their intersection point. This is the core principle behind how VISAR creates sound spots out of what seems like thin air, as depicted by the interaction of primary beams creating a difference-frequency wave in `Fig. 2` of the paper.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-visar-01.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 2  An illustration of air nonlinearity that the transducer array can generate audible differential frequency beam from a high energy primary beam composed of high frequencies.
</div>


## VISAR: Crafting Sound in Space

**The Problem VISAR Solves:**
The challenge in creating truly immersive AAR has been to project sound to a specific, localized point in space without requiring users to wear headphones and without the sound "leaking" into surrounding areas where it's not wanted. Existing directional speaker technologies often project sound in a beam, meaning the sound is audible along the entire path of the beam, not just at a specific spot. Furthermore, when trying to create precise sound spots using arrays of ultrasound transducers, issues like **grating lobes** (unwanted secondary sound beams, as shown in `Fig. 3b` when spacing is greater than half a wavelength ) can cause sound to appear in unintended locations, confusing the listener (as seen in `Fig. 4d`, where an extraneous spot appears due to grating lobe crossover ). Additionally, supporting multiple users with individual sound spots introduces problems of interference between these spots.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-visar-02.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 3  Challenge: the beam patterns of an 8-channel phased array emitting 40kHz and target 0° and 30° while varying the spacing between elements (above half-wavelength, half-wavelength, and below half-wavelength). Grating lobes appear when the spacing is above half-wavelength.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-visar-03.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 4  (a) An illustration of a preliminary setup; (b) shows the heatmap that an obvious audible 1kHz component is produced at the intersection Z_1 of the beam. (c) shows the audible sound at Z_1 is much stronger than Z_2, Z_3, Z_4 and Z_5. This demonstrates the feasibility of producing a virtual sound spot using Visar. (d) shows the heatmap that when the transmit beams are deflected by 10°, there is not only a target spot but also a spot generated by the intersection of the grating lobes.
</div>


**VISAR's Approach:**
VISAR tackles these challenges with a clever system design. Its key idea is to use **two arrays of ultrasound transducers** (like tiny speakers that emit ultrasound). Each array sends out a different high-frequency ultrasonic signal. These signals are steered to intersect at a desired point in space. It's only at this intersection point that the **air nonlinearity** effect kicks in, causing the ultrasonic signals to interact and generate an audible sound that seems to originate right from that spot. This creates a fine-grained sound spot, down to a 15cm x 15cm area.

To make this practical, VISAR incorporates several key features:
1.  **Simultaneous Tracking and Projection:** VISAR needs to know where the user is to project the sound spot accurately. It uses a **frequency-division technique**, employing different ultrasound frequencies for tracking the user and for projecting the sound, so these processes don't interfere with each other and the tracking remains inaudible. `Fig. 5` in the paper shows the different frequency responses of the transducers used for this. The tracking itself uses **FMCW (Frequency Modulated Continuous Wave) chirps** that are steered to find the user, and the reflected signals are used to calculate their distance and location (illustrated in `Fig. 6` and the spatial modeling in `Fig. 7`).

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-visar-04.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 5  Frequency response of two ultrasound transducers of different central frequencies (20kHz and 40kHz).
</div>


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-visar-05.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 6  An illustration of the tracking process, including chirp steering range and an example of chirp signals. We first scan a large range and obtain the user’s location. Then, we perform small range scans due to users’ movement. After each scan, we update the scan range to ensure the continuous tracking of the system.
</div>


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-visar-06.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 7  Suppose the guide direction $\alpha$ is known, we can model the space for tracking (black lines) and determine the projection directions of two transducer arrays (orange lines).
</div>


2.  **Minimizing Sound Leakage:** To prevent audible sound from being generated along the path of the individual ultrasound beams before they intersect, VISAR uses **single-sideband (SSB) modulation** for the audio signals. This technique is more effective at reducing this "self-demodulation" problem compared to simpler amplitude modulation, as demonstrated in `Fig. 8` of the paper.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-visar-07.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 8  The spectrogram of amplitude modulation and USB modulation. USB modulation performs weaker audio leakage in the transmission path.
</div>


3.  **Beam Optimization:** To deal with the problematic **grating lobes** and interference between multiple beams (especially in multi-user scenarios), VISAR employs an **optimization-based beamforming scheme**. This involves adjusting the spacing between the transducer elements and the weights (amplitude and phase) of the signals sent to each element. The goal is to suppress grating lobes, create "nulls" (areas of no sound) in other unwanted directions, and enhance the main sound beam (see `Fig. 9` for a conceptual diagram of this optimization ). `Fig. 10` shows the effectiveness of this optimization in suppressing grating lobes and leaks.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-visar-08.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 9  Description of beam optimization. We optimize the ultrasonic transducer array on a column basis. The arguments of optimization are the distances between the columns of the ultrasonic transducer and the beam weight of the audio transmitted, including amplitude and phase. The objective of optimization is to suppress the grating lobe, perform wide-nulling in other possible audio playback directions, and ensure that the main lobe is strong enough.
</div>


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-visar-09.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 10  The beam pattern of 40.3kHz and 40.5kHz using optimization and not using optimization.
</div>


4.  **Multi-Spot Scheduling for Multiple Users:** When projecting sound to multiple users, there's a risk of creating numerous extraneous sound spots where different beams (intended for different users or even grating lobes) intersect. VISAR introduces a **multi-spot scheduling scheme**. This involves smartly redistributing which array sends which part of the sound signal (e.g., carrier wave vs. modulated audio) and slightly adjusting the locations of the target spots to ensure that any unavoidable extraneous spots are positioned as far away from users as possible or are "silent" (due to how signals combine). `Fig. 10` illustrates how this scheduling can reduce unwanted spots and noise.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-visar-10.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 11  The description of spot scheduling, where the blue beam is the carrier wave, the green beam is the up-converted audio played to User 1, and the yellow beam is the up-converted audio played to User 2. In the case of two users, the original solution would generate two extra spots. If the contents are redistributed, the extra spots will be reduced, but there are still audible noises. By adjusting the position of the target spot, we keep the audible noises as far away from the user as possible.
</div>


**Innovation:**
The core innovation of VISAR lies in its **holistic approach to creating device-free, fine-grained virtual sound spots**. It’s not just about generating sound using air nonlinearity, but doing so in a way that is practical for real-world AAR applications. This includes the **concurrent tracking and projection** using frequency division, the **optimization techniques to ensure clean sound delivery** by suppressing grating lobes and interference, and the intelligent **scheduling for multi-user scenarios**. Unlike previous systems that might create sound beams or require mechanical rotation, VISAR uses digital beam steering for fast and flexible spot positioning  and specifically aims for these small, controllable audible zones.

**How Well Does It Work? (Effects):**
VISAR performs impressively. Experiments show a tracking error of just $7.83cm$ and an orientation estimation error (how well users can tell where the sound is coming from) of about $10.06 degrees$.

Imagine you're in that museum again. A 7.83cm tracking error means VISAR knows almost exactly where your head is. The sound guiding you to the next exhibit will feel like it’s truly coming from a precise point just ahead of you, not vaguely from a general direction. An orientation error of 10 degrees is quite good – if the sound is meant to come from directly in front, you’ll perceive it very close to that. 

For the general public, this means the sound will feel **accurately placed and easy to localize**. The system can project sound spots effectively up to a working distance of about $2.8m$, which is suitable for many indoor spaces like homes, offices, or small museum rooms. It also works well for users of various heights, from $1.35m$ to $1.9m$. Users also rated the system positively in terms of **audibility, clarity, and directiveness**, especially after the optimization techniques were applied.


**Application Scenarios:**
The potential applications are vast and exciting:

1.  **Intuitive Navigation:** As in the museum example, VISAR can provide "eyes-free" navigation in indoor spaces like airports, shopping malls, or hospitals. Imagine your phone silently guiding you via localized sounds, without you needing to constantly look at a screen. This is especially powerful for the **visually impaired**, offering them a new sense of freedom and awareness in unfamiliar environments.
2.  **Personalized Public Information:** In a crowded train station, instead of announcements blaring everywhere, important information specific to your journey could be discreetly delivered to a sound spot right near your ear.
3.  **Immersive Entertainment:** Imagine a game where sounds from virtual characters or events emanate from their actual positions in your room, making the experience incredibly immersive without headphones. Or a home theater system where sound effects can be placed precisely in 3D space.
4.  **Enhanced Museum Exhibits and Retail Experiences:** Information about an artwork or product could be whispered from the object itself as you approach, creating a more engaging and personal interaction.
5.  **Focused Audio for Work or Study:** In an open office or library, you could receive private audio notifications or listen to music within your personal sound spot without disturbing others.
6.  **Assistive Technology:** Beyond navigation, it could provide alerts or information to individuals with specific needs in a very direct and non-intrusive manner.

VISAR's ability to create these controllable, headphone-free sound zones opens a new frontier for how we integrate digital audio information seamlessly and intuitively into our daily lives.


## Publications

<div hidden>
{% cite zhou-chi25 %}
</div>

