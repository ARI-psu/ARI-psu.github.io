---
layout: post
title: "Robotic Depowdering for Additive Manufacturing via Pose Tracking"
date: 2022-02-24 12:00:00
categories: research
description: "Robotic Depowdering for Additive Manufacturing via Pose Tracking"
author: "Junyi Geng"
published: true
sidebar:  false
permalink: /depowdering/
image: /img/posts/2022-02-24-depowdering/depowdering_trim.gif
datatable: true
title_image: None
link-new-tab: true
---




With the rapid development of powder-based additive manufacturing, depowdering, a process of removing unfused powder that covers printed parts, has become a major bottleneck to further improve its productiveness. Traditional manual depowdering is extremely time-consuming and costly, and some prior automated systems lack adaptability to different parts. We introduce a robotic system to fully automate depowdering. The key component is a visual perception system, which consists of a pose tracking module that tracks the 6D pose of powder-occluded parts in real-time, and a progress estimation module that estimates the completion percentage. Our depowdering system can remove powder efficiently for various types of parts without causing any damage. To the best of our knowledge, this is one of the first vision-based, fully automated depowdering systems for additive manufacturing.

<figure>
 <img src="/img/posts/2022-02-24-depowdering/depowdering_setup.jpeg" style="width:59%" />
 <figcaption>
        (a) Examples of manual depowdering. Human operators use blowers, vacuums, and brushes to remove the unfused powder. (b) Overview
of our depowdering system. The point cloud sequence from 3D cameras is fed into the visual perception system to track the 6D pose of the powder-
occluded part. Based on the estimated pose, a depowdering path is generated for the robot to remove powder through vacuuming and air blasting.
 </figcaption>
</figure>


## Robotic Depowdering System 
The architecture of the depowdering system consists of a visual perception system (VPS), and a motion planning system (MPS). The VPS tracks the part pose in real-time, extracts the powder contour around printed parts, and estimates the depowdering progress. The progress is defined as the height
ratio between the visible portion of the part and the complete part. Then, based on the estimated pose and the powder contour, the MPS generates a depowdering path along the outer contour of the visible part surface.

<figure>
 <img src="/img/posts/2022-02-24-depowdering/depowdering_flowchart.jpg" style="width:89%" />
 <figcaption>
        The architecture of our system. The inputs to the system are the CAD model and the point cloud can. When the depowdering progress is at the  beginning phase, no tracking is performed, and the initial pose is used. Once the progress exceeds the pre-defined threshold, the core algorithm "conditional update ICP" starts running. The robot first removes powder through vacuuming, and then finishes up depowdering by air blasting.
 </figcaption>
</figure>

## Visual Perception System  
The goals of the VPS are to: (1) track the current 6D part pose in real-time. (2) identify the powder contour around the part and estimate the depowdering progress. With the known initial pose and the CAD model, we formulate the pose tracking problem as a real-time registration problem. The traditional ICP is able to align a source point cloud to a target point cloud by minimizing the L2 error without relying on feature extraction.

One major challenge for ICP is the target appearance variation. A common practice to address this is to update the template based on the current object appearance. However, neither using the entire CAD model as a template or update the template every frame by taking the overlap between the CAD model and the current point cloud scan is ideal. Because it either results in a mismatch between the template or the target or template quickly becomes erroneous

We propose a conditional template update strategy for ICP to avoid accumulated template update errors. Specifically, the template is updated only when the part appearance has changed significantly. In depowdering, this happens either when (1) more part surface becomes visible as more powder is cleaned or (2) printed parts have moved either by the depowdering tool or due to the loss of balance. Either scenario causes the powder distribution to change.

<figure>
 <img src="/img/posts/2022-02-24-depowdering/depowdering_trim.gif" style="width:59%" />
 <figcaption>
        Automatic Robotic Depowdering.
 </figcaption>
</figure>


### Related Paper

@article{liu2022robotic,
  title={Robotic Depowdering for Additive Manufacturing Via Pose Tracking},
  author={Liu, Zhenwei and Geng, Junyi and Dai, Xikai and Swierzewski, Tomasz and Shimada, Kenji},
  journal={IEEE Robotics and Automation Letters},
  volume={7},
  number={4},
  pages={10770--10777},
  year={2022},
  publisher={IEEE}
}