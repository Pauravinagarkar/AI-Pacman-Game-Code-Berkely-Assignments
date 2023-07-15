# Artificial Intelligence

# Reinforcement Learning

You will download `rl.zip` and modify the functions in `class QLearningAgent(ReinforcementAgent):` of `qlearningAgents.py`.

### Task A: Implement a Q-learning agent
Implement a Q-learning agent that can navigate a grid world. The agent learns by trial and error from interactions with the environment through its `update(state, action, nextState, reward)` method. The `QLearningAgent` class in `qlearningAgents.py` provides a stub of a Q-learner, which can be selected with the option `-a q`.

You need to implement the following functions in `qlearningAgents.py`:
- `update(state, action, nextState, reward)`: Updates the Q-values based on the observed state, action, next state, and reward.
- `computeValueFromQValues(state)`: Computes the maximum Q-value over all possible actions in a given state.
- `getQValue(state, action)`: Returns the Q-value for a specific state-action pair.
- `computeActionFromQValues(state)`: Computes the best action to take in a given state based on the Q-values. In case of ties, randomly break them for better behavior. The `random.choice()` function can be used for this purpose.
- Important: Make sure to only access Q-values by calling the `getQValue` function in `computeValueFromQValues` and `computeActionFromQValues`.

### Task A - Experiment 1
With the Q-learning update implemented, you can observe the Q-learner learn under manual control using the keyboard:
```
python gridworld.py -a q -k 4 -m --noise 0.0
```
- `-k` controls the number of episodes the agent gets to learn.
- `-m` means you manually control Pacman's actions.
- `--noise 0.0` means there is no randomness, making it a deterministic game.

Manually steer Pacman north and then east along the optimal path for four episodes. Afterward, you should see the updated Q-values.

**Hint:**
- In `computeValueFromQValues` and `computeActionFromQValues`, obtain the available actions using `self.getLegalActions(state)`.
- Observe how the agent learns about the state it was just in, not the one it moves to.

Include a screenshot of the final result (gridworld with updated Q-state values) after executing 4 manual episodes in your PDF report.

### Task A - Experiment 2
Run the following command:
```
python autograder.py -q q3
```
Your code is expected to pass all four test cases. Include a screenshot of the result showing that your code has passed all four test cases in your PDF report.

### Task B: Modify the `getAction` function
Continue modifying the `getAction` function in `qlearningAgents.py`. This function computes the action to take in the current state. There is a parameter `self.epsilon`, which is a probability. With probability `self.epsilon`, the agent should take a random action from all legal actions available in that state. With probability `1 - self.epsilon`, the agent will take the best policy action obtained from the `computeActionFromQValues` function.

### Task B - Experiment 1
Run the following command and observe how the Q-learner updates the Q-state values for 100 episodes:
```
python gridworld.py -a q -k 100
```
Include a screenshot of the final result (gridworld with updated Q-state values) after executing 100 automatic episodes in your PDF report.

### Task B - Experiment 2
Run the following command and observe how the crawler bot learns to move to the right. You can decrease the "Step Delay" to 0.0125 by pressing the top-left "-" button to see the displayed results sooner:
```
python crawler.py
```
Include a screenshot of the intermediate result of your code when the crawler bot is in the middle of the scene in your PDF report.

### Task B - Experiment 3
Run the following autograder, and your code should pass all four test cases:
```
python autograder.py -q q4
```
Include a screenshot of the result showing that your code has passed all four test cases in your PDF report.

