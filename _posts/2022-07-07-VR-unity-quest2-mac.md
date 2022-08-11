---
layout: post
title:  Developing for the Oculus (Meta) Quest 2 with Unity on Apple Silicon Macs (M1, M2)
date:   2022-07-07
description: 
tags: Virtual-Reality Unity Oculus Quest 2 Mac M1 M2 Apple-Silicon
categories: software-development
---
Most online resources claim that it is not possible to develop for the Meta Quest 2 in Unity with Apple Silicon Macs (such as my 2020 Macbook Pro with a M1 ARM chip). This not true. It may not be an entirely optimal process, but it is very much possible. And with acceptable speed at that (the first build will take a lot longer though):

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/Unity-Quest2-ARM/compilation_time.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>

There are basically two ways to build software for the Quest 2 with Unity:

1. Let it run on your computer with the headset being connected the entire time ("PC-VR")
2. Build the entire project for the Android platform and copy the resulting app to the headset ("mobile VR")


The former is currently not possible, since Meta does not support Macs at all with their Oculus Link software. And it would be the prefered way for development, since you jump very quickly into the VR scence with Unity's play mode.

But, you can do the latter. And with the good performance for build times on Apple Silicon Macs. To do so, you need to switch to the Android platform in Unity's Build Settings and select the appropriate XR Plug-in in the Project Settings (both OpenXR and Oculus should work). Afterwards build and run the project. Also make sure that the Oculus Quest 2 is selected as the Run Device in the Build Settings:

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0">
         {% include figure.html path="assets/img/Unity-Quest2-ARM/build-settings.jpg" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>

This is a viable way of building more simple projects and testing things on the go. A simplistic demo scene builds on my baseline MacBook Pro (M1, 2020) in about 12 seconds (with Unity 2021.3.5f1 SILICON LTS). I image that build times would be even lower with the high-performance versions of Apple Silicon (M2, M1 Pro/Max/Ultra).
