---
layout: post
title: "Flying Hand: End-Effector-Centric Framework for Versatile Aerial Manipulation Teleoperation and Policy Learning"
date: 2025-05-09 12:00:00
categories: research
description: ""
author: "Yuanzhu Zhan"
published: true
sidebar:  false
permalink: /flying_hand/
image: /img/posts/2025-05-09-flying_hand/pipeline.png
datatable: true
title_image: None
link-new-tab: true
---


Aerial manipulation has recently attracted increasing interest from both industry and academia. Previous approaches have demonstrated success in various specific tasks. However, their hardware design and control frameworks are often tightly coupled with task specifications, limiting the development of cross-task and cross-platform algorithms. Inspired by the success of robot learning in tabletop manipulation, we propose a unified aerial manipulation framework with an end-effector-centric interface that decouples high-level platform agnostic decision-making from task-agnostic low-level control. Our framework consists of a fully-actuated hexarotor with a 4-DoF robotic arm, an end-effector-centric whole-body model predictive controller, and a high-level policy. The high-precision end-effector controller enables efficient and intuitive aerial teleoperation for versatile tasks and facilitates the development of imitation learning policies. Real-world experiments show that the proposed framework significantly improves end-effector tracking accuracy, and can handle multiple aerial teleoperation and imitation learning tasks, including writing, peg-in-hole, pick and place, changing light bulbs, etc. We believe the proposed framework provides one way to standardize and unify aerial manipulation into the general manipulation community and to advance the field.


## Approach Overview
<figure>
 <img src="/img/posts/2025-05-09-flying_hand/pipeline.png"/>
 <figcaption>
       Pipeline
 </figcaption>
</figure>

## Experiment Results
##### Control Performance
<video controls autoplay loop muted playsinline 
       src="/img/posts/2025-05-09-flying_hand/endeffector_control_experiment.mp4" type="video/mp4">
</video>

##### EE-Centric MPC
<video controls autoplay loop muted playsinline 
       src="/img/posts/2025-05-09-flying_hand/collision_avoidence.mp4" type="video/mp4">
</video>

##### Autonomous Policy Learning
<video controls autoplay loop muted playsinline 
       src="/img/posts/2025-05-09-flying_hand/peginhole_2.mp4" type="video/mp4">
</video>

<video controls autoplay loop muted playsinline 
       src="/img/posts/2025-05-09-flying_hand/valve_rotate_3.mp4" type="video/mp4">
</video>

##### Human Teleoperation
<video controls autoplay loop muted playsinline 
       src="/img/posts/2025-05-09-flying_hand/pickandplace_glue.mp4" type="video/mp4">
</video>


<video controls autoplay loop muted playsinline 
       src="/img/posts/2025-05-09-flying_hand/pickandplace_bluetape.mp4" type="video/mp4">
</video>

<!-- ### Publication -->
<section class="section" id="Publication">
  <div class="container is-max-desktop content">
    <h2 class="title">BibTeX</h2>
    <pre><code>@article{he2025flying,
      title={Flying Hand: End-Effector-Centric Framework for Versatile Aerial Manipulation Teleoperation and Policy Learning},
      author={He, Guanqi and Guo, Xiaofeng and Tang, Luyi and Zhang, Yuanhang and Mousaei, Mohammadreza and Xu, Jiahe and Geng, Junyi and Scherer, Sebastian and Shi, Guanya},
      journal={arXiv preprint arXiv:2504.10334},
      year={2025}
    }
    </code></pre>
  </div>
</section>