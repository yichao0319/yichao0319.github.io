---
layout: project
title: Sensing the Unseen -- How WiFi Can Recognize and Authenticate Humans
description: WiFi sensing represents a groundbreaking advancement in smart technology, transforming ordinary WiFi routers into sophisticated sensing tools capable of recognizing and authenticating individuals invisibly. This technology bypasses traditional limitations by using ambient WiFi signals to distinguish unique physiological and behavioral characteristics, enabling both gesture-independent and simultaneous multi-user authentication. Systems like FreeAuth and MultiAuth utilize innovative algorithms and machine learning models to extract subtle yet distinctive signal patterns, ensuring reliable identification with impressive accuracy rates. Applicable in diverse scenarios from secure home access and collaborative workplaces to interactive gaming environments, WiFi sensing not only enhances user experience but significantly bolsters security and privacy. As we continue to explore this promising field, WiFi sensing holds the potential to seamlessly integrate into everyday life, fostering a future where intuitive, non-intrusive security measures become standard.
img: assets/img/researches/research-wifi-sensing-cover.png
importance: 2022
category: research
date: 2022-10-01
show: true

---

## Introduction to WiFi Sensing

WiFi sensing leverages common wireless signals from everyday WiFi routers to detect and analyze human activities and behaviors without using intrusive devices like cameras or wearables. It has profound implications for convenience, privacy, and security in smart environments.

Imagine your WiFi router recognizing who enters your home, sensing unauthorized access, or detecting unusual activity—all invisibly. WiFi sensing achieves this by analyzing how human movements affect WiFi signal propagation, thus providing a powerful tool for security, healthcare, and smart home applications.

## WiFi-Based User Authentication

### Gesture-Independent Authentication

In one innovative approach, we explore how to authenticate users based solely on their unique physiological characteristics, irrespective of specific gestures or movements. Our system, **FreeAuth**, captures subtle differences in individuals' physiology as they move, reflected in statistical patterns of WiFi signals. By using a specialized adversarial learning model (shown in `Fig. 1`), FreeAuth extracts these unique, gesture-independent features and successfully distinguishes users with a high degree of accuracy.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/researches/research-wifi-sensing-freeauth-01.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 1 System Illustration of **FreeAuth**.
</div>

`Fig. 2` presents the detailed architecture of the adversarial neural network used in FreeAuth. It comprises three critical components: a Convolutional Neural Network (CNN)-based feature extractor, a Recurrent Neural Network (RNN)-based gesture suppressor, and a Gaussian Mixture Model (GMM)-based user authenticator. The CNN effectively extracts fine-grained signal features, while the RNN suppresses gesture-specific characteristics to emphasize invariant user traits. Finally, the GMM-based authenticator leverages statistical distributions to robustly distinguish individual users. This multi-layered architecture ensures effective gesture-independent authentication by focusing on physiological uniqueness.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/researches/research-wifi-sensing-freeauth-02.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 2  **FreeAuth**'s architecture of the adversarial neural network.
</div>

**Innovation:**

* Utilizes adversarial learning to distinguish between gesture-specific and user-specific signal patterns.
* First system to achieve gesture-independent authentication effectively.

**Results and Applications:**

* Achieved $91.3\%$ authentication accuracy for known gestures, $88.5\%$ for undefined gestures.
* Suitable for secure, seamless user verification in smart homes, offices, and IoT environments.

### Multi-User Authentication

Extending WiFi-based authentication to scenarios involving multiple simultaneous users, **MultiAuth** uses a single WiFi device to authenticate several users at once. By profiling the multipath components—how signals bounce off different individuals—our innovative algorithm (MUTA) effectively separates signals attributed to different people. `Fig. 3` visually demonstrates how this multipath separation clearly distinguishes multiple users.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/researches/research-wifi-sensing-multiauth-01.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 3  **MultiAuth**: ToA measurement with CSI phase shifts.
</div>

`Fig. 4` highlights how MultiAuth successfully distinguishes different users based on their distinct behavioral patterns in time-frequency spectrograms. The variations in limb movements, intervals between actions, and motion changes create unique spectral patterns for each user, clearly visualized in the figure.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/researches/research-wifi-sensing-multiauth-02.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 4 Time-frequency spectrograms for two users.
</div>

`Fig. 5` outlines the detailed architecture of the dual-task neural network model used in MultiAuth. This model integrates Convolutional Neural Networks (CNN) and Recurrent Neural Networks (RNN) to effectively extract robust and fine-grained features from user behavior profiles. The shared CNN-RNN feature extractor supports both user authentication and activity recognition, enhancing the accuracy and reliability of the multi-user authentication process.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/researches/research-wifi-sensing-multiauth-03.png" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Fig. 5 **MultiAuth**'s architecture of CNN-RNN-based dual-task neural network model.
</div>

**Innovation:**

* MUTA algorithm for high-resolution separation of individual signal paths.
* Employs a dual-task neural network (CNN-RNN) for robust simultaneous authentication.

**Results and Applications:**

* Achieved an impressive $87.6\%$ accuracy in multi-user environments.
* Applicable in crowded spaces, collaborative workplaces, and gaming environments, significantly enhancing multi-user security.

## Practical Impact and Future Directions

Our WiFi sensing research transforms everyday WiFi routers into powerful, non-intrusive sensing and authentication devices. By focusing on real-world applicability—such as distinguishing multiple users simultaneously and authenticating without predefined gestures—we provide solutions directly addressing current limitations in smart environment security and privacy.

Moving forward, WiFi sensing technology could integrate deeper with everyday devices, enhancing security in homes, healthcare monitoring, and even public safety measures, shaping a future where sensing and security become invisible yet omnipresent elements of daily life.

## Highlight of This Article

WiFi sensing represents a groundbreaking advancement in smart technology, transforming ordinary WiFi routers into sophisticated sensing tools capable of recognizing and authenticating individuals invisibly. This technology bypasses traditional limitations by using ambient WiFi signals to distinguish unique physiological and behavioral characteristics, enabling both gesture-independent and simultaneous multi-user authentication. Systems like FreeAuth and MultiAuth utilize innovative algorithms and machine learning models to extract subtle yet distinctive signal patterns, ensuring reliable identification with impressive accuracy rates. Applicable in diverse scenarios from secure home access and collaborative workplaces to interactive gaming environments, WiFi sensing not only enhances user experience but significantly bolsters security and privacy. As we continue to explore this promising field, WiFi sensing holds the potential to seamlessly integrate into everyday life, fostering a future where intuitive, non-intrusive security measures become standard.


## Publications

<div hidden>
{% cite kong-infocom22 %}
{% cite kong-mobihoc21 %}
</div>
