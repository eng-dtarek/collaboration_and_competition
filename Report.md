## Learning Algorithm:

In order to build an agent that is able to solve the problem, I used Multi Agent Deep Deterministic Policy Gradient approach which is described in this [paper](https://arxiv.org/abs/1706.02275)


### Components:

* Actor Network: consists of three fully connected layers along with relu function and tanh function.

* Critic Network: consists of three fully connected layers along with relu function.

* Adam Optimizer: that optimizes the actions of the agent.

* Experience Replay: with a buffer to store the experience and sampling from it.

* Ornstein-Uhlenbeck: add a certain amount of noise to the action values at each timestep.

### Hyperparameters: 

I have tried different values of some parameters until solving the environment in 1027 episodes using the follwing parameters values:

* BUFFER_SIZE = int(1e5)  
* BATCH_SIZE = 250        
* GAMMA = 0.99           
* TAU = 1e-3              
* LR_ACTOR = 1e-4         
* LR_CRITIC = 1e-3       
* WEIGHT_DECAY = 0 
* MU = 0.
* THETA = 0.15
* SIGMA = 0.2       

## Plot of Rewards:

![plot of rewards](/download.png)

## Ideas for Future Work:

There are many ideas that can improve the agent's performance dramatically like the following:

* Tuning the hyperparameters.
* Changing the neural networks architectures.
* Using prioritized experience Replay may improve the agent.
* Using Proximal Policy Optimization.
