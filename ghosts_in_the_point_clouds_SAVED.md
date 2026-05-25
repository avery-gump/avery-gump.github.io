---
title: "Ghosts in the Point Clouds: De-glaring LiDAR in the Transient Domain"
collection: publications
category: conferences
permalink: /publication/ghosts-in-the-point-clouds
excerpt: 'TODO'
date: 8/6/2026
venue: 'CVPR'
slidesurl: '/files/qual_exam_presentation.pptx'
paperurl: 'http://academicpages.github.io/files/paper1.pdf'
citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
---
[INSERT VIDEO]


## Problem 
Lidar is undergoing a rapid transformation from complex, bulky, expensive mechanically spinning systems to more compact solid-state arrays. This transformation can be thought of as a transition from a unique isolated modality towards a camera-like architechture. Camera-fication of lidar brings with it many benefits as we can build up a well studied system. But it also comes with some new failure modes such as glare.



### What is Glare? 
Glare occurs in traditional cameras when there are bright objects in the scene being imaged e.g. the sun or headlights from a car. For active imaging systems such as dToF lidar, the glare comes from the emitted itself and objects in the scene that cause intense retro-reflective returns. Stop signs, traffic cones, and even common recreational equipment (such as bikes) all contain retroreflectors and can blind lidar. Not only do these obscure what is there this also causes high confidence detections for what is not there. 

The physical mechanism for this is internal multipath bounces. Lets consider a simple case [FIG 1 INSERT].

EXPLAIN FIGURE PANE BY PANE

...



### Why has it not been a problem sofar? 

Traditional scanning based systems (like those developed by popular manufacturers such as Velodyne) do not see this problem because they seperate the pixel arrays in what they refer to as detector groups. 

[IMAGE DETECTOR GROUPS]

for each group only one transmit/recieve pair is activated at a time in a 2D scanning fashion. This is not ideal for two reasons. Firstly, this scanning takes time, and with highly dynamic scenes this can be costly. Motion related artifacts appear more regularly, and less information can be acquired from the scene. We perform our experiments with a 1D scanning system which turns on transmit/recieve pairs in a horizontal band spanning 6 rows. Fully solid-state systems which is where the technology is heading would exhibit even more problematic glare, our method can be easily adapted to these systems.

## Solution

### How we model glare.
To model this glare first lets consider the forward model: 

This is a full description of what we refer to as the transient glare spread function (TGSF). In practice the transient component is well under the timing resolution of our sensor so we can drop this part and only consider the spatially varying glare spread function (GSF). We measure the GSF by turning off the emitter of our lidar device and pointing an ir flashlight at the reciever. To isolate the returns due to spread from other sources (incident light, multipath, noise) we use a small aperature at the end of a long baffle on the flashlight; we also capture three images, one with the flashlight on and two with the flashlight off (one before and one after the flashlight capture). We do this to isolate any noise due to darkcounts and subtract these averaged frames from the capture with the flashlight on. 

### High level solution.

At a high level, in theory, we can just invert this matrix apply a correction as such: 

$$
Ideal = G^{-1} Measured
$$

In practice, the problem is ill-posed and pseudo-inversion techiniques are poorly regularized and numerically unstable. This leads us to our solution from a statistical perspective. 

[MORE INFORMATION]

Echos vs Histograms. 

Pipeline Image 



### Pileup is a problem.
What is pileup? 

Why is it problematic here?

### Our solution.
[MATH] Histograms -> echos -> pileup correction -> confidence metric -> ...




## Results
We wanted to test our approach in a number of different realistic scenarios. WHAT SCENARIOS WE CONSTRUCTED. 

![Figure 4: Final cropped results](/images/ghosts_in_the_point_clouds_images/results_2.png)

![Figure 4: Final cropped results](/images/ghosts_in_the_point_clouds_images/results_1.png)


<iframe 
  src="https://view.officeapps.live.com/op/embed.aspx?src=https://avery-gump.github.io/files/qual_exam_presentation.pptx" 
  width="100%" 
  height="450px" 
  frameborder="0" 
  title="PowerPoint Viewer">
</iframe>

