---
layout: page
title:  Event-Based End-to-End Robot Control 
description: a project with a background image
img: assets/img/pioneer-robot.png
importance: 3
category: research
---

# Training Neural Networks for Event-Based End-to-End Robot Control

I reproduced this project with a Poineer mobile robot in the V-REP simulator on 20231028.
There are four kinds of controllers, named Braitenberg, DQN, SNN, R-STDP.

A video demo link is attched bellow:

<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=112687409268319&bvid=BV1X33yeYEnF&cid=500001597648077&p=1&muted=true" scrolling="no" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>


# Host Machine Env
Ubuntu16.04, virtual machine using EXSI-8.0, 4Cores 8GB Memroy 25GB hard disk. 

## Dependencies
1. ROS-kinetic
2. NEST2.10
3. V-REP 3.6
4. Python2


# Runing the v-rep simulator
```
$ cd /V-REP_PRO_V3_6_2_Ubuntu16_04
$ ./vrep.sh
```

and the screenshot is attached bellow:
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
After you start the controller, it will show like the picture bellow:
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/pioneer-robot.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

# Framework

## DQN


## Deep Q-Leaning

## DQN+SNN

## R-STDP

## Braitenberg



# References
Links:
https://blog.csdn.net/qq_38587510/article/details/104369066
https://www.guyuehome.com/1966
https://www.coppeliarobotics.com/helpFiles/en/ros1Tutorial.htm
https://manual.coppeliarobotics.com/en/rosInterf.htm

V-REP previous versions:
https://www.coppeliarobotics.com/previousVersions

NEST2.10:
https://nest-simulator.readthedocs.io/en/v2.20.0/installation/oldvers_install.html