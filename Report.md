# Udacity's Deep RL Nanodegree - Project 1: Navigation

## Technical Report



In this report we will talk in detail about the algorithm and techniques used to solved this Reinforcement Learning scenario





(Gif of the solved  episode.)



### Problem Statement



#### Environment

In this scenario the RL-agent is dropped in a large square environment where it must collect yellow bananas scattered around the world while avoiding the blue ones. The environment was made with Unity's ML-Agents framework. It roughly looks as following looking from the top:



![rect903](/home/said/rect903.png)



This environment provides the following rewards:

- Each **yellow** banana collected provides a reward of **+1**.
- Each **blue** banana collected provides a reward of **-1**.
- No rewards are provided in a per-time-step basis.



#### Actions

The agent has four discrete actions available at it's disposal:
- **`0`** - move forward.
- **`1`** - move backward.
- **`2`** - turn left.
- **`3`** - turn right.



#### State Space

The state space has 37 dimensions and consists of the agent's velocity, as well as ray-based perception of objects in front of the agent.



### Deep-Q Learning



This exercise was solved replicating the techniques of the Deep-Q learning from the famous Google Mind [paper about it](https://storage.googleapis.com/deepmind-media/dqn/DQNNaturePaper.pdf). 

> Mnih, V., Kavukcuoglu, K., Silver, D. *et al.* Human-level control through deep reinforcement learning.                    *Nature* **518,** 529–533 (2015). 



Which Implements the following algorithm



![image-20200506205940385](/home/said/.config/Typora/typora-user-images/image-20200506205940385.png)



This works particularly well for the current environment given that both its **State Space** and **Action Space** are discrete.



#### Neural Network.

To approximate the **Action-Value Function** we can use a Deep Neural Network just as suggested in the paper. However, given that the input is not an image, there is no need to use a Convolutional Architecture. Instead, a network with two fully connected  RELU layers ending with a softmax function is more than enough.

( Make a Cute diagrama with the Neural network.)



#### Experience Replay

All steps' **`(State, Action, Reward, Next State)`**   tuples are saved in to a queue  in memory. Every **`4`** time steps, a mini-batch of **`64`** tuples are selected to update the Neural Network weights.

#### Target Network

Two Neural Networks (with the exact same architecture) are used simultaneously for the learning process. The main network is used to select the best action for a given state.

The second network is used to generate the target labels against which the error to back-propagate the weights are calculated. 

The Loss functions if therefore defined as:



![image843](/home/said/image843.png)



#### Selected Hyper-parameters

The code uses the following Hyper-parameters:

- **`Number of Hidden Layers`**  =  2
- **`Neurons per layers`**  =  64 
- **`Gamma`**  =  0.99
- **`TAU`**  =  1e-3
- **`Learning Rate`**  =  5e-4
- **`Steps per update`**  =  4
- **`Batch Size`**  =  64



### Results

When simulated, we receive the following plot of score over episodes.



![image-20200506222642665](/home/said/.config/Typora/typora-user-images/image-20200506222642665.png)



As it can be seen, the algorithm achieves an average score of 13 in about 800 episodes, effectively solving the Task.



### Future work

There are several ways to improve this project. The implemented algorithm is 5 years old now and there are several know improvements. for example, the mini-batch are currently chosen completely at random, instead of using **Importance Sampling.**





Icons made by <a href="https://www.flaticon.com/authors/freepik" title="Freepik">Freepik</a> from <a href="https://www.flaticon.com/" title="Flaticon"> www.flaticon.com</a>