---
layout: single
title: "Aided Target Recognition using Imprecise and Uncertain Data"
date: 2019-12-22
categories: [research]
tags: [aided target recognition, weak learning, uncertain/imprecise labels, target detection, manifold learning, dimensionality reduction, multiple instance learning]
header:
  teaser: /photos/atr/weak_bbox.JPG
---

<figure>
    <a href="/photos/atr/weak_bbox.JPG"><img src="/photos/atr/weak_bbox.JPG"></a>
    <figcaption>Figure 1: Two targets from the DSIAC MS-003-DB dataset.  Canonical bounding boxes are shown in green while imprecise, "relaxed" bounding boxes are shown in blue.  Red dots denote the centers of the targets.</figcaption>
</figure>

Target detection is a paramount area of research in the field of remote sensing which aims to locate an object or region of interest while suppressing unrelated objects and information (Geng 2017, Chaudhuri 1995, Zare 2018).  Traditional supervised learning approaches require extensive amounts of highly precise, sample-level or pixel-level groundtruth to guide algorithmic training.  However, acquiring large quantities of accurately labeled training data can be expensive, both in terms of time and resources, and may actually be unattainable in some cases.  

<figure>
    <a href="/photos/atr/weak_labels.JPG"><img src="/photos/atr/weak_labels.JPG"></a>
    <figcaption>Figure 2: Examples of weak labels.  The top left and right show examples of spot and scribble annotations, respectively.  The bottom left and right images demonstrate imprecise bounding box and image-level labels.</figcaption>
</figure>

The figures in this post show military and civilian vehicles captured by a mid-wave infrared (MWIR) sensor.  One could presumably design an algorithm to both detect vehicles in the MWIR frames and denote which classes the vehicles belong to.  In fact, many computer vision algorithms have already been developed to perform target detection using exact, pixel-level segmentation masks and tight, canonical bounding boxes (Figure 1).  Yet, pixel-level groundtruth are often subjective and drawing a tight box around every training target in a dataset is extremely tedious, often taking teams of annotators countless hours to complete.  A practical solution to strenuous labeling is to simply use *less precise* labels.  Examples of imprecise labels include: relaxed bounding boxes (Figure 1), spot labels (Figure 2), and scribble annotations (Figure 2).  As shown in Figure 3, images can even be annotated at a high level as *including* or *excluding* target pixels. 

<figure class="half">
    <a href="/photos/atr/target_img.png"><img src="/photos/atr/target_img.png"></a>
    <a href="/photos/atr/bg_img.png"><img src="/photos/atr/bg_img.png"></a>
    <figcaption>Figure 3: Example target detection training images using image-level labels. Images are labeled as "Target" if they contain target pixels somewhere in the frame.  Otherwise, they are annotated as "Background".</figcaption>
</figure>

While the benefits of imprecise labels are apparent, current approaches in the literature which learn from weakly annotated data are drastically outperformed by their strictly supervised counterparts in pixel-level target detection tasks.  Thus, our current efforts are focused on improving the mappings from weak annotations to pixel-level segmentations.  Presently, we are exploring the use of class-level manifold information to promote class discriminability for target detection.  In contrast to traditional approaches, our work learns from weakly-labeled groundtruth.


### References

* A. Zare, C. Jiao and T. Glenn, "Discriminative Multiple Instance Hyperspectral Target Characterization" in *IEEE Trans. Pattern Anal. Mach. Inteli.* vol. 40, num 10, pp 2342-2354. Oct. 2018. 

* X. Geng, L. Ji and Y. Zhao, "The basic equation for target detection in remote sensing," in *CoRR*. 2017.

* B. Chaudhuri and S. Parui, "Target Detection: Remote Sensing Techniques for Defence Applications," in *Defence Science Journal.* vol 45, pp 285-291. Apr. 1995.