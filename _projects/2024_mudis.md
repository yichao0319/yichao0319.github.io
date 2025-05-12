---
layout: project
title: Multi-directional Speaker Using Air Nonlinearity
description: We propose a novel multi-directional speaker using a parametric array to generate multiple highly directional sound beams. The system leverages air nonlinearity to reproduce audible sound from ultrasounds. It overcomes the challenges in traditional parametric arrays in terms of transducer size and focused wavefront, by using a special cell structure that connects ultrasonic transducers with optimal interspace to redirect an approximate omnidirectional wavefront. An optimization-based algorithm is developed to minimize unintended leakages. To further improve sound quality, we propose a nonlinear distortion reduction scheme.
img: assets/img/projects/project-mudis-cover.png
importance: 2024
category: research
date: 2024-10-01
show: true

authors:
  - name: Yijie Li
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Juntao Zhou
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Dian Ding
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Yi-Chao Chen
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Lili Qiu
    url: ""
    affiliations:
      name: UT Austin
      name: Microsoft Research Asia-Shanghai
  - name: Jiadi Yu
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  - name: Guangtao Xue
    url: ""
    affiliations:
      name: Shanghai Jiao Tong University
  

---

## Abstract

Traditional speakers emit sound indiscriminately in all directions, often causing noise pollution and interfering with private listening experiences in public spaces. Our innovative solution, **MuDiS**, introduces a revolutionary multi-directional speaker that directs distinct audio precisely to multiple users simultaneously without audio leakage. Using ultrasonic transducers and acoustic metasurfaces, MuDiS achieves wide-angle digital steering, independent audio beams, and minimal unintended leakage, vastly improving on existing commercial technologies.


## Introduction: Why Directional Speakers?

Imagine walking through a crowded museum, each exhibit providing personalized audio commentary precisely where visitors stand—without any headphones or disturbing neighboring exhibits. Directional speakers make this scenario possible by focusing sound beams toward specific directions. This technology transforms public and communal spaces like museums, gyms, libraries, and offices into environments offering personalized audio experiences without noise pollution.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-mudis-cover.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1  An example scenario for using a multi-directional speaker: in a museum, multi-directional speaker delivers audio specific to the exhibit that each visitor is viewing without interfering with each other.
</div>


## Challenges in Existing Technology

Current directional speakers either rely on large physical arrays that are bulky and difficult to deploy or employ parametric arrays with limited steering angles and mechanical constraints. Traditional parametric arrays also suffer from unintended audio leaks and nonlinear distortion, severely limiting their practical use.


## MuDiS

MuDiS uniquely combines parametric array technology with carefully engineered acoustic metasurfaces and advanced optimization algorithms. The metasurface ensures correct spacing between transducers and transforms the emitted wavefront into a more uniform spherical shape. This significantly enhances the steering angle and reduces audio leakage.


### Key Innovations

MuDiS employs three groundbreaking methods:

* **Acoustic Metasurface Design**: Our custom-designed metasurface corrects wavefront shape, enabling much wider steering angles (up to 130°) compared to traditional speakers. By precisely engineering the acoustic path, MuDiS significantly reduces leakage and grating lobes.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-mudis-01.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 2  The 3D geometry components of physical simulationof anacousticmetasurface.
</div>

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-mudis-02.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 3  The 3D geometry and 3D printed structure of initial and optimal structure. Four materials are selected forcomparison.
</div>


* **Optimization-based Beamforming**: We developed an algorithm specifically targeting unintended audio leakage, minimizing interactions between multiple audio beams. This ensures each listener hears only their intended audio clearly.

* **Nonlinear Distortion Reduction**: MuDiS integrates a sophisticated optimization technique to minimize audio distortion resulting from nonlinear acoustics, greatly enhancing the perceived sound quality.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-mudis-03.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 4  Problem formulation and objectives for leakage-cancellationoptimization.
</div>



## Results

We constructed a prototype of a multi-directional speaker employing our metasurface. We proceed to demonstrate the efficacy of our proposed **Optimization-based Beamforming** and **Nonlinear Distortion Reduction** scheme alongside traditional beamforming (Delay and Sum Beamforming) and MVDR Beamforming scheme.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-mudis-04.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 5  MuDiS prototype and experiment setup.
</div>


### Prototype

As depicted in `Fig. 6`, our multi-directional speaker with the metasurface simultaneously transmits two distinct beams. The first beam is directed towards 0° to transmit a female voice, while the second beam targets 60° to transmit a male voice. Recorded voices from 0°, 30°, and 60° are provided below for reference.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/projects/project-mudis-05.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 6  Scenario.
</div>


