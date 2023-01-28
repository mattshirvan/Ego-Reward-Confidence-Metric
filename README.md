# Ego-Reward-Confidence-Metric
Einstein ego equation utilized as a confidence metric against a threshold for decision making.

The following is an example of pseudocode of the ego equation as a confindence metric with the reward signal either explicitly or
implicitly encoded into the ego equation:

#### # Compute Knowledge <br>
knowledge = calculateKnowledge();

#### # Calculate the ego equation <br>
ego = $\lbrace ^{ \frac{1}{knowledge}, \\ knolwedge \\ > \\ 0} _{1, \\ otherwise}$ <br>

#### # Calculate the reward for each action taken by the agent <br>
reward = calculateReward(action)

#### # Incorporate the reward into the ego equation explicitly or implicitly <br>
ego = $\lbrace ^{ ego * reward, \\ goal \\ explicit} _{ego, \\ goal \\ implicit}$ <br>

#### # Use the ego equation to determine the agent's level of confidence <br>
confidence = determineConfidence(ego)

#### # Calculate the confidence threshold <br>
threshold =  $\lbrace ^{ c \\ \in  \\ \Re, \\ constant \\ threshold} _{\epsilon, \\ stochastic \\ threshold}$ <br>

#### # Use the confidence to determine when the agent should take risks and explore new strategies <br>
if (confidence > threshold): <br>
&emsp; takeRisks(); <br>
&emsp; exploreNewStrategies(); <br>


#### # Use the confidence to determine when the agent should focus on exploiting existing strategies <br>
else: <br>
&emsp; exploitExistingStrategies(); <br>
