

![[reinforcement_learning.png]]
# Upper Confidence Bound
UCB is a deterministic algorithm for Reinforcement Learning that focuses on exploration and exploitation based on a confidence boundary that the algorithm assigns to each machine on each round of exploration. These boundary decreases when a machine is used more in comparison to other machines.
> example: which Ads customers will click on

## How it works
1. At each round n, we consider two numbers for machine m:
	- N(n) = number of times the machine m was selected up to round n.
	- R(n) = number of rewards of the machine m up to round n.
2. From these two numbers we have to calculate,
	- The average reward of machine m up to round n, $$r(n) = R(n) / N(n)$$
	- The confidence interval $[r(n) — Δ(n), r(n)+Δ(n)]$ at round n with, 
$$Δ(n)= \sqrt{ 1.5 * log(n) / N(n) } $$
3. We select the machine m that has the maximum $UCB = r(n)+Δ(n)$

> Intuitive explanation
https://medium.com/analytics-vidhya/upper-confidence-bound-for-multi-armed-bandits-problem-ea5d7bc840ff

# Thompson Sampling (Bayesian Bandits)
## How it works
1. At each round n, we consider two numbers for machine m:
	- $N_i^1(n)$ = number of times the ad $i$ got reward 1 up to round n.
	- $N_i^0(n)$ = number of times the ad $i$ got reward 0 up to round n.
2. For each ad $i$, we take a random draw from the beta distribution below:
	$$
	\theta_i (n) = \beta (N_i^1 (n)+1, N_i^0 (n) + 1)	
  $$
3. We select the ad that has the highest $\theta_i (n)$