### Performance

We constructed a prototype of a multi-directional speaker employing our metasurface. We proceed to demonstrate the efficacy of our proposed <b> Optimization-based Beamforming </b> and <b> Nonlinear Distortion Reduction </b> scheme alongside traditional beamforming (Delay and Sum Beamforming) and MVDR Beamforming scheme.

<div class="comparisons-desktop" align="center">
  <h3> Original Voices. </h3>
  <table style="text-align: center">
      <tbody>
          <tr>
              <td>
                  <div class="audio">
                    {% include audio2.liquid path="assets/audio/project-mudis/woman6.wav" %}
                  </div>
              </td>
              <td>
                  <div class="audio">
                  {% include audio2.liquid path="assets/audio/project-mudis/man6.wav" %}
                  </div>
              </td>
          </tr>
          <tr>
              <th>0°: Female Voice</th>
              <th>60°: Male Voice</th>
          </tr>
      </tbody>
  </table>

  <br>
  <br>
  <h3> Sound Received at 0° <div style="color: #dc3545;">&#160;(Expected: Female Voice Only)</div></h3>
  <table style="text-align: center">
      <tbody>
          <tr>
              <td>
                  <div class="audio">
                  {% include audio2.liquid path="assets/audio/project-mudis/2beams_0deg/demo_null_0deg.wav" %}
                  </div>
              </td>
              <td>
                  <div class="audio">
                  {% include audio2.liquid path="assets/audio/project-mudis/2beams_0deg/demo_raw_0deg.wav" %}
                  </div>
              </td>
              <td>
                  <div class="audio">
                  {% include audio2.liquid path="assets/audio/project-mudis/2beams_0deg/demo_mvdr_0deg.wav" %}
                  </div>
              </td>
          </tr>
          <tr>
              <th>Ours</th>
              <th>Traditional Multi-beamforming</th>
              <th>MVDR Multi-beamforming</th>
          </tr>
      </tbody>
  </table>

  <br>
  <br>
  <h3> Sound Received at 30° <div style="color: #dc3545;">&#160;(Expected: No Voice)</div></h3>
  <table style="text-align: center">
      <tbody>
          <tr>
              <td>
                  <div class="audio">
                  {% include audio2.liquid path="assets/audio/project-mudis/2beams_30deg/demo_null_30deg.wav" %}
                  </div>
              </td>
              <td>
                  <div class="audio">
                  {% include audio2.liquid path="assets/audio/project-mudis/2beams_30deg/demo_raw_30deg.wav" %}
                  </div>
              </td>
              <td>
                  <div class="audio">
                  {% include audio2.liquid path="assets/audio/project-mudis/2beams_30deg/demo_mvdr_30deg.wav" %}
                  </div>
              </td>
          </tr>
          <tr>
              <th>Ours</th>
              <th>Traditional Multi-beamforming</th>
              <th>MVDR Multi-beamforming</th>
          </tr>
      </tbody>
  </table>

  <br>
  <br>
  <h3> Sound Received at 60° <div style="color: #dc3545;">&#160;(Expected: Male Voice Only)</div></h3>
  <table style="text-align: center">
      <tbody>
          <tr>
              <td>
                  <div class="audio">
                  {% include audio2.liquid path="assets/audio/project-mudis/2beams_60deg/demo_null_60deg.wav" %}
                  </div>
              </td>
              <td>
                  <div class="audio">
                  {% include audio2.liquid path="assets/audio/project-mudis/2beams_60deg/demo_raw_60deg.wav" %}
                  </div>
              </td>
              <td>
                  <div class="audio">
                  {% include audio2.liquid path="assets/audio/project-mudis/2beams_60deg/demo_mvdr_60deg.wav" %}
                  </div>
              </td>
          </tr>
          <tr>
              <th>Ours</th>
              <th>Traditional Multi-beamforming</th>
              <th>MVDR Multi-beamforming</th>
          </tr>
      </tbody>
  </table>
</div>



---

## Demo Video

<div class="embed-responsive embed-responsive-16by9">
  <iframe class="embed-responsive-item" width="560" height="315"
    src="https://www.youtube.com/embed/DmBe3b4w9c0?si=uRo4S30Ojr9EsQMH" frameborder="0"
    allowfullscreen=""></iframe>
</div>

---

## Publications

<div hidden>
{% cite li-mobicom24 %}
</div>



