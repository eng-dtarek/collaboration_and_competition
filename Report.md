## Learning Algorithm:

In order to build these agents that are able to solve the problem, I used Multi Agent Deep Deterministic Policy Gradient approach that provides interacting agents with the ability to collaboratively learn and adapt to the behaviour of other agents. See this [paper](https://arxiv.org/abs/1706.02275).
Experience replay is shared between the agents to learn from past experience. In this problem  we have two continuous actions, corresponding to movement toward (or away from) the net, and jumping. If we base our exploration mechanism on random uniform sampling, these would have a mean of zero, in turn cancelling each other out. This can cause the system to oscillate without making much progress. So the Ornstein-Uhlenbeck process is used to add a certain amount of noise to the action values at each timestep. This noise is correlated to previous noise, and therefore tends to stay in the same direction for longer durations without canceling itself out.
The model architecture of critic and actors are taken from my solution of the previous project [Continuous_Control](https://github.com/eng-dtarek/Continuous_Control) except for batch normalization. 

### Components:

* Actor Network: consists of three fully connected layers along with relu function and tanh function.

* Critic Network: consists of three fully connected layers along with relu function.

* Adam Optimizer: that optimizes the actions of the agent.

* Experience Replay: with a buffer to store the experience and sampling from it.

* Ornstein-Uhlenbeck: add a certain amount of noise to the action values at each timestep.

### Hyperparameters: 

I began with the same Hyperparameters from my solution on the previous project [Continuous_Control](https://github.com/eng-dtarek/Continuous_Control). that provides good results. Then I tried different values of some parameters like BATCH_SIZE, TAU, LR_ACTOR, LR_CRITIC, and SIGMA until solving the environment in 1027 episodes using the follwing parameters values:

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
* Adding Batch Normalization.
* Changing the neural networks architectures.
* Using prioritized experience Replay may improve the agent.
* Using Proximal Policy Optimization.
