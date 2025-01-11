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




## 2. Bellman Equation 
- According to the Bellman Equation, long-term- reward in a given action is equal to the reward from the current action combined with the expected reward from the future actions taken at the following time. Let’s try to understand first.

What happens without Bellman Equation?

- Initially, we will give our agent some time to explore the environment and let it figure out a path to the goal. As soon as it reaches its goal, it will back trace its steps back to its starting position and mark values of all the states which eventually leads towards the goal as V = 1.

- The agent will face no problem until we change its starting position, as it will not be able to find a path towards the trophy state since the value of all the states is equal to 1. So, to solve this problem we should use Bellman Equation:

- V(s)=maxa(R(s,a)+ γV(s’))

- State(s): current state where the agent is in the environment
- Next State(s’): After taking action(a) at state(s) the agent reaches s’
- Value(V): Numeric representation of a state which helps the agent to find its path. V(s) here means the value of the state s.
- Reward(R): treat which the agent gets after performing an action(a).

- R(s): reward for being in the state s
- R(s,a): reward for being in the state and performing an action a
- R(s,a,s’): reward for being in a state s, taking an action a and ending up in s’
e.g. Good reward can be +1, Bad reward can be -1, No reward can be 0.

- Action(a): set of possible actions that can be taken by the agent in the state(s). e.g. (LEFT, RIGHT, UP, DOWN)

- Discount factor(γ): determines how much the agent cares about rewards in the distant future relative to those in the immediate future. It has a value between 0 and 1. Lower value encourages short–term rewards while higher value promises long-term reward

![pic 1](https://github.com/user-attachments/assets/e35d7cac-90e5-42f0-8470-33f46104bf57)



The Bellman equation in reinforcement learning is a mathematical formula used to determine the value of states or state-action pairs in a decision-making process. It serves as the foundation for many reinforcement learning algorithms, helping agents learn how to make optimal decisions to maximize rewards over time.
- Immediate Reward: The reward the agent receives right now.
- Future Rewards: The rewards the agent expects to collect by acting optimally in the future.
- The agent considers the immediate reward from its current state and action.
- It predicts the value of the next state, assuming it will continue to act optimally.
- By solving this equation iteratively, the agent can learn the best strategy to maximize its total reward over time.


## 3. Markov Property
- Markov property: The probability of a future state depends only on the current state, not on any past or future states.
- A Markov Decision Process (MDP) is a mathematical tool that helps make optimal decisions in dynamic systems where outcomes are partially random and partially controllable. MDPs are used in many fields, including artificial intelligence, robotics, ecology, economics, healthcare, and telecommunications . A Markov Decision Process (MDP) is a way to model situations where a decision-maker chooses actions to move between different states, aiming to maximize rewards, while dealing with some uncertainty about the outcomes of their actions.

  ![pic 2](https://github.com/user-attachments/assets/bfaa60f2-be7a-4a5a-bdf8-cc790e62ca7e)


## 4. Policy v/s Plan 
1. Policy:
A policy is a strategy or a rule that tells the agent what action to take in any given state. It defines the agent's behavior.

- Deterministic Policy: For each state, the policy specifies exactly one action.
- Stochastic Policy: For each state, the policy specifies a probability distribution over possible actions (i.e., the agent may take different actions in the same state with certain probabilities).
- A policy is like a "decision-making guide" for the agent, telling it what to do at each moment.
  
2. Plan:
A plan refers to a sequence of actions or a set of decisions an agent will take to achieve a goal. It is the agent’s roadmap to reach a desired outcome. In some contexts, planning involves searching for the best sequence of actions in advance.

- In classical planning, agents create a detailed plan beforehand, usually with perfect knowledge of the environment.
- In reinforcement learning, an agent may learn its plan by exploring the environment and updating its knowledge through trial and error.
- A plan is like a "predefined roadmap" that shows a step-by-step approach to achieving a goal, often learned through experience.
  
Key Difference:
- A policy is an ongoing decision-making rule used in any state the agent encounters. It can be learned and refined over time.
- A plan is usually a longer-term, goal-oriented sequence of actions, which can either be precomputed or dynamically planned as the agent learns.
- In RL, the policy is what the agent follows during training or execution, while the plan (if needed) might be considered when figuring out how to achieve long-term objectives.

## 5. Q-Learning 
Q-learning is a fundamental algorithm in Reinforcement Learning (RL). It allows an agent to learn how to act optimally in a given environment by maximizing the total rewards it receives over time. Here's an intuitive breakdown:

1. Key Idea: Learning by Experience
Q-learning enables an agent to learn from its interactions with the environment. The agent doesn't need a pre-built model of the environment but instead explores and adjusts its actions based on feedback (rewards) received.

2. Understanding Q-Values (Quality Values)
Think of the Q-value as a "score" that tells the agent how good a particular action is in a specific state.
Higher Q-values mean better actions in that state.
The agent keeps track of these Q-values in a Q-table: a table where each cell corresponds to a state-action pair.

4. Exploration vs. Exploitation
The agent faces a choice:

- Exploration: Try new actions to discover potentially better rewards.
- Exploitation: Stick to actions with the highest known Q-values.
This is often managed using an ε-greedy strategy, where the agent randomly explores with probability 
ϵ, and otherwise exploits its current knowledge.

5. Learning Over Time
Initially, the Q-values are random or zero (the agent knows nothing).
As the agent interacts with the environment, it updates its Q-values based on the feedback it receives.
Over time, the Q-table converges to represent the optimal strategy.
6. Why is it Powerful?
- It works for model-free environments (the agent doesn’t need to know the environment’s dynamics).
- It helps the agent learn optimal policies for decision-making.
- Q-learning can be extended to more complex problems using Deep Q-Learning (DQL), where neural networks approximate the Q-values.
Intuition in Practice
Imagine a robot in a maze:

The robot starts without a clue where the exit is.
It explores the maze, taking actions (e.g., move up, down, left, right).
After bumping into walls and moving closer to the exit, it receives rewards (or penalties).
The Q-values are updated after each step, helping the robot remember which actions led to better outcomes.
Eventually, the robot learns the best path to the exit by maximizing its total rewards.
