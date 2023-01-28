# Ego-Reward-Confidence-Metric
Einstein ego equation utilized as a confidence metric against a threshold for decision making.

The following is an example of pseudocode of the ego equation as a confindence metric with the reward signal either explicitly or
implicitly encoded into the ego equation:

#### # Compute Knowledge <br>
Knowledge $\gets$ R + $\bar{R}$ + $\sum_{} \vec{Q}$ + $\sum_{}$ $\vec{\pi}$ + $\sum_{} \vec{W}$ + (ANY Knowledge available to agent)<br>

#### # Calculate the ego equation <br>
Ego $\gets$ $\lbrace ^{ \frac{1}{Knowledge}, \\ Knolwedge \\ > \\ 0} _{1, \\ otherwise}$ <br>

#### # Calculate the reward for each action taken by the agent <br>
reward $\gets$ calculateReward(action)

#### # Incorporate the reward into the ego equation explicitly or implicitly <br>
Ego $\gets$ $\lbrace ^{ Ego * reward, \\ goal \\ explicit} _{Ego, \\ goal \\ implicit}$ <br>

#### # Use the ego equation to determine the agent's level of confidence <br>
confidence $\gets$ determineConfidence(Ego)

#### # Calculate the confidence threshold <br>
threshold $\gets$  $\lbrace ^{ c \\ \in  \\ \Re, \\ constant \\ threshold} _{\epsilon, \\ stochastic \\ threshold}$ <br>

#### # Use the confidence to determine when the agent should take risks and explore new strategies <br>
if (confidence > threshold): <br>
&emsp; takeRisks(); <br>
&emsp; exploreNewStrategies(); <br>


#### # Use the confidence to determine when the agent should focus on exploiting existing strategies <br>
else: <br>
&emsp; exploitExistingStrategies(); <br>
