# Q-Learning-Reinforcement-Learning
Q-Learning falls under the family of Reinforcement Learning algorithms and, more specifically, under the Value-based methods branch.

Before we look at Q-Learning, here’s a quick recap of the fundamental elements of Reinforcement Learning:

•	Agent — an “intelligent actor” that can interact with its environment, e.g. a player in a game.
•	Environment — the “world” where that agent “lives” or operates.
•	Action Space — a list or range of actions the agent can perform.
•	State/Observation Space — a list or range of possible environment configurations. A state/observation provides information to the agent about its environment (e.g. its location).
•	Reward — incentive (or disincentive) that we give to the agent when it performs desired (undesired) actions at various states. We can reduce future rewards relative to present rewards by using the discount factor {gamma(𝛾)}.
•	Exploration/Exploitation {epsilon(𝜖)}— enables us to set how much time the agent should spend exploring the environment vs exploiting its existing knowledge about the environment.
•	Episode — one complete cycle from the start position to the end position. E.g., in the context of a game, an episode would last from the moment your agent starts a new level until it dies or completes the level.
•	Alpha(𝛼) — learning rate, which influences the learning speed and convergence towards the optimal policy.
•	Policy(𝜋) —an agent’s strategy to pursue a goal.

How does Q-Learning work?

Difference between Policy-based and Value-based methods

Q-Learning falls into the category of Value-based methods, so let’s start by understanding the difference between Value-based and Policy-based methods.

•	Policy-based methods — we train the agent directly on what action to take in which state. It is described by a policy function that can be either deterministic (gives the precise action for each state) or stochastic (provides a probability distribution over actions).
•	Value-based methods — we train the agent indirectly by teaching it to identify which states (or state-action pairs) are more valuable so that it can be guided by value maximization. It is described by a value function where the value of a state is the expected discounted return the agent can get if it starts in that state.
Regardless of which method we use to train our agent, finding the optimal policy function or the optimal value function equates to discovering the optimal policy(𝜋).

Q-function and Q-table

Since Q-Learning is a Value-based method, we must have a value function, which we will call a Q-function. Inside, it will have a Q-table containing every state-action pair.
Training a Q-function is simply finding the values associated with each state-action pair stored in a Q-table. Knowing these values enables the agent to choose the best action at each state.

Q-Learning algorithm

Before we look at the actual Q-Learning algorithm, here are a couple more things to note:

•	On-policy vs Off-policy: Q-Learning is an off-policy algorithm, which means that during training, we use different policies for the agent to act (acting policy) and to update the Q-function (updating policy). Meanwhile, On-policy means that the same policy is used for acting and updating. More on this in the Python section.
•	Temporal Difference (TD) vs Monte Carlo: Q-Learning uses a TD approach, which means that during training, it updates the Q-function after each step. Meanwhile, the Monte Carlo approach is to wait until the end of the episode before making the update to the value function.

Q learning is a Value-based methods — we train the agent indirectly by teaching it to identify which states (or state-action pairs) are more valuable so that it can be guided by value maximization. Once we train the agent the Q-Table values is being updated through each step, until it reaches the maximum number of episodes, an episode as a fix number of steps, or the Q-table reaches it most optimal policy values, rewards that guide the best actions to take by the agent in each state, the algorithm converges. 

Important parameters to tune are epsilon, gamma, learning rate. 

Epsilon: enables us to set how much time the agent should spend exploring the environment vs exploiting its existing knowledge about the environment.

Gamma (Discount factor): Typically choose a value between 0.95 and 0.99. The purpose of a discount factor is to give us control over the preference for short-term vs long-term rewards. High Gamma values will prioritize long term rewards and low gamma values will prioritize short term rewards. 

Alpha(𝛼): Learning rate, which influences the learning speed and convergence towards the optimal policy.


