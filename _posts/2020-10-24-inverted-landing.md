---
layout: post
title: "Bio-inspired Inverted Landing Strategy in a Small Aerial Robot Using Policy Gradient"
date: 2020-10-24 12:00:00
categories: research
description: "Bio-inspired Inverted Landing"
author: "Junyi Geng"
published: true
sidebar:  false
permalink: /inverted/
image: /img/posts/2020-10-24-inverted-landing/title_post.png
datatable: true
title_image: None
link-new-tab: true
---



Landing upside down is a challenging aerobatic feat that is rountinely performed by bats and many insects species such as flies, however, it is rarely achieved in small aerial robots using their onboard resources. Such capability is essential for small aerial robots as it not only expands the repertoire of aerobatic maneuvers, but also enables the robots to perch robustly on surfaces of various inclinations.
Previous work has only achieved arguably less difficult landing types on horizontal, vertical or inclined surfaces with the help of external motion tracking or with specialized grasp mechanisms. 
We propose a bio-inspired inverted landing strategy using computationally efficient Relative Retinal Expansion Velocity (RREV) as a visual cue. This landing strategy consists of a sequence of two motions, i.e. an upward acceleration and a rapid angular maneuver. A policy search algorithm is applied to optimize the landing strategy and improve its robustness by learning the transition timing between the two motions and the magnitude of the
target body angular velocity.

<figure>
 <img src="/img/posts/2020-10-24-inverted-landing/framework.png" style="width:50%" />
 <figcaption>
        Overview of the inverted landing problem. This study consists of three parts: the reinforcement learning agent which learns the high level
parameters for the bio-inspired landing strategy; the low level controller which controls the motion of the quadrotor according to the high level
parameters and the states it received; and the simulated landing environment and quadrotor.
 </figcaption>
</figure>


<figure>
 <img src="/img/posts/2020-10-24-inverted-landing/fly_landing.png" style="width:60%" />
 <figcaption>
        An example of the inverted landing of a fly and the visual cue RREV. (a) Flies land upside down on the ceiling by excuting a sequence of well coordinated behavioral modules. (b) The Relative Retina Expansion Velocity (RREV) is due to the looming stimuli when flies approach the ceiling.
 </figcaption>
</figure>


## Bio-Inspired Landing Strategy
The inverted landing strategy extracted from the flies underlines a sequence of two motions: an upward acceleration and a rapid body rotation. More importantly, the transition timing of the two motions is determined by a threshold of RREV, and furthermore, the desired magnitude of the rotational maneuvers is linearly related to the RREV, and two other visual cues that encode the relative fore/aft and lateral ceiling rotation. Note that, as inspired by the flies' landing strategy, the visual feedback is only used to trigger and determine the target degree of the angular maneuver,
while it is not used during the angular maneuver per se, which is visually open-loop . 

This landing strategy is simplified in two ways to apply to the aerial robot. First, as the quadrotor is symmetric in longitudinal and lateral, the rotation motion in the landing is restricted to only pitch. Second, the forward motion is assumed to be small in this work so that the fore/aft visual cue is negligible.

<figure>
 <img src="/img/posts/2020-10-24-inverted-landing/RL.png" style="width:50%"  />
 <figcaption>
        The reinforcement learning agent. The agent learns the distribution of two meta parameters, which are the transition timing between the two motions executed in the landing strategy, and the gain which determines the magnitude of the rotation velocity, respectively.
 </figcaption>
</figure>

## Learning Process
To adapt and optimize the landing strategy learned from flies to a robot, we choose to use model-free Reinforcement Learning (RL) in this work.
We present an application of the SyS-PEPG algorithm on a simulated nano quadrotor with the goal of achieving inverted landing on a ceiling. It consists of three parts (1) a RL agent which learns high level meta parameters; (2) the low level flight controller which generates desired rotor speed according to the high level parameters and quadrotor states it received; and (3) a simulated quadrotor with landing environment.

The quadrotor is assumed to be able to extract the visual cue RREV (which can be calculated directly from the optical flow using the optical flow sensor available to the quadcopter). The SyS-PEPG algorithm learns the distribution of two high level meta parameters, i.e. the threshold for RREV which determines the timing of the transition of the two motion primitives, and the gain which determines the magnitude of angular velocity.

<figure>
    <img src="/img/posts/2020-10-24-inverted-landing/results_a.png" style="width:55%" />
    <img src="/img/posts/2020-10-24-inverted-landing/results_b.png" style="width:42%" />
    <figcaption>
        A sample of a successful inverted landing. (a) The position and the animated landing sequence. (b) The time trajectory of RREV, linear
velocity, attitude, and angular velocity of the quadrotor.
    </figcaption>
</figure>


## Video



### Publication
```
@inproceedings{liu2020bio,
  title={Bio-inspired inverted landing strategy in a small aerial robot using policy gradient},
  author={Liu, Pan and Geng, Junyi and Li, Yixian and Cao, Yanran and Bayiz, Yagiz E and Langelaan, Jack W and Cheng, Bo},
  booktitle={2020 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS)},
  pages={7772--7777},
  year={2020},
  organization={IEEE}
}

```
