

##  Minimax Game using Minimax Implementation.

### Introduction
The objective is to design a minimax algorithm for Pacman (player-MAX) to play a game with three ghosts (player-MINs). The game tree will consist of MAX nodes and MIN nodes. MAX nodes will call a "max" function to collect the largest value from its successors, while MIN nodes will call a "min" function to collect the minimum value from its successors.

### Implementation
The implementation involves modifying the `getAction` function in the `MinimaxAgent` class in the `multiAgents.py` file. This function should:
- Recursively call the "max" function and the "min" function.
- Propagate the "leaf" node values to upper layers until the root node is reached.
- Finally, return the best action for player-max (Pacman) at the root node.

### Files to Edit
The main file to edit for this assignment is `multiAgents.py`, which is where the multi-agent search agent resides.

### Relevant Files
- `pacman.py`: This file runs Pacman games and includes a Pacman GameState class that will be extensively used in this assignment.
- `game.py`: Contains the logic behind how the Pacman world works, including supporting classes like AgentState, Agent, Direction, and Grid.
- `util.py`: Provides useful data structures for implementing search algorithms, including functions that may be helpful.

### Task: Minimax Agent
The task is to implement an adversarial search agent in the `MinimaxAgent` class stub provided in `multiAgents.py`. The minimax agent should be able to work with any number of ghosts. The minimax tree will have multiple min layers (one for each ghost) for every max layer.

The code should expand the game tree to an arbitrary depth and score the leaves of the minimax tree using the supplied `scoreEvaluationFunction`. The `MinimaxAgent` class extends the `MultiAgentSearchAgent` class, which provides access to `self.depth` (the number of search plies in the game tree). Each search ply corresponds to one Pacman move and the responses of all the ghosts. For example, a search with `self.depth=2` will involve Pacman and each ghost moving two times.

It is important to make references to the `self.depth` variable where appropriate, as this variable is populated based on command line options.

### Experiment
To run the experiment, use the following command:
```
python pacman.py -p MinimaxAgent -l minimaxClassic -a depth=4 --frameTime 0
```

### Hints and Observations
- The evaluation function for the Pacman test, `scoreEvaluationFunction`, is already provided and should not be modified.
- The minimax values of the initial state in the `minimaxClassic` layout are 9, 8, 7, and -492 for `self.depth=1`, 2, 3, and 4 respectively.
- Pacman is always agent 0, and the agents move in order of increasing agent index.
- All states in the minimax algorithm should be `GameStates`, which can be passed into `getAction` or generated using `GameState.generateSuccessor`.
- On larger boards such as `openClassic` and `mediumClassic`, Pacman tends to avoid dying but struggles to win. Pacman may move around without making progress and might miss nearby dots because it doesn't know where to go after eating them.
- To check the correctness of the code, the `autograder.py` script can be run with the following command:
```
python autograder.py -q q2
```
- The `autograder.py` script will show the algorithm's behavior on a number of small trees and a Pacman game. To run the script without graphics, use the `--no-graphics` option:
```
python autograder.py -q q2 --no-graphics
```
- It is expected that the correct implementation of minimax will lead to Pacman losing the game in some tests of the `autograder.py`. This behavior is correct and will pass the tests.

