# DeepReinforcementlearningSubOptimalPolicy
This project involves to implementation of a suboptimal policy in the CartPole environment from OpenAI gym.
We have generated return plots for both discounted and undiscounted returns for each of the 60 policies. In each plot, a separate line represents a different γ value, and each point on a line corresponds to the return (discounted or undiscounted) for a specific iteration.

The results in the discounted graph are consistent with expectations: the average return is higher for higher γ values. Specifically, for γ=0.95, the expected return converges to approximately 20 within fewer than 5 iterations. For γ=0.99, the expected return eventually falls between 80 and 90 after only a few iterations—showing an improvement over γ=0.95, but not a dramatic one. For γ=1.0, the return values are considerably higher and more volatile, with maximum values reaching around 300 and several regions where returns range between 200 and 250. However, this is somewhat lower than anticipated, as we did not observe values approaching 500, which is expected given that our chosen strategy is sub-optimal. Even so, γ=1.0 dominates, indicating that when you do not diminish future rewards at all, the policy finds a strategy that maximizes the long-horizon reward. This makes sense in CartPole, where longevity directly translates to higher total reward.

For the undiscounted return plot, we again see one line per γ value, with each point representing the total reward at a given iteration. Unlike the discounted results, the lines here occasionally cross and exhibit more pronounced spikes. For example, γ=0.95 might briefly surpass γ=0.99, γ=1.0, and we see peaks around 200–300 that later dip back toward 100–150. This behaviour arises because the policies trained under discounted objectives— re now evaluated by a purely cumulative metric, which can yield unexpected rankings of performance. While γ=1.0 may still reach high values, there is no consistent dominance as in the discounted case, and the overall volatility is higher. These variations are normal when measuring undiscounted returns for policies optimized with different 
γ. They do not indicate a coding error; rather, they highlight that each policy’s training focus does not always align perfectly with a plain-sum reward evaluation.




