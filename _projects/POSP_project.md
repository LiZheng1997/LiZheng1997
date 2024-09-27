---
layout: page
title: POSP
description: a project for picking out a single package
img: assets/img/single-package.jpg
importance: 1
category: work
---

# Background

This is a [project](https://github.com/LiZheng1997/POSP) for picking out a single package when there are parallel packages. **POSP** means Pick Out Single Package, this project aims at solving the problem of parallel packages transporting on a conveyor belt. The Normal situation is that two packages are close to each other, but sometimes a difficult situations is that one package will be too close to the other one or two packages.

Like the video shows below, you can click the picture to watch it:

[![Parallel packages](https://res.cloudinary.com/marcomontalbano/image/upload/v1722966674/video_to_markdown/images/youtube--vM1hwYmYbvQ-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/vM1hwYmYbvQ "Parallel packages")


Some screenshots about the detection of parallel packages are like bellow: 

<div class="col-sm mt-3 mt-md-0">
    {% include figure.html path="assets/img/single-package.jpg" title="parallel packages color" class="img-fluid rounded z-depth-1" %}
</div>


The following pictures are raw RGB images and aligned depth image using heatmaps to show different depth values.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/0001_Color.png" title="parallel packages color" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/0001_Depth.png" title="parallel packages depth" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/0002_Color.png" title="kinematic model" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/0002_Depth.png" title="kinematic model" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/0003_Color.png" title="kinematic model" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/0003_Depth.png" title="kinematic model" class="img-fluid rounded z-depth-1" %}
    </div>
</div>


# Framework

## Hardware

## Software