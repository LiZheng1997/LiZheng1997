---
layout: page
title: MiRo Bio-inspired Visual-System
description: Apply Computer Vision algorihtms & a bio-inspired theory on a biomimetic robot named MiRo.  
img: assets/img/MiRo-tracking.png
importance: 1
category: work
related_publications: 
---

This is my first version of an bio-inspired visual system which is based on OpenCV APIs and ANN, and the final aim of this project is intercepting a moving target. I pre-defined three targets, named pedestrians, MiRo robots and MiRo toy balls. In total, there are three scenarios for different deploying situations, like on-board; off-board and in a simulator (Gazebo). Some codes are inspired from code samples in the MDK-2019 version. Thanks for their brilliant work on building MiRo robots. I am also one of the big fan loving biomimetic robots. Link: http://labs.consequentialrobotics.com/miro-e/docs/index.php?page=Introduction


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/MiRo-tracking.png" title="miro-tracking-miro" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/MiRo-tracking-pedestrian.png" title="miro-tracking-people" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Left: A MiRo robot is tracking and following another MiRo robot. Right: A MiRo robot wants to intercept and catch a pedestrian.
</div>

**Demo1**(intercepting_ball):

https://github.com/user-attachments/assets/e40b4b14-01dd-4721-882a-032114d49827

**Demo2**(intercepting_miro_without_safety_control)

https://github.com/user-attachments/assets/b8287cf4-107c-41ef-ab00-4e6006fa9c54

**Demo3**(intercepting_miro_real_world)

https://github.com/user-attachments/assets/22280969-d234-42e9-8bf1-78218282ab04

**Demo4**(intercepting_pedestrian_real_world)

https://github.com/user-attachments/assets/27777dc7-73cb-4ded-9c11-af9d9ba88df4



