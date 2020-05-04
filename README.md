# Udacity's Deep RL Nanodegree - Project 1: Navigation

[//]: # (Image References)

[image1]: https://user-images.githubusercontent.com/11748427/80967527-cc864e00-8e16-11ea-8467-df71ffbbeb5b.gif "Trained Agent"


## Introduction

This Repository contains my solution for the first project of the Deep Reinforcement Learning from Udacity. In this exercise an RL-agent is dropped in a large square environment where it must collect yellow bananas scattered around the world while avoiding the blue ones. The environment was made with Unity's ML-Agents framework. 

![Trained Agent][image1]


## Environment Definition

##### Rewards

- Each **yellow** banana collected provides a reward of **+1**.
- Each **blue** banana collected provides a reward of **-1**.
- No rewards are provided in a per-time-step basis.

##### State Space

The state space has 37 dimensions and consists of the agent's velocity, as well as ray-based perception of objects in front of the agent.

##### Action Space

The agent has four discrete actions available at it's disposal:
- **`0`** - move forward.
- **`1`** - move backward.
- **`2`** - turn left.
- **`3`** - turn right.

#### Task Goal

The agent must learn to select the appropriate action to maximize the amount of yellow bananas it collects in each episode of the task. In order to consider the environment solved, the agent must get an average score of +13 over 100 consecutive episodes.



## Getting Started

1. Download the environment from one of the links below.  You need only select the environment that matches your operating system:
    - Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux.zip)
    - Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana.app.zip)
    - Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86.zip)
    - Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Windows_x86_64.zip)
    
    (_For Windows users_) Check out [this link](https://support.microsoft.com/en-us/help/827218/how-to-determine-whether-a-computer-is-running-a-32-bit-version-or-64) if you need help with determining if your computer is running a 32-bit version or 64-bit version of the Windows operating system.

    (_For AWS_) If you'd like to train the agent on AWS (and have not [enabled a virtual screen](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Training-on-Amazon-Web-Service.md)), then please use [this link](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P1/Banana/Banana_Linux_NoVis.zip) to obtain the environment.

2. Place the file in the DRLND GitHub repository, in the `p1_navigation/` folder, and unzip (or decompress) the file. 

### Instructions

Follow the instructions in `Navigation.ipynb` to get started with training your own agent!  
