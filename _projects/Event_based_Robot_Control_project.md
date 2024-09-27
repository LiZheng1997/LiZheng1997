---
layout: page
title:  Training Neural Networks for Event-Based End-to-End Robot Control 
description: End-to-end robot controllers using DQN, Braitenberg Vehicle, SNN, R-STDP
img: assets/img/pioneer-robot.png
importance: 3
category: research
---

I reproduced this project with a Pioneer P3-DX mobile robot in the V-REP simulator on 20231028.
There are four kinds of controllers, named **Braitenberg**, **DQN**, **DQN+SNN**, **R-STDP**.

Check codes on [Github](https://github.com/Bluet-NeuroRobotics/Training-Neural-Networks-for-Event-Based-End-to-End-Robot-Control)

The robot is attached with a DVS camera like the picture below:
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/pioneer-robot-dvs.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


A video demo link is attched below:

<div class="video-container iframe-container">
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=112687409268319&bvid=BV1X33yeYEnF&cid=500001597648077&p=1&muted=true" width="80%" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>
</div>

# Host Machine Environment
I created a Ubuntu16.04, virtual host machine using EXSI-8.0, 4Cores 8GB Memroy 25GB hard disk. 

## Dependencies
1. ROS-kinetic
2. NEST2.10
3. V-REP 3.6
4. Python2


# Running the v-rep simulator
```
$ cd /V-REP_PRO_V3_6_2_Ubuntu16_04
$ ./vrep.sh
```

and the screenshot is attached below:
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/robot-lane-keeping.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

# Star the Controller

## Braitenberg
```
$ python Controller/Braitenberg/controller.py 
```
After you start the controller, it will show like the picture below:
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/pioneer-robot.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

# Framework

## Simulated Environment
The experiment is based on a lane-following scenario, depicted in the picture below.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/env.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


## Input Event data
The input data pre-processing is depicted like the picture below:
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/input-dvs-frames.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
the raw 128x128 DVS frames is devided into small 4x4 regions and counting every event over consecutive frames regardless of the polarity. Then, the image is cropped at the top and bottom resulting in a 32 × 16 image. Fianlly, the input image will be transformed into a binary values with only [0,1].

## DQN

### Defined Rewards of MDP per time-step
The reward is defined as a Gaussian distributed function of the lane-center distance.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/rewards-definition.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Communication between components of the DQN controller
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/commnuication-DQN-controller.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


## DQN+SNN
The SNN is trained approximating the policy given by the Q-network of the DQN algorithm.

### The Algorithm of Converting ANNs to SNNs
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Converting-ann-snn.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
Model-based normalization algorithm for converting ANNs into SNNs according to Diehl et al(Fast-classifying, high-accuracy spiking deep networks through weight and threshold balancing.). 

### Communication between components of the DQN-SNN controller
The communication diagram is attached below:
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/comm-dqn-snn.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


## Braitenberg
Communication and components of the Braitenberg vehicle controller: 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/communication-braitenberg-controller.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

The network architecture of the Braitenberg vehicle using DVS frames as input.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/network-braitenberg-vehicle.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


## R-STDP
The network architecture is different from the previous Braitenberg vehicle, it merely use one SNN to control left and right motor outputs.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/network-rstdp.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


# Comparision of different controllers on the outer lane
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/comparision-controllers.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


It is obvious from the result that R-STDP is the most robust and stable one from the distance away from the lane center.


# References

***Papers:***


[1] Towards a framework for end-to-end control of a simulated vehicle with spiking neural networks
[2] Fast-classifying, high-accuracy spiking deep networks through weight and threshold balancing

***Links:***


[](https://blog.csdn.net/qq_38587510/article/details/104369066)

[](https://www.guyuehome.com/1966)

[](https://www.coppeliarobotics.com/helpFiles/en/ros1Tutorial.htm)

[](https://manual.coppeliarobotics.com/en/rosInterf.htm)

***V-REP previous versions:***

[](https://www.coppeliarobotics.com/previousVersions)


***NEST2.10:***

[](https://nest-simulator.readthedocs.io/en/v2.20.0/installation/oldvers_install.html)