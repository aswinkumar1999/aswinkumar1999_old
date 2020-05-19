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

We saw about the installation of mujoco and mujoco-py in the last blog , keeping in mind the same install location , let us run the Simulator with the inbuilt Humanoid Model.

```bash
# cd to the mujoco directory
$ cd ~/.mujoco/mujoco200/bin
# Simulate the Humanoid Model example
$ ./simulate ../model/humanoid.xml
```

##### For Help - Toggle `F1` Key

Now we have the simulator window opened up , Let us now see some basic actions that we can perform.

## Basics

#### Change Theme , Size and UI Layout

In the Left Side of the windows , We have the UI tab , where we have a lot of options to control the looks of the simulations window such as `Spacing`, `Control` , `Font` Here is an Example to Change the Theme of the Window.

<p align="center">
  <img width="960" height="540" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/theme.gif" />
</p>


#### Pan , Rotate and Zoom

These are the Following mouse functions :

- Left Click and move your mouse to Rotate.
- Middle Click and Moving your mouse Zooms in and out   
- Right Click and mouse to PAN

<p align="center">
  <img width="960" height="540" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/pzr.gif" />
</p>


#### Joint and Control

We can define sensors and actuators in our models, we will see how to do that in the upcoming blog , but to control and see the output values , you can look at the Right UI which has the Joint and Control Tab.


<p align="center">
  <img width="960" height="540" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/joincont.gif" />
</p>


#### Force and Torue 

You can Apply force and Torque to the bodies in the model , to do so , you will have to :

- Select the Body where you want to apply force or Torque `Double Click` , the body gets highlighted
- Press `Crtl + Left Click` and Move your mouse to Apply Torque
- PRess `Crtl + Right Click` and Move your mouse to Apply Force to the Body

<p align="center">
  <img width="960" height="540" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/fortor.gif" />
</p>

#### Labelling 

We can Label bodies and geometry in our `XML` file so that we can keep track of them especially for complex models. 

To view labels , you can go under the Rendering Tab in the Left UI and scroll through the Label options to select whichever you want. 

**Labelling - Body **

<p align="center">
  <img width="960" height="540" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/lab_body.gif" />
</p>

**Labelling - Geometry **

<p align="center">
  <img width="960" height="540" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/lab_geom.gif" />
</p>

#### Frame 

We can take a Look at the Frame Axis of Bodies , Geometries, Sites etc... 

It can be found next to the Label Options. 

**Frame - Worldbody**

<p align="center">
  <img width="960" height="540" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/frame_world.gif" />
</p>

**Frame - Body**

<p align="center">
  <img width="960" height="540" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/frame_body.gif" />
</p>

**Frame - Geometry**

<p align="center">
  <img width="960" height="540" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/frame_geom.gif" />
</p>

#### Model Elements 

Under the Rendering Tab , We also have other options to play with , Some of are display of Center of Mass , Display of Contact points , Contact Forces etc... 

You can toggle them to turn the features on and off. 

**Model - Display Center of mass**

<p align="center">
  <img width="960" height="540" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/model_COM.gif" />
</p>

**Model - Contact Force**

<p align="center">
  <img width="960" height="540" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/model_com_force.gif" />
</p>

**Model - Display Actuators**


<p align="center">
  <img width="960" height="540" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/model_actuator.gif" />
</p>


#### OpenGL Effects 

This has nothing to do with the model and this provides some cool OpenGL Features , These Features are also placed under Rendering Tab.

**OpenGL - Wireframe Mode**


<p align="center">
  <img width="960" height="540" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/opengl_wireframe.gif" />
</p>

**OpenGL - Reflections and Shadows**


<p align="center">
  <img width="960" height="540" src="https://github.com/aswinkumar1999/aswinkumar1999.github.io/raw/master/assets/img/posts/mujoco-part-1/opengl_reflshad.gif" />
</p>
