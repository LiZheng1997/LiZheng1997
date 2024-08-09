---
layout: page
title: Follow Me
description: a project which implements a visual tracking and control system 
img: assets/img/gimbal-camera.png
importance: 1
category: work
giscus_comments: true
---

This "**Follow Me**" project implements a visual tracking & control system with using a PixKit-1.0 Chassis.

I designed and implemented a pure visual tracking system for a customer. The customer expected that this tracking system finally could track three objects(Cars, Pedestrians and UAVs) and follow them once a goal, means SOT(Single Object Tracking). Followings are two video demos.


<div class="video-container iframe-container">
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=689345413&bvid=BV1Bm4y1w7BZ&cid=866920512&p=1&muted=true" scrolling="yes" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>
</div>

<div class="video-container iframe-container">
<iframe src="//player.bilibili.com/player.html?isOutside=true&aid=561767384&bvid=BV1xe4y1i7wi&cid=866931240&p=1&muted=true" width="100%" scrolling="yes" border="0" frameborder="no" framespacing="0" allowfullscreen="true"></iframe>
</div>


# Requirements and Motivation

## Motivation
According to the definition of "**Follow Me**" functionality, we want our robots(Pixkit-1.0 with cameras) to follow a goal(The user/customer) freely, or we want to add more trailers behind a robot to follow a person who want to use trailers to carry on stuff with hands free. 

## Hardware Requirements
1. Pixkit-1.0 Chassis
2. Gimbal Camera(3-Axis Rotation: Roll Pitch Yaw)
3. IPC with a GPU card(RTX2070 or better)

### Gimbal Camera

The gimbal camear used in this project looks like pictures bellow.
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/20220114-e0917cd4.png" title="Flow Diagram" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/gimbal-camera.png" title="Flow Diagram" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Software Requirements
1. Pixkit-1.0 ROS Driver
2. Gimbal Camera control ROS Driver
3. Docker

# A flow diagram

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/SOT-tracking-diagram.png" title="Flow Diagram" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

## Detection, Tracking and Visual Control

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/20220116-76d60e91.png" title="Detection" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/20220116-3b5f0f20.png" title="Tracking" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/20220116-67901f3c.png" title="Visual Control" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
        Left: YoloX Detection result
        Middle: Siamfc++ Tracking result
        Right: Visual Control
</div>

<div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/realtime-effect.png" title="Visual Control" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
        Realtime tracking-by-detection and following a pedstrian.
</div>

# Future Work
In order to empower Pixkit-1.0 with a visual-based tracking and following funcionality, and mainly focus on tracking a pedestrian freely, we can use aforementioned pure visual tracking system which is the first version. In the next stage, I will develop a second version to cover more categories if needed and optimize selected sensors, I plan to change the gimbal camera to a normal RGB camera(FILR/leopard/Sensing) with a low cost. 