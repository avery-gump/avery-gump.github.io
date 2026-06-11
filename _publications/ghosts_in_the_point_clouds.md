---
title: "Ghosts in the Point Clouds: De-glaring LiDAR in the Transient Domain"
collection: publications
category: conferences
permalink: /publications/ghosts-in-the-point-clouds
excerpt: 'In this work we looked at an overlooked but critical failure mode in SP-LiDAR known as glare (or to the LiDAR community bloom).'
date: 2026-08-06
venue: 'CVPR'
slidesurl: '/files/ghosts_in_the_point_clouds/slides.pptx'
paperurl: '/files/ghosts_in_the_point_clouds/paper.pdf'
citation_key: 'ghosts2026'
arxiv: "https://arxiv.org/abs/2605.24753"
---
<div style="position: relative; padding-bottom: 56.25%; height: 0; overflow: hidden; max-width: 100%; background: #000; border-radius: 4px; box-shadow: 0 2px 8px rgba(0,0,0,0.15); margin: 30px 0;">
  <iframe 
    src="https://www.youtube.com/embed/GOt1ORUL8U4" 
    style="position: absolute; top: 0; left: 0; width: 100%; height: 100%; border: 0;" 
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" 
    allowfullscreen>
  </iframe>
</div>

## Problem 
Modern LiDARs are rapidly transitioning from bulky, mechanically scanned systems to ultra-compact, low-cost, solid-state arrays. This miniaturization—while enabling scalability, affordability, and camera-like data structures—introduces a new and severe failure mode: internal-multipath glare. When light from a bright or retroreflective surface reflects and scatters within the LiDAR, light that should reach a single pixel spreads across the pixel array. The resulting artifacts create phantom objects, obscure real ones, and produce safety-critical ``ghosts in the point clouds.'' This paper introduces a physically grounded sensing model and algorithmic techniques for addressing this effect. We show that internal glare can be represented as a linear, scene-independent operator—the Transient Glare Spread Function (TGSF)—acting on the transient measurements. Building on this model, we develop a training-free approach that operates on low-level LiDAR detections (or echoes) prior to point-cloud formation, leveraging knowledge of the glare spread function to reason about the likelihood of each detection arising from glare. The resulting approach is compatible with existing LiDAR signal-processing pipelines, and deployable on unmodified commercial sensors. Using experiments with real single-photon LiDAR hardware, we demonstrate substantial suppression of severe glare artifacts while preserving true scene structure.

Below see some of our results from this work, see the paper for more detail! Project page soon to be update to include more information as well.

## Results
![Figure 4: Final cropped results](/images/ghosts_in_the_point_clouds_images/results_1.png)

![Figure 4: Final cropped results](/images/ghosts_in_the_point_clouds_images/results_2.png)



<iframe 
  src="https://1drv.ms/p/c/755d80330a742869/IQRJcLYTZzBRToA4rehiquAgAar4tbnmlPbfYnrVJ2pJkqw?em=2&amp;wdAr=1.7777777777777777"
  style="width: 100%; aspect-ratio: 16 / 9; border: none; border-radius: 4px;" 
  title="PowerPoint Viewer"
  allowfullscreen="true">
  This is an embedded <a target="_blank" href="https://office.com">Microsoft Office</a> presentation, powered by <a target="_blank" href="https://office.com/webapps">Office</a>.
</iframe>
