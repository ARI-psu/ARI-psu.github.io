---
layout: post
title: "Flying Calligrapher: Contact-Aware Motion and Force Planning and Control for Aerial Manipulation"
date: 2024-08-31 12:00:00
categories: 
  - highlights
  - research
description: "Aerial Writing for Art"
author: "Xiaofeng Guo"
published: true
sidebar:  false
permalink: /flyingcalligraphy/
image: /img/posts/2024-08-30-flyingcalligraphy/aerialwriting.gif
datatable: true
title_image: None
link-new-tab: true
---

### Aerial Writing for Art

Aerial manipulation has gained interest for completing high-altitude tasks that are challenging for human workers, such 
as contact inspection and defect detection. Previous research has focused on maintaining static contact points or forces. 
This letter addresses a more general and dynamic task: simultaneously tracking time-varying contact force and motion 
trajectories on tangential surfaces. We propose a pipeline that includes contact-aware trajectory planning to generate 
dynamic, feasible trajectories and a hybrid motion-force controller to compensate for contact and friction forces. We 
demonstrate the approach on an aerial calligraphy task using a novel sponge pen design as the end-effector. Additionally, we developed a touchscreen interface for flexible user input. Experiments show our method can effectively draw diverse letters, achieving an IoU of 0.59 and an end-effector position tracking RMSE of 2.93 cm.

<video width="1280" height="960" controls>
  <source src="/img/posts/2024-08-30-flyingcalligraphy/teaser.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>


## Approach Overview
<figure>
 <img src="/img/posts/2024-08-30-flyingcalligraphy/pipeline.png"/>
 <figcaption>
         Pipeline of the proposed system. 
 </figcaption>
</figure>

Users either manually define the target strokes or draw the target letter through a touchscreen interface. Then, the trajectory planning module generates a dynamic-feasible motion-force trajectory. A hybrid motion and force controller is designed for the UAM to track the reference trajectory. Finally, a novel end-effector pen is designed for the UAM to draw the target letters.


<!-- <h2 class="title is-2" style="text-align: center;">Experiment Results</h2> -->
<section class="section">
  <div class="container is-max-desktop">
    <div class="columns is-centered">
      <div class="column is-12">
        <div class="columns is-centered">
          <div class="column is-12">
            <h2 class="title is-3">Experiment Results</h2>
          </div>
        </div>
          <!-- add text at the top left of these three videos -->
        <div class="title is-4">
          <p>
            Single Letter Drawing
          </p>  
        </div>
        <div class="title is-6">
          <p>write letter 'A'</p>        
        </div>
        <div class="columns is-centered">
          <div class="column is-4">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write_a_20_1.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>trial 1</p>        
            </div>
          </div>
          <div class="column is-4">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write_a_21_1.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>trial 2</p>        
            </div>
          </div>
          <div class="column is-4">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write_a_22_1.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>trial 3</p>        
            </div>
          </div>
        </div>
        <div class="title is-6">
          <p>write letter 'I'</p>        
        </div>
        <div class="columns is-centered">
          <div class="column is-4">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write_i_20_1.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>trial 1</p>        
            </div>
          </div>
          <div class="column is-4">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write_i_21_1.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>trial 2</p>        
            </div>
          </div>
          <div class="column is-4">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write_i_22_1.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>trial 3</p>        
            </div>
          </div>
        </div>
        <div class="title is-6">
          <p>write letter 'R'</p>        
        </div>
        <div class="columns is-centered">
          <div class="column is-4">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write_r_20_1.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>trial 1</p>        
            </div>
          </div>
          <div class="column is-4">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write_r_21_1.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>trial 2</p>        
            </div>
          </div>
          <div class="column is-4">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write_r_22.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>trial 3</p>        
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="container is-max-desktop">
    <div class="columns is-centered">
      <div class="column is-12">
        <div class="title is-4">
          <p>
            Complex Letter Drawing
          </p>  
        </div>
        <div class="columns is-centered">
          <div class="column is-12">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write_2024_10x.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>writing '2024'</p>        
            </div>
          </div>
        </div>
        <div class="columns is-centered">
          <div class="column is-12">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/zhixingheyi_10x.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>writing a Chinese idiom "知行合一" (meaning: Unity of Knowledge and Action)
              </p>        
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

  <div class="container is-max-desktop">
    <div class="columns is-centered">
      <div class="column is-12">
        <div class="title is-4">
          <p>
            Ablation Study
          </p>  
        </div>
        <div class="title is-6">
          <p>
            Control Comparison  
          </p>
        </div>
        <div class="columns is-centered">
          <div class="column is-6">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write_r_control_baseline.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>without contact-related ff</p>        
            </div>
          </div>
          <div class="column is-6">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write_r_21_1.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>our method
              </p>        
            </div>
          </div>
        </div>
        <div class="title is-6">
          <p>
            Trajectory Planning Comparison
          </p>
        </div>
        <div class="columns is-centered">
          <div class="column is-6">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write_i_0_planning_baseline.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>with equal distance sample trajecotry generation</p>        
            </div>
          </div>
          <div class="column is-6">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write_i_21_1.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>our method
              </p>        
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
  <div class="container is-max-desktop">
    <div class="columns is-centered">
      <div class="column is-12">
        <div class="title is-4">
          <p>
            Speed Comparison
          </p>  
        </div>
        <div class="columns is-centered">
          <div class="column is-4">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write_i_21_1.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>vmax = 24.3 cm/s</p>        
            </div>
          </div>
          <div class="column is-4">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write-i-15.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>vmax = 33.1 cm/s
              </p>        
            </div>
          </div>
          <div class="column is-4">
            <video controls autoplay loop muted playsinline 
              src="/img/posts/2024-08-30-flyingcalligraphy/write-i-17.mp4" type="video/mp4">
            </video>
            <div class="content has-text-centered">
              <p>vmax = 40.2 cm/s
              </p>        
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</section>


  <div class="container">
    <h2 class="title is-2" id="press-coverage">Media</h2>
    <br>
    <div class="columns is-centered">
      <div class="column is-centered has-text-centered">
        <a target="_blank" href="https://spectrum.ieee.org/video-friday-unitree-talks-robots">
          <img src="https://upload.wikimedia.org/wikipedia/commons/7/7d/IEEE-Spectrum.svg" width="70%"/>
        </a>
      </div>
  </div>


<section class="section" id="Publication">
  <div class="container is-max-desktop content">
    <h2 class="title">BibTeX</h2>
    <pre><code>@article{guo2024flying,
       author    = {Guo, Xiaofeng and He, Guanqi and Xu, Jiahe and Mousaei, Mohammadreza and Geng, Junyi and Scherer, Sebastian and Shi, Guanya},
       title     = {Flying Calligrapher: Contact-Aware Motion and Force Planning and Control for Aerial Manipulation},
       journal   = {IEEE Robotics and Automation Letters},
       year      = {2024},
       pages     = {Under Review}
}</code></pre>
  </div>
</section>