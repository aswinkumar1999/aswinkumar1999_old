---
layout: post
title: MuJoCo simulator
author: Aswinkumar
date: '2020-05-18 10:19:51 +0530'
category:
        - Robotics
        - MuJoCo
        - MuJoCo-Py
        - OpenAI
summary: MuJoCo for Noobs - Part 2
thumbnail: mujoco-part-1/pzr.gif
---

Hi ! Welcome to my Blog on MuJoCo. The Aim of this blog is to get people on-board MuJoCo in the least time possible. I am a Sophomore at a University, my Programming experience has been developed by looking at multiple example and reading code, but when it came to MuJoCo, the Documentation was very thorough yet i felt like i was lacking the basic skills to understand a lot of them initially and was very intimitated when i first came across it. So I set myself a goal to write MuJoCo blogs which would help people who love explanations through examples. **But do remember , the blog is supposed to set a starting point and break the ice for people who do not have any major first hand experiences in robotic modelling , i refer the XML Reference all the time and once you get familiar and comfortable with the basic , do use the documentation to make sure you are exploiting all the features of MuJoCo.**

In this post , Let us cover the Following :

- Playing with the MuJoCo Simulator
- Hello mujoco-py

If you have not seen my Part 1 of the post , Do look at it for the basics.

# Playing with the MuJoCo Simulator

## Running the Simulator

We saw about the installation of mujoco and mujoco-py in the last blog , keeping in mind the same install location.

```bash
# cd to the mujoco directory
$ cd ~/.mujoco/mujoco200/bin
# Simulate the Humanoid Model example
$ ./simulate ../model/humanoid.xml
```

Now we have the simulator window opened up , Let us now see some basic actions that we can perform.

#### Change Theme , Size and UI Layout

In the Left Side , We have the UI tab , where we have a lot of options to control the looks of the simulations window such as `Spacing`, `Control` , `Font` Here is an Example to Change the Theme of the Window.

<p align="center">
  <img width="640" height="480" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/theme.gif" />
</p>


#### Pan , Rotate and Zoom

These are the Following mouse functions :

- Left Click and move your mouse to Rotate.
- Middle Click and Moving your mouse Zooms in and out   
- Right Click and mouse to PAN

<p align="center">
  <img width="640" height="480" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/pzr.gif" />
</p>


#### Joint and Control

We can defi
