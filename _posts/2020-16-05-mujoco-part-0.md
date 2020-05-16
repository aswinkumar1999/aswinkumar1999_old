---
layout: post
title: Getting Started with MuJoCo
author: Aswinkumar
date: '2020-05-15 10:19:51 +0530'
category:
        - Robotics
        - MuJoCo
        - MuJoCo-Py
        - OpenAI
summary: MuJoCo for Noobs
thumbnail: mujoco-part-0/thumb.png
---

Hi ! Welcome to my Blog on MuJoCo. The Aim of this blog is to get people on-board MuJoCo in the least time possible. I am a Sophomore at a University, my Programming experience has been developed by looking at multiple example and reading code, but when it came to MuJoCo, the Documentation was very thorough yet i felt like i was lacking the basic skills to understand a lot of them initially and was very intimitated when i first came across it. So I set myself a goal to write MuJoCo blogs which would help people who love explanations through examples. **But do remember , the blog is supposed to set a starting point and break the ice for people who do not have any major first hand experiences in robotic modelling , i refer the XML Reference all the time and once you get familiar and comfortable with the basic , do use the documentation to make sure you are exploiting all the features of MuJoCo.**

In this post , Let us cover the Following : 

- What is MuJoCo ? 
- How a Model is defined in MuJoCo ? 
- Intro to mujoco-py 
- mujoco-py Installtion 
- Hello World in MuJoCo !

# What is MuJoCo ? 

MuJoCo stands for **Mu**lti-**Jo**int dynamics with **Co**ntact.

MuJoCo is a physics engine aiming to facilitate research and development in robotics, biomechanics, graphics and animation, and other areas where fast and accurate simulation is needed. It offers a unique combination of speed, accuracy and modeling power, yet it is not merely a better simulator. 

[Checkout this video from MuJoCo](http://www.mujoco.org/image/home/mujocodemo.mp4)

### Licenses 

You can head over to [MuJoCo License page](https://www.roboti.us/license.html) and obtain a license to use their software. If you are a student , then you get 1 year if MuJoCo for free.


# How is a Model defined in MuJoCo ? 

The user specifies models in the native MJCF format - which is an XML file format designed to be as human readable and editable as possible. URDF model files can also be loaded. 

Unified Robot Description Format (URDF) is a popular XML file format in which many robots have been modeled.

In this blog , we will discuss more about MJCF and not discuss about URDF format.

# mujoco-py 

#### [Documentation for mujoco-py](https://openai.github.io/mujoco-py/build/html/index.html) 
#### [GitHub](https://github.com/openai/mujoco-py)

`mujoco-py` is a library which allows using MuJoCo from Python3. 

This is particularly very useful when we design Control Systems or AI agents for robots. mujoco-py was developed by [OpenAI](https://openai.com).

You can install `mujoco-py` by using pip

```
$ pip3 install -U 'mujoco-py<2.1,>=2.0'
```

### Install from source 

Clone this repository and move into the directory.
```
git clone git@github.com:openai/mujoco-py.git
cd mujoco-py
```
Make sure your setup tools are up to date
```
python -m pip install --upgrade setuptools
```
Install both regular and dev dependencies for mujoco-py
```
pip install -r requirements.txt
pip install -r requirements.dev.txt
```
Now install mujoco-py
```
python setup.py install
```

#### Post-Installation Steps 

- Download the MuJoCo version 2.0 binaries for Linux or OSX.

- Unzip the downloaded mujoco200 directory into `~/.mujoco/mujoco200`, and place your license key (the `mjkey.txt` file from your email) at `~/.mujoco/mjkey.txt`.


If everything completes successfully you should be able to run the examples

```
python examples\body_interaction.py
```

## Hello World in MuJoCo 

Great , with all the above steps performed, let's go on build our first model. 

Now , Let's verify we are in the correct directory. 

```
$ cd ~/.mujoco/mujoco200/  
$ pwd 
/Users/~user~/.mujoco/mujoco200
```

Let us now create a new folder where we will save our models and python files. 

```
$ mkdir my_files
```

Create a new model file in this folder and add a few lines to it.

```
$ touch my_files/hello_mujoco.xml
```

Add the following lines to it and save it. 

```
<mujoco>
   <worldbody>
      <light diffuse=".5 .5 .5" pos="0 0 3" dir="0 0 -1"/>    
      <geom type="plane" size="1 1 0.1" rgba=".9 0 0 1"/>
      <body pos="0 0 1">
         <joint type="free"/>
         <geom type="box" size=".1 .2 .3" rgba="0 .9 0 1"/>
      </body>
   </worldbody>
</mujoco>
```

Let us now simulate this and then go back to seeing them in detail line-by-line. 

To simulate this do the following : 

```
$ cd /bin # Change to directory containing the binaries 
$ ./simnulate ../my_files/hello_mujoco.xml
```

Voila !! Now you have an OpenGL window pop-up with the animation of the falling cube. 

Now Let us see in brief about what the lines mean , for which we will extensively use the [documentation](http://www.mujoco.org/book/XMLreference.html) provided by MuJoCo 
