---
layout: post
title: "Control, Estimation and Planning for Coordinated Transport of a Slung Load by a Team of Aerial Robots"
date: 2020-12-19 12:00:00
categories: research
description: "Cooperative Transport of a Slung Load using a Team of Aerial Robots"
author: "Junyi Geng"
published: true
sidebar:  false
permalink: /multilift/
image: /img/posts/2020-12-19-multilift/outdoor_short.gif
datatable: true
title_image: None
hero_image: /img/posts/2020-12-19-multilift/fly-payload.png
hero_height: is-large
remove_hero_title: true
link-new-tab: true
---




Transporting slung load using a team of cooperative aerial robots, or denoted by the term multilift, can increase the utility of a fleet of smaller aerial robots by enabling the transport of large, heavy payloads via coordinated transport, which frees us from developing vehicles for extra-large payloads that occur only infrequently. However, the complexity of the coupled system dynamics and the difficulty of payload manipulation and coordinated control lead to challenges in operational development.


## A Comprehensive Hierarchical Load-leading Control Strategy
The first challenge is what strategy to use to coordinately control the multilift so that the payload can be well manipulated. This is the core ingredient that determines the solutions of other parts of the system. The difficulty arises from the complexity of the multilift – the coupling between the aerial robots and the slung load. The complex coupling produces not only the high nonlinearity of the system, but also
imposes differing control requirements for each component. 

We have developed a comprehensive hierarchical control strategy for the multilift problem, where the payload can sense itself and lead the whole fleet. The strategy employs a “load-leading” design where the payload pose control, cable force computation, and robot kinematics commanding are achieved in a hierarchical manner. Unlike the conventional approach where the slung load is treated as an external disturbance of the robot formation, this approach proposes to attach sensors onboard the payload. It directly controls the payload pose while computing the required cable forces and robot states in real time. In this manner, the robots behaving as the actuator guarantees the feasibility of the desired payload pose. The strategy also enables convenient motion planning. The payload can either follow a pre-planned trajectory autonomously, or fly by human-in-the-loop control. 

Furthermore, We have developed a testbed consisting of four quadrotor robots and a payload. Flight tests have been successfully conducted in an indoor motion capture studio as well as outdoor with GPS
information.


<figure>
 <img src="/img/posts/2020-12-19-multilift/scheme.png" style="width:59%" />
 <figcaption>
        Hierarchical Load-leading conrol strategy.
 </figcaption>
</figure>


<figure>
    <img src="/img/posts/2020-12-19-multilift/37deg_disturbance_trim.gif" style="width:41%" />
    <img src="/img/posts/2020-12-19-multilift/fly_payload_trim_480.gif" style="width:55%" />
    <figcaption>
        Left: The system can reject impulse response; Right: The system can receive online command from a human pilot, instead of tracking a pre-planned trajectory thanks to the payload as the team leader.
    </figcaption>
</figure>


<figure>
 <img src="/img/posts/2020-12-19-multilift/outdoor_short.gif" style="width:70%" />
 <figcaption>
        Outdoor lateral trajectory tracking test.
 </figcaption>
</figure>

## Slung Load Inertial Property Estimation
The second challenge hinges on the model accuracy needed in the load-leading strategy. This requires augmented perception capability of the payload. In scenarios such as search and rescue, payload properties may be unknown. However, accurate payload inertial properties, such as mass, center of
mass, and moments of inertia, is important for achieving good transportation performance.

The ``load-leading'' framework enables a strategy for estimating payload parameters so as to improve the model accuracy. I have developed an inertial properties estimation strategy for a multilift slung load without introducing any cable tension load cells, so as to reduce the total weight and system cost. The difficulty is how to design excitation strategy for the system to observe the unknown parameters. Here, additional challenge arises from the lack of cable tension sensor. I created an indirect method on the aerial robot side to estimate the cable force. Then, I designed a sequence of flight patterns that excite different inertial properties to be observable. 

The estimation strategy has been validated indoor. Incorporating the estimated payload parameters into the loop significantly improves the tracking performance for the aerial robots. This study provides motivation and guidance on experiment design for system identification for complex system.

<figure>
    <img src="/img/posts/2020-12-19-multilift/figure_8.png" style="width:39%" />
    <img src="/img/posts/2020-12-19-multilift/tracking_error.png" style="width:55%" />
    <figcaption>
        Left: Controller compensation test. We flew the figure-8 pattern to excite the payload motion, and compared the case with or without controller compensation (with estimated parameters involved); Right: Rotor tracking error. Uncompensated case shows a significantly greater tracking error.
    </figcaption>
</figure>


## Trajectory Planning and Control Based on Load Distribution
The third challenge is the power allocation of the individual robots for sustainable manipulation tasks. This limits the global transportation performance: if one of the robots runs out of energy, the transportation will breakdown due to highly coupled mechanism. In the case of a homogeneous fleet of robots carrying a payload, it is intuitively appealing to operate the robots at near-equal load, leaving little room for unequal load distribution and thus maximizing the energy efficiency.

The ``load-leading'' framework also leads to convenient cooperative trajectory planning, which reduces to a simpler planning problem for the payload. I have developed a trajectory planning approach that simultaneously plans the slung load trajectory and cable forces while satisfying path and force
constraints and minimizing the variance in cable tension. The load distribution based planning problem can thus be formulated as an optimal control problem.

The proposed approach has been validated both in simulation and indoor flight test. The robots ended up with near-equal energy consumption and less total power. The approach developed can be extended to other general multi-robot system to lower the power consumption and extend the flight range and endurance. Therefore, it has the potential for saving considerable costs in real cooperative mission.

<figure>
 <img src="/img/posts/2020-12-19-multilift/load_distribution.png" style="width:59%"/>
 <figcaption>
        Comparison between with/without planning based on load distribution. Planning based on load distribution clearly reduced the cable tension variance.
 </figcaption>
</figure>



## Related Papers


### Citation
```
@article{geng2020cooperative,
  title={Cooperative transport of a slung load using load-leading control},
  author={Geng, Junyi and Langelaan, Jack W},
  journal={Journal of Guidance, Control, and Dynamics},
  volume={43},
  number={7},
  pages={1313--1331},
  year={2020},
  publisher={American Institute of Aeronautics and Astronautics}
}

@article{geng2021estimation,
  title={Estimation of Inertial Properties for a Multilift Slung Load},
  author={Geng, Junyi and Langelaan, Jack W},
  journal={Journal of Guidance, Control, and Dynamics},
  volume={44},
  number={2},
  pages={220--237},
  year={2021},
  publisher={American Institute of Aeronautics and Astronautics}
}

@article{geng2022load,
  title={Load-Distribution-Based Trajectory Planning and Control for a Multilift System},
  author={Geng, Junyi and Singla, Puneet and Langelaan, Jack W},
  journal={Journal of Aerospace Information Systems},
  volume={19},
  number={5},
  pages={366--381},
  year={2022},
  publisher={American Institute of Aeronautics and Astronautics}
}

```
