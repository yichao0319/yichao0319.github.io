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

Imagine walking through a museum, and instead of looking at a map, a voice seems to float from the direction of the exhibit you’re seeking, whispering, "This way to the artifacts!" This isn't magic; it's **acoustic augmented reality (AAR)**, a technology that layers virtual sounds onto our real world. A new system called **VISAR** is making this possible without headphones or any gadgets you need to wear. It uses the air itself to create **focused spots of sound**—like personal audio bubbles—that can guide you, inform you, or entertain you in a completely new way.

## Why Acoustic AR? And What's the Challenge?

While visual augmented reality (AR) gets a lot of attention, sound is a powerful and natural way to experience extra information. Think about it: you can hear things from all directions without turning your head. Acoustic AR aims to use this, perhaps for navigation in busy airports or for bringing museum exhibits to life with stories that seem to come from the objects themselves.

The big hurdle? Most current systems need you to wear headphones. They try to trick your ears into thinking sound is coming from different places. This can be complicated, and not everyone wants to wear headphones all the time. The dream is to have sound appear naturally in the space around you, without any extra gear.

## VISAR's Bright Idea: Sound from Ultrasound

VISAR achieves this device-free experience by harnessing a cool physics phenomenon called **air nonlinearity**. Normally, sound travels through air in a predictable way. But if you send out very high-frequency sounds (ultrasound, which humans can't hear) at high intensity, the air itself can cause these ultrasonic waves to interact and change. This interaction can create new sound waves, including sounds that are perfectly audible to us.

VISAR uses two arrays of small ultrasound emitters. Each array sends out a beam of ultrasound. These beams are aimed so they cross at a specific point in the air. On their own, the ultrasound beams are silent to us. But where they meet, the air nonlinearity effect happens, and voilà – an audible sound is generated right at that intersection, creating a **virtual sound spot**. This spot can be quite small, down to a 15cm by 15cm area, making the sound very localized. `Fig. 1` shows the goal: making information accessible through sound that feels like it's part of the environment itself.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-visar-cover.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1  VISAR projects virtual sound spot sources to realize direction guidance in AAR scenarios such as navigation.
</div>


## How VISAR Makes It Work

Creating these clean, controllable sound spots isn't simple. VISAR has some smart solutions:

1.  **Tracking Users:** To put a sound spot in the right place (e.g., just in front of you), VISAR needs to know where you are. It uses some of its ultrasound capability to do this, sending out signals and listening for reflections to pinpoint your location, all without you hearing the tracking process.
2.  **Clean Sound Projection:** A big challenge is making sure sound only appears at the target spot, not along the ultrasound beams themselves or in other random places.
    * It uses a special kind of signal modulation (called **single-sideband modulation**) to reduce sound leakage along the path of the ultrasound beams.
    * Ultrasound arrays can sometimes create unwanted side beams (called **grating lobes**) that might make extra, confusing sound spots. VISAR uses a sophisticated **beam optimization** process. Think of it as fine-tuning the signals from each little emitter in the array to focus the energy only where it's wanted and cancel it out where it's not.
3.  **Sounds for More Than One:** What if two people in a room need to hear different things? VISAR has a **multi-spot scheduling** system. It figures out the best way to assign signals to its arrays and can even subtly shift spot locations to minimize interference, ensuring each person gets their own clear audio message.

## What Makes VISAR Special and What Can It Do?

The big innovation in VISAR is how it combines all these elements into a practical system. It's not just about making sound from ultrasound; it's about doing it accurately, keeping the sound clean, and making it work for multiple users in real-time. Tests show VISAR can track users with an accuracy of about 7.83cm, and people can tell where the sound is coming from with an error of only about 10 degrees. This means the sound feels like it's coming from a precise, believable location.

The possibilities are exciting:

* **Intuitive Navigation:** Like in the museum (`Fig. 1`), VISAR could guide people through airports, shopping malls, or help visually impaired individuals navigate unfamiliar spaces with greater ease and confidence.
* **Personalized Information:** Imagine getting quiet, personalized flight updates at a gate, or product information whispered to you in a store, without everyone else hearing it.
* **Immersive Experiences:** Games could have sounds that truly seem to come from objects or characters in your room. Movies could have even more realistic soundscapes without needing complex speaker setups.
* **Focused Work/Study:** You could receive private audio notifications or listen to something without disturbing others in an open office or library.

VISAR demonstrates a future where sound enhances our reality in a much more seamless and personal way, all without needing us to plug in or put on any extra devices. It’s truly about making technology adapt to us, rather than the other way around.

***

## Publications

<div hidden>
{% cite zhou-imwut24 -f journal %}
</div>

