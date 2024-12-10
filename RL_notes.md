

Markov Definition

![image.png](image.png)

Markov Property

![image.png](image%201.png)

![image.png](image%202.png)

![image.png](image%203.png)

Why Discounting is a good idea

![image.png](image%204.png)

![image.png](image%205.png)

Bellman Equation

![image.png](image%206.png)

Direct solution of Bellman Equation

![image.png](image%207.png)

![image.png](image%208.png)

Solve bellman equation directly

![image.png](20241209234600.png)

Iterative policy evaluation

![](20241209234746.png)

![image.png](image%2011.png)

Optimal Policy and optimal value and Q function

![](20241209234858.png)

![](20241209234933.png)

Three Assumption for BOE

![image.png](image%2014.png)

Convergence Rule

![image.png](image%2015.png)

Dynamic Programming

Two assumption of DP

1. MDP to be finite
2. A perfect model for environment, means we know the trasition and reward function

![image.png](image%2016.png)

For every states ⇒

![image.png](image%2017.png)

In short, update value function using policy untill value function converge, then be greedy to update the policy, then go back to step 2 untill the policy converge.

**Policy Iteration Algorithms**
![](20241209235040.png)
**Value Iteration Algorithms**
![](20241209235157.png)

If value of all states are updated same time or individually

![image.png](image%2020.png)

![image.png](image%2021.png)

Why value iteration is guranteed to converge

![](20241209235316.png)
![](20241209235345.png)

Monte Carlo

![image.png](image%2024.png)

![](20241209235535.png)
First Visit MC vs Evert Visit MC
![](20241209235657.png)
Batch VS Online Monte-Carlo

![image.png](image%2026.png)

No Need to store samples traces

![image.png](image%2027.png)

Temporal Difference Learning

![image.png](image%2028.png)

MC update the value using the actual return R, where dp use the estimated return to update the value

![image.png](image%2029.png)

![image.png](image%2030.png)

![image.png](image%2031.png)

![image.png](image%2032.png)

![image.png](image%2033.png)

What is Markov Property

![image.png](image%2034.png)

![image.png](image%2035.png)

MC Control

Why use model free control

![image.png](image%2036.png)

On-policy vs off-policy

![image.png](image%2037.png)

![image.png](image%2038.png)

Means we have a policy that gives a non-zero probablity to all possible actions

![image.png](image%2039.png)

Epsilon Greedy

![image.png](image%2040.png)

![](20241209235827.png)
![image.png](image%2042.png)

![image.png](image%2043.png)

![image.png](image%2044.png)

![image.png](image%2045.png)

TD Control

Difference between online and offline learning

| Aspect          | Offline Learning                                     | Online Learning                                         |
|------------------|-----------------------------------------------------|--------------------------------------------------------|
| Data            | Pre-collected dataset (fixed and static).            | Dynamically collected through interaction with the environment. |
| Interaction     | No interaction during training (training is offline).| Continuous interaction and learning during training.   |
| Updates         | Policy/value function is updated using the dataset once or iteratively (batch learning). | Policy is updated incrementally after every interaction. |
| Adaptability    | Not adaptive to new environments unless retrained.   | Adaptive to changing environments in real-time.        |
| Exploration     | Limited to what the dataset covers (no active exploration). | Actively explores to discover new states and actions.  |


![image.png](image%2047.png)

**SARSA**
![](20241210000101.png)
![image.png](image%2049.png)

![image.png](image%2050.png)


**Q-learning**
![](20241210000229.png)
![](20241210000250.png)
Target policy and behaviour policy

For on policy method, same policy is used to generate episode and to optimise. However, for off-policy method, the target policy are the one use to optimise and behaviour policy are the one used to generate episode.

![image.png](image%2052.png)

![image.png](image%2053.png)

![image.png](image%2054.png)

Function Approximation

![image.png](image%2055.png)

![image.png](image%2056.png)

![image.png](image%2057.png)

![image.png](image%2058.png)

![image.png](image%2059.png)

The estimates make the estimates closer to the real V/Q value, but not reach the real V/Q value, in the end, it will get close enough to the true V/Q value.

![image.png](image%2060.png)

DQN

![image.png](image%2061.png)

![image.png](image%2062.png)

![image.png](image%2063.png)

![image.png](image%2064.png)

![image.png](image%2065.png)

![image.png](image%2066.png)

![image.png](image%2067.png)
**Experience Reply Algorithmes**
![](20241210000346.png)
![image.png](image%2069.png)

![image.png](image%2070.png)

Clipping Rewards: Varation in rewards maeks the training unstable ⇒ Clip positive reward to 1, and negative reward to -1

![image.png](image%2071.png)

Skipping Frame to reducing computational cost and accelerating training times.

![image.png](image%2072.png)

Dobule Q network

Normal netowork will produce a maximisation bias

![image.png](image%2073.png)

Use the main netowrk instead of the target network to do action selection (compared with normal target network)

![image.png](image%2074.png)

![image.png](image%2075.png)

Target Network
![](20241210000524.png)
Double Q network provide prediction that are closer to the final value and more stable and less biased.

![image.png](image%2077.png)

Policy Gradient

Why using policy based method:

For some environment that has large action space (especially continous action space), iterate through all actions might take a long time, thus have a policy that direct output action would be more efficient.

![image.png](image%2078.png)

Objective of Policy Gradient

![](20241210000632.png)
Finit difference are simple, inefficient(especially when have tons of parameters), and sometime efficient (it can even work for non-differentiable ones)

![image.png](image%2080.png)

Directly calculating the policy gradient

![](20241210000758.png)

REINFORCE algorithms

![image.png](image%2082.png)

![image.png](image%2083.png)

![image.png](image%2084.png)

REINFORCE algorithms suffer greatly from variance, a single erratic trajectory can cause a suboptimal shift into wired area of optimisation.

![image.png](image%2085.png)
Gussian Policy
![](20241210001508.png)
Policy gradients is trial-and-arror (like MC)
![](20241210001535.png)
The action in future cannot affect the actions in the past.

![image.png](image%2088.png)

Actor Critics

Policy based method has low bias but larger variance

![image.png](image%2089.png)

![image.png](image%2090.png)

TD Error

- Generate the trace
- Update the policy value
- calcualte the TD error
- update the Q value error

![](20241210001936.png)
Advantage Actor Critic (A2C)
![](20241210002012.png)
![image.png](image%2093.png)

A3C is the parallel and asynchronous version of A2C, the there is a global network which takes the gradient of each agent, and the agent will sometimes update their states according to global network.

![image.png](image%2094.png)

![image.png](image%2095.png)

![image.png](image%2096.png)

![image.png](image%2097.png)

![image.png](image%2098.png)

![image.png](image%2099.png)

![image.png](image%20100.png)

![image.png](image%20101.png)

![image.png](image%20102.png)

![image.png](image%20103.png)
