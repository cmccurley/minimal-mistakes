---
layout: posts
title: "Aided Target Recognition using Imprecise and Uncertain Data"
date: 2019-12-21
categories: [research]
tags: [aided target recognition]
header:
  teaser: /photos/atr/weak_bbox.JPG
---

<figure>
    <a href="/photos/atr/weak_bbox.JPG"><img src="/photos/atr/weak_bbox.JPG"></a>
    <figcaption>Two targets from the DSIAC dataset.  Canonical bounding boxes are shown in green while less precise "relaxed" bounding boxes are shown in blue.</figcaption>
</figure>

Target detection is a paramount area of research in the field of remote sensing which aims to locate an object or region of interest while suppressing background (Geng 2017, Chaudhuri 1995).  Target detection can be formulated as a two-class classification problem where samples belonging to a class of interest are discriminated from a global background distribution (Zare 2016).  The goal of target detection in remote sensing is to correctly classify every true positive instance (TP) in a given scene while denoting as few false alarms (FA) as possible (non-target samples predicted as targets).  The objective of learning is to discover prototypes which represent both the target and background classes which can be used to classify a sample at test.  Traditional supervised learning approaches require extensive amounts of highly precise groundtruth to guide algorithmic training.  However, acquiring large quantities  of accurately labeled training data can be expensive both in terms of time and resources, and in some cases, may even be infeasible to obtain.  

<figure>
    <a href="/photos/atr/weak_labels.JPG"><img src="/photos/atr/weak_labels.JPG"></a>
    <figcaption>Examples of weak labels.</figcaption>
</figure>

The figures in this post show frames taken from the DSIAC MS-003-DB dataset, which demonstrates mid-wave infrared (MWIR) video segments of moving military vehicles taken at approximately 30 frames per second (FPS).  Many computer vision algorithms have already been developed to perform target detection using canonical bounding boxes (shown in green in the top figure).  However, drawing tight boxes around targets in each video frame is extremely tedious and time consuming.  It would be beneficial if an annotator could provide a less-restrictive form of label for each frame, such as a relaxed bounding box (shown in blue in the top figure) or as a small subset of target pixels such as single dot or scribble (shown in the middle figure).  Labeling burden could be decreased even further if a single frame could be labeled at a high level as *including* or *excluding* target pixels, as shown in the bottom figure. 

<figure class="half">
    <a href="/photos/atr/target_img.JPG"><img src="/photos/atr/target_img.JPG"></a>
    <a href="/photos/atr/bg_img.JPG"><img src="/photos/atr/bg_img.JPG"></a>
    <figcaption>Example target detection training images using image-level labels. Images are labeled as either containing or exluding target pixels somewhere in the frame.</figcaption>
</figure>

Our current efforts in this area of research are focused on developing dimensionality reduction and manifold learning approaches which promote class discriminability for target detection applications.  In contrast to traditional learning approaches, our work uses weakly-supervised labels for training.


### References

* A. Zare, C. Jiao and T. Glenn, "Discriminative Multiple Instance Hyperspectral Target Characterization" in *IEEE Trans. Pattern Anal. Mach. Inteli.* vol. 40, num 10, pp 2342-2354. Oct. 2018. 

* X. Geng, L. Ji and Y. Zhao, "The basic equation for target detection in remote sensing," in *CoRR*. 2017.

* B. Chaudhuri and S. Parui, "Target Detection: Remote Sensing Techniques for Defence Applications," in *Defence Science Journal.* vol 45, pp 285-291. Apr. 1995.