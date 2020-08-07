---
layout: posts
title: "Aided Target Recognition using Imprecise and Uncertain Data"
date: 2019-12-22
categories: [research]
tags: [aided target recognition]
header:
  teaser: /photos/atr/weak_bbox.JPG
---

<figure>
    <a href="/photos/atr/weak_bbox.JPG"><img src="/photos/atr/weak_bbox.JPG"></a>
    <figcaption>Two targets from the DSIAC dataset.  Canonical bounding boxes are shown in green while imprecise, "relaxed" bounding boxes are shown in blue.</figcaption>
</figure>

Target detection is a paramount area of research in the field of remote sensing which aims to locate an object or region of interest while suppressing unrelated objects and information (Geng 2017, Chaudhuri 1995, Zare 2018).  Traditional supervised learning approaches require extensive amounts of highly precise, sample-level or pixel-level groundtruth to guide algorithmic training.  However, acquiring large quantities of accurately labeled training data can be expensive, both in terms of time and resources, and in some cases may be unattainable.  

<figure>
    <a href="/photos/atr/weak_labels.JPG"><img src="/photos/atr/weak_labels.JPG"></a>
    <figcaption>Examples of weak labels.</figcaption>
</figure>

The figures in this post show frames taken from the DSIAC MS-003-DB dataset, which displays mid-wave infrared (MWIR) video segments of moving military vehicles taken at approximately 30 frames per second (FPS).  Many computer vision algorithms have already been developed to perform target detection using canonical bounding boxes (shown in green in the top figure).  However, drawing tight boxes around targets in each video frame is extremely tedious and time consuming.  An alternative is to allow annotators to provide less precise labels for each frame, such as relaxed bounding boxes (shown in blue in the top figure) or small subsets of target pixels such as single dots or scribbles (shown in the middle figure).  Images can even be annotated at a high level as *including* or *excluding* target pixels, as shown in the bottom figure. 

<figure class="half">
    <a href="/photos/atr/target_img.JPG"><img src="/photos/atr/target_img.JPG"></a>
    <a href="/photos/atr/bg_img.JPG"><img src="/photos/atr/bg_img.JPG"></a>
    <figcaption>Example target detection training images using image-level labels. Images are labeled as either containing or exluding target pixels somewhere in the frame.</figcaption>
</figure>

While the benefits of imprecise labels are apparent, current weak learning approaches in the literature are drastically outperformed by their strictly supervised counterparts in pixel-level target detection tasks.  Our current efforts in this area of research are focused on developing dimensionality reduction and manifold learning approaches which promote class discriminability for target detection applications.  In contrast to traditional approaches, our work learns from weakly-labeled groundtruth.


### References

* A. Zare, C. Jiao and T. Glenn, "Discriminative Multiple Instance Hyperspectral Target Characterization" in *IEEE Trans. Pattern Anal. Mach. Inteli.* vol. 40, num 10, pp 2342-2354. Oct. 2018. 

* X. Geng, L. Ji and Y. Zhao, "The basic equation for target detection in remote sensing," in *CoRR*. 2017.

* B. Chaudhuri and S. Parui, "Target Detection: Remote Sensing Techniques for Defence Applications," in *Defence Science Journal.* vol 45, pp 285-291. Apr. 1995.