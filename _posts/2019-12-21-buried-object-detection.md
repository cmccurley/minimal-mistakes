---
layout: single
title: "Multi-Sensor Fusion for Buried Object Detection"
date: 2019-12-21
categories: [research]
tags: [landmine, weak learning, uncertain/imprecise labels, explosive hazard detection, target detection, multiple instance learning]
header:
  teaser: /photos/landmine/landmine.jpg
---

<figure>
    <a href="/photos/landmine/landmine.jpg"><img src="/photos/landmine/landmine.jpg"></a>
    <figcaption>Figure 1: Partially-buried explosive hazard.</figcaption>
</figure>

Buried *Explosive hazard detection* (EHD) is a particularly difficult problem which has been investigated for years. The goal of EHD is to *safely* detect and classify *underground* threats, from *above* ground.  A variety of sensors are used to extract information about underground scenes.  For example, *wide-band electromagnetic induction* (WEMI) sensors (metal detectors) send time-varying electromagnetic fields through the ground to energize conductive objects and read the resulting relaxation energies.  Alternatively, *ground penetrating radar* (GPR) emit signals from an array of sensors and collect reflected waves to indicate subsurface objects.  Either of these sensors can be used to independently discover buried threats.  However, EMI can only locate conductive objects and GPR alone cannot determine whether an object located underground is an explosive hazard, a rock, or a piece of debris.  Because each sensor is limited in fundamentally opposing ways, it is intuitive that they should be fused to provide supporting or contrasting context to aid in algorithmic decision making.  

<figure>
    <a href="/photos/landmine/gpr.jpg"><img src="/photos/landmine/gpr.jpg"></a>
    <figcaption>Figure 2: Ground-penetrating radar scans.  Object hyperbolas are captured by the red boxes created from the two ends and peak points denoted by blue crosses.</figcaption>
</figure>

While it is easy to understand *why* EHD sensors should be fused, actually combining them is difficult in practice.  Each sensor usually operates at different spatial and temporal resolutions.  This means that while the locations of training targets my be given by *Universal Transverse Mercator* (UTM) or *Global Positioning System* (GPS) coordinates, one-to-one correspondence between sampled points does not exist.  Because matching incorrect points can be highly detrimental to the algorithmic learning process, methods should be used which learn from weak and imprecise groundtruth.  Moreover, fusion can be difficult due to imprecision which stems from characteristics of the individual sensors in response to environmental conditions.  For example, traditional target detection algorithms for WEMI sensors rely on discovering anomalous data points from a uniform background.  However, soil conditions are, in practice, highly varying, and magnetic soils provide destructive interference to EMI signals, making SNR-based detection methods difficult. 

For these reasons, my fellow researchers and I explored methods to improve WEMI detection and classification for EHD sensor fusion.  Specifically, we sought to remove characteristic soil interference and perform anomaly detection using weak and ambiguous groundtruth.  

To see some of our work in these areas, check out my paper [here]({% link _posts/2019-12-28-Comparison-of-Handheld.md %}). 


