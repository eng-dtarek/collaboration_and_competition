# Project 3: Collaboration and Competition

## Introduction

For this project, you will work with the [Tennis](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#tennis) environment.

In this environment, two agents control rackets to bounce a ball over a net. If an agent hits the ball over the net, it receives a reward of +0.1. If an agent lets a ball hit the ground or hits the ball out of bounds, it receives a reward of -0.01. Thus, the goal of each agent is to keep the ball in play.

The observation space consists of 8 variables corresponding to the position and velocity of the ball and racket. Each agent receives its own, local observation. Two continuous actions are available, corresponding to movement toward (or away from) the net, and jumping.

The task is episodic, and in order to solve the environment, your agents must get an average score of +0.5 (over 100 consecutive episodes, after taking the maximum over both agents). Specifically,

* After each episode, we add up the rewards that each agent received (without discounting), to get a score for each agent. This yields 2 (potentially different) scores. We then take the maximum of these 2 scores.

* This yields a single score for each episode.

The environment is considered solved, when the average (over 100 episodes) of those scores is at least +0.5.

## Approach and solution

The notebook Tennis.ipynb contains the code to set up the environment and the outer episode iteration to solve the reinforcement problem. My solution uses A multi agent variant of DDPG called Multi Agent Deep Deterministic Policy Gradient (MADDPG) is described in this [paper](https://arxiv.org/abs/1706.02275)

## Dependencies

To set up your python environment to run the code in this repository, follow the instructions below.

1. Create (and activate) a new environment with Python 3.6.

    * Linux or Mac:

    ```
    conda create --name tennis python=3.6
    source activate tennis
    ```

    * Windows:
    ```
    conda create --name tennis python=3.6 
    activate tennis

2. Clone the repository (if you haven't already!), and navigate to the python/ folder. Then, install several dependencies.

```
git@github.com:eng-dtarek/collaboration_and_competition.git
cd collaboration_and_competition/python
pip install .
```

3. Create an [IPython kernel](http://ipython.readthedocs.io/en/stable/install/kernel_install.html) for the continuous_control environment.

```
python -m ipykernel install --user --name tennis --display-name "tennis"
```

4. Before running code in a notebook, change the kernel to match the tennis environment by using the drop-down Kernel menu.


## Getting Started

1. Download the environment from one of the links below. You need only select the environment that matches your operating system:
    
    * Linux: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Linux.zip)
    * Mac OSX: [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis.app.zip)
    * Windows (32-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86.zip)
    * Windows (64-bit): [click here](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P3/Tennis/Tennis_Windows_x86_64.zip)

2. Place the file in the repository, in the repository, and unzip (or decompress) the file.

3. Follow the instructions in tennis.ipynb to get started with training your own agent!
