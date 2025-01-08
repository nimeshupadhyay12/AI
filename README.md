# AI

## 1. What is reinforcement Learning

Reinforcement Learning: An Overview
- Reinforcement Learning (RL) is a branch of machine learning focused on making decisions to maximize cumulative rewards in a given situation. Unlike supervised learning, which relies on a training dataset with predefined answers, RL involves learning through experience. In RL, an agent learns to achieve a goal in an uncertain, potentially complex environment by performing actions and receiving feedback through rewards or penalties.

Key Concepts of Reinforcement Learning
- Agent: The learner or decision-maker.
- Environment: Everything the agent interacts with.
- State: A specific situation in which the agent finds itself.
- Action: All possible moves the agent can make.
- Reward: Feedback from the environment based on the action taken.
  
How Reinforcement Learning Works
- RL operates on the principle of learning optimal behavior through trial and error. The agent takes actions within the environment, receives rewards or penalties, and adjusts its behavior to maximize the cumulative reward. This learning process is characterized by the following elements:

- Policy: A strategy used by the agent to determine the next action based on the current state.
- Reward Function: A function that provides a scalar feedback signal based on the state and action.
- Value Function: A function that estimates the expected cumulative reward from a given state.
- Model of the Environment: A representation of the environment that helps in planning by predicting future states and rewards.
- Example: Navigating a Maze. 


Main points in Reinforcement learning – 
- Input: The input should be an initial state from which the model will start
- Output: There are many possible outputs as there are a variety of solutions to a particular problem
- Training: The training is based upon the input, The model will return a state and the user will decide to reward or punish the model based on its output.
The model keeps continues to learn.
The best solution is decided based on the maximum reward.


Advantages and Disadvantages of Reinforcement Learning
- Advantages:
1. Reinforcement learning can be used to solve very complex problems that cannot be solved by conventional techniques.

2. The model can correct the errors that occurred during the training process. 

3. In RL, training data is obtained via the direct interaction of the agent with the environment

4. Reinforcement learning can handle environments that are non-deterministic, meaning that the outcomes of actions are not always predictable. This is useful in real-world applications where the environment may change over time or is uncertain.

5. Reinforcement learning can be used to solve a wide range of problems, including those that involve decision making, control, and optimization.

6. Reinforcement learning is a flexible approach that can be combined with other machine learning techniques, such as deep learning, to improve performance.

- Disadvantages:
1. Reinforcement learning is not preferable to use for solving simple problems.

2. Reinforcement learning needs a lot of data and a lot of computation

3. Reinforcement learning is highly dependent on the quality of the reward function. If the reward function is poorly designed, the agent may not learn the desired behavior.

4. Reinforcement learning can be difficult to debug and interpret. It is not always clear why the agent is behaving in a certain way, which can make it difficult to diagnose and fix problems.

Conclusion
- Reinforcement learning is a powerful technique for decision-making and optimization in dynamic environments. Its applications range from robotics to personalized learning systems. However, the complexity of RL requires careful design of reward functions and significant computational resources. By understanding its principles and applications, one can leverage RL to solve intricate real-world problems.




## Bellman Equation 
- According to the Bellman Equation, long-term- reward in a given action is equal to the reward from the current action combined with the expected reward from the future actions taken at the following time. Let’s try to understand first.

What happens without Bellman Equation?

- Initially, we will give our agent some time to explore the environment and let it figure out a path to the goal. As soon as it reaches its goal, it will back trace its steps back to its starting position and mark values of all the states which eventually leads towards the goal as V = 1.

- The agent will face no problem until we change its starting position, as it will not be able to find a path towards the trophy state since the value of all the states is equal to 1. So, to solve this problem we should use Bellman Equation:

- V(s)=maxa(R(s,a)+ γV(s’))

- State(s): current state where the agent is in the environment
- Next State(s’): After taking action(a) at state(s) the agent reaches s’
- Value(V): Numeric representation of a state which helps the agent to find its path. V(s) here means the value of the state s.
- Reward(R): treat which the agent gets after performing an action(a).

R(s): reward for being in the state s
R(s,a): reward for being in the state and performing an action a
R(s,a,s’): reward for being in a state s, taking an action a and ending up in s’
e.g. Good reward can be +1, Bad reward can be -1, No reward can be 0.

- Action(a): set of possible actions that can be taken by the agent in the state(s). e.g. (LEFT, RIGHT, UP, DOWN)

- Discount factor(γ): determines how much the agent cares about rewards in the distant future relative to those in the immediate future. It has a value between 0 and 1. Lower value encourages short–term rewards while higher value promises long-term reward


- The Bellman equation in reinforcement learning is a mathematical formula used to determine the value of states or state-action pairs in a decision-making process. It serves as the foundation for many reinforcement learning algorithms, helping agents learn how to make optimal decisions to maximize rewards over time.
- Immediate Reward: The reward the agent receives right now.
- Future Rewards: The rewards the agent expects to collect by acting optimally in the future.
- The agent considers the immediate reward from its current state and action.
- It predicts the value of the next state, assuming it will continue to act optimally.
- By solving this equation iteratively, the agent can learn the best strategy to maximize its total reward over time.
