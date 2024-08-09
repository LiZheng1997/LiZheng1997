---
layout: page
title: T & R Visual Navigation
description: Teach & Repeat Visual Navigation using a Jaguar 4 wheels Robot
img: assets/img/jaguar-robot.jpg
importance: 2
category: research
---

# Background

During the short internship with Dr Li Sun from 2019.12-2020.01, and under the help of two PhD students from the Czech Technical University in Prague, I deployed the following Teach & Repeat algorithms on a Jaguar robot 4x4 wheels(differential base), with a ZED stereo camera mounted on it. All codes can accessed from their [github](https://github.com/Bluet-NeuroRobotics/stroll_bearnav/tree/core?tab=readme-ov-file)


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/jaguar-robot.jpg" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Navigation-process.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
        Left: The Jaguar robot's outlook
        Right: The Testing place is near a church 
</div>



The final video demo is attached bellow, you can click the picture to watch it.

[![Teach & Repeat visual navigation](https://res.cloudinary.com/marcomontalbano/image/upload/v1723098695/video_to_markdown/images/youtube--4-_VVGgxXEI-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=4-_VVGgxXEI "Teach & Repeat visual navigation")



# System

## Hardware
1. a ZED camera(1st 2nd mini generation are all nice)
2. a PS4 joystick (for the first teach round, not used in repeat round)
3. a Ackerman chassis or robots with differential base (control commands will be different)
4. a Jetson Xavier/Orin Developer Kit 32G/Laptop. (Computing Unit)
5. a ac8265 wifi card is necessary (if you use Jetson Dev kit)
6. a USB Hub
7. a USB to TTL serial port Line

## Software
1. PS4 ROS driver
2. Ackerman chassis ROS driver/Robot Velocity Control ROS driver
3. ZED camera ROS driver
4. ROS1-melodic


# Framework

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/t&p-framework.png" title="Framework" class="img-fluid rounded z-depth-1" %}
    </div>
</div>



# Relevant Links
[Day-to-night navigation using a single experience map](https://sites.google.com/view/kevinlisun/home/project-navigation?authuser=0)

[Visual Teach & Repeat 3](https://utiasasrl.github.io/vtr3/)


# References

[1] Krajník, T., Majer, F., Halodová, L. and Vintr, T., 2018, October. Navigation without localisation: reliable teach and repeat based on the convergence theorem. In 2018 IEEE/RSJ International Conference on Intelligent Robots and Systems (IROS) (pp. 1657-1664). IEEE.