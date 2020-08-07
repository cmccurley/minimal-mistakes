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

Buried *Explosive hazard detection* (EHD) is a particularly difficult problem which has been investigated for years. The goal of EHD is to both detect and classify underground threats without having to dig up the object which triggered and alarm.  Typically, one or more sensors are used to extract information about an underground scene.  For example, *wide-band electromagnetic induction* (WEMI) sensors (metal detectors) send time-varying electromagnetic fields through the ground to energize conductive objects and read the resulting relaxation energies.  Alternatively, *ground penetrating radar* (GPR) emit signals from an array of sensors and collect reflected waves to indicate subsurface objects.  Either of these sensors can be (and are) used to independently discover buried threats.  However, EMI can only locate conductive objects and GPR alone cannot determine whether an object located underground is an explosive hazard, a rock, or a piece of debris.  Because each sensor is limited in fundamentally opposing ways, it is intuitive that they should be fused to provide supporting or contrastive context to aid in anomaly detection decision making.  

<figure>
    <a href="/photos/landmine/gpr.jpg"><img src="/photos/landmine/gpr.jpg"></a>
    <figcaption>Ground-penetrating radar scans.  Object hyperbolas are captured by the red boxes, created from the two ends and peak points denoted by blue crosses.</figcaption>
</figure>

The majority of my work on this project focused on implementing and comparing anomaly detection algorithms for EMI sensors.  Target detection with EMI data poses a few distinct challenges.  First, there is a wide variety of explosive hazards to be detected, ranging from small anti-personnel to large anti-tank, and from high-metal to non-conductive.  Second, traditional target detection algorithms rely on discovering anomalous data points from a uniform background.  However, soil conditions are highly varying, which makes it difficult to characterize the background class.  Additionally, conductive soils provide destructive interference to EMI signals, making SNR-based detection methods difficult.  Finally, traditional supervised learning requires highly accurate groundtruth for algorithmic training.  While exact locations of targets may be known from a *Universal Transverse Mercator* (UTM) or *Global Positioning System* (GPS), the true extent of signal propagation is difficult to obtain in practice.  For these reasons, my fellow researchers and I explored methods to remove characteristic soil interference and perform anomaly detection using weak and ambiguous groundtruth.  

To see some of our work in these areas, check out my paper [here]({% link _posts/2019-12-28-Comparison-of-Handheld.md %}). 


