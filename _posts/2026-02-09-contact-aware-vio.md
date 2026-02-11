---
layout: post
title: "Aerial Manipulation with Contact-Aware Onboard Perception and Hybrid Control"
date: 2026-02-09 12:00:00
categories: research
description: "A Category-level Object 6D Pose and Shape Estimation Framework"
author: "Yuanzhu Zhan"
published: true
sidebar:  false
permalink: /contact-aware-vio/
image: /img/posts/2026-02-09-contact-aware-vio/real_world.gif
datatable: true
title_image: None
link-new-tab: true
---


Aerial manipulation (AM) promises to move Unmanned Aerial Vehicles (UAVs) beyond passive inspection to contact-rich tasks such as grasping, assembly, and in-situ maintenance. Most prior AM demonstrations rely on external motion capture (MoCap) and emphasize position control for coarse interactions, limiting deployability. We present a fully onboard perception–control pipeline for contact-rich AM that achieves accurate motion tracking and regulated contact wrenches without MoCap. The main components are (1) an augmented visual–inertial odometry (VIO) estimator with contact-consistency factors that activate only during interaction, tightening uncertainty around the contact frame and reducing drift, and (2) image-based visual servoing (IBVS) to mitigate perception–control coupling, together with a hybrid force–motion controller that regulates contact wrenches and lateral motion for stable contact. Experiments show that our approach closes the perception-to-wrench loop using only onboard sensing, yielding an velocity estimation improvement of 66.01% at contact, reliable target approach, and stable force holding—pointing toward deployable, in-the-wild aerial manipulation.


## Proposed Pipeline
<figure>
 <img src="/img/posts/2026-02-09-contact-aware-vio/Pipeline.png"/>
 <figcaption>
       Overview of the proposed pipeline
 </figcaption>
</figure>

The proposed pipeline has three key components: (1) A contact-aware VIO processes stereo imagery to produce vehicle/end-effector state estimates, activating contact factors only during interaction. (2) During approach, image-based visual servoing (IBVS) drives the platform using only the VIO-estimated body velocity. (3) Upon contact, a hybrid force–motion controller regulates the normal wrench while IBVS continues to track lateral motion, closing the perception-to-wrench loop with onboard sensing.

## Contact-Aware Visual-Inertial Odometry
<figure>
 <img src="/img/posts/2026-02-09-contact-aware-vio/pose_graph.png"/>
 <figcaption>
       Pose graph of the proposed contact-aware VIO
 </figcaption>
</figure>

Our method builds upon VINS-Fusion, where visual–inertial state estimation is expressed within a factor graph framework, and the system state is recovered through joint optimization of camera reprojection errors and IMU pre-integration constraints. While this formulation achieves high accuracy in general scenarios, it may suffer from drift when external interactions occur. To mitigate this issue, we extend it by introducing contact factors that leverage robot–environment interactions. In particular, when the system is in contact with a wall, the relative motion at the contact point is constrained, and this information is encoded as an additional factor in the graph. By incorporating such constraints, the estimator gains improved robustness and reduced drift, especially in environments with limited visual features or long-term operation.

## Experiment
  <div class="container is-max-desktop">
    <div class="columns is-centered">
      <div class="column is-12">
        <div class="title is-4">
          <p>
            Peg-in-hole simulation
          </p>  
        </div>
        <div class="columns is-centered">
          <div class="column is-6">
            <figure> 
              <img src="/img/posts/2026-02-09-contact-aware-vio/peginhole_view.png">
            </figure>
            <div class="content has-text-centered">
              <p>peg in hole Gazebo sim</p>        
            </div>
          </div>
          <div class="column is-6">
            <figure> 
              <img src="/img/posts/2026-02-09-contact-aware-vio/peginhole_vs_error.png">
            </figure>
            <div class="content has-text-centered">
              <p>alignment error</p>        
            </div>
          </div>
        </div>
        <div class="columns is-centered">
          <div class="column is-6">
            <figure> 
              <img src="/img/posts/2026-02-09-contact-aware-vio/peginhole_vs_radius_error.png">
            </figure>
            <div class="content has-text-centered">
              <p>scaling error</p>        
            </div>
          </div>
          <div class="column is-6">
            <figure> 
              <img src="/img/posts/2026-02-09-contact-aware-vio/peginhole_force.png">
            </figure>
            <div class="content has-text-centered">
              <p>force measurement</p>        
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

Real-world experiment
<figure>
  <img src="/img/posts/2026-02-09-contact-aware-vio/realshooting_stack.png"/>
  <figcaption>
       Snapshots of real-world experiments. (a) Visual servoing initialized. (b) Approaching the target. (c) Force holding.
  </figcaption>
</figure>

<figure> 
  <img src="/img/posts/2026-02-09-contact-aware-vio/realshooting_force.png">
  <figcaption>
    force measurement
  </figcaption>
</figure>

<figure> 
  <img src="/img/posts/2026-02-09-contact-aware-vio/realshooting_vx.png">
  <figcaption>
    velocity estimation error in contact direction
  </figcaption>
</figure>

## Video

<!-- {% youtube 3AMcM3uUaUw %} -->
<video controls autoplay loop muted playsinline 
       src="/img/posts/2026-02-09-contact-aware-vio/full-video.mp4" type="video/mp4">
</video>

<!-- ### Publication -->
<section class="section" id="Publication">
  <div class="container is-max-desktop content">
    <h2 class="title">BibTeX</h2>
    <pre><code>@misc{zhan2026aerialmanipulationcontactawareonboard,
      title={Aerial Manipulation with Contact-Aware Onboard Perception and Hybrid Control}, 
      author={Yuanzhu Zhan and Yufei Jiang and Muqing Cao and Junyi Geng},
      year={2026},
      eprint={2602.08251},
      archivePrefix={arXiv},
      primaryClass={cs.RO},
      url={https://arxiv.org/abs/2602.08251},
    }
</code></pre>
  </div>
</section>
