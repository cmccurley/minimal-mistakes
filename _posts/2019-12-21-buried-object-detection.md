---
layout: posts
title: "Multi-Sensor Fusion for Buried Object Detection"
date: 2019-12-21
categories: [research]
tags: [landmine]
header:
  teaser: /photos/landmine/landmine.jpg
---

<figure>
    <a href="/photos/landmine/landmine.jpg"><img src="/photos/landmine/landmine.jpg"></a>
    <figcaption>Partially-buried explosive hazard.</figcaption>
</figure>

Buried explosive hazard detection is a particularly difficult problem which has been investigated for years. *Explosive hazard detection* (EHD) systems typically employ one or more sensors to extract information about and underground scene.  For example, *wide-band electromagnetic induction* (WEMI) sensors, or metal detectors, send time-varying electromagnetic fields through the ground to energize conductive objects and read the resulting relaxation energies.  Alternatively, *ground penetrating radar* (GPR) emit signals from an array of sensors and collect reflected waves to indicate subsurface objects.  Either of these sensors can be used to discover buried threats, independently.  However, EMI can only locate conductive objects (typically metal) and GPR can only determine whether an object is located underground, but not if that object is a hazard, a rock, or a piece of debris.  It is intuitive that these two sensors should be fused to provide supporting or contrastive context to aid in anomaly detection decision making.  

<figure>
    <a href="/photos/landmine/gpr.jpg"><img src="/photos/landmine/gpr.jpg"></a>
    <figcaption>Ground-penetrating radar scans.  Object hyperbolas are captured by the red boxes, created from the two ends and peak points denoted by blue crosses.</figcaption>
</figure>

The majority of my work on this project focused on implementing and comparing anomaly detection algorithms for EMI sensors.  Target detection with EMI data poses a few distinct challenges.  First, there is a wide variety of explosive hazards to be detected, ranging from small anti-personnel to large anti-tank, and from high-metal to non-conductive.  Second, traditional target detection algorithms rely on discovering anomalous data points from a uniform background.  However, soil conditions are highly varying, which makes it difficult to characterize the background class.  Additionally, conductive soils provide destructive interference to EMI signals.  Finally, traditional supervised learning requires highly accurate groundtruth for algorithmic training.  While exact locations of targets may be known from a *Universal Transverse Mercator* (UTM) or *Global Positioning System* (GPS), the true extent of signal propagation is difficult to obtain in practice.  For these reasons, my fellow researchers and I explored methods to remove characteristic soil interference and anomaly detection using weak and ambiguous groundtruth and compared these to popular methods in the literature.    

To see some of our work in these areas, check out my paper [here](https://faculty.eng.ufl.edu/machine-learning/2019/03/comparison-of-hand-held-wemi-target-detection-algorithms/). 


