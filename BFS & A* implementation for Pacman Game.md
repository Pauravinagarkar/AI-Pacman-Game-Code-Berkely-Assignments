The code for this assignment consists of several Python files, some of which you will need to read and understand in order to complete the assignment, and some of which you can ignore. You can download and unzip all the code and supporting files `search_and_games.zip`.

## Files to Edit:
You will edit portions of `search.py`, where all your search algorithms will reside. There is no need to change the other files/code in the source code folder.

The following items are essential components of your algorithm. Please explain them in the submitted PDF report.
- For Breadth-First Search:
  - How Frontier is defined
  - How graph search is implemented
  - How successors (children nodes) of the current node are generated and how they enter the Frontier queue
  - How `goalTest` is called
  - How the solution path is returned
- For A* Search:
  - How `g`, `h`, and `f` values are obtained for a node
  - How Frontier is defined
  - How graph search is implemented
  - How successors (children nodes) of the current node are generated and how they enter the Frontier queue
  - How `goalTest` is called
  - How the solution path is returned.

## Files you might want to look at:
- `pacman.py`: The main file that runs Pacman games. This file describes a Pacman `GameState` class, which you use in this project.
- `game.py`: The logic behind how the Pacman world works. This file describes several supporting classes like `AgentState`, `Agent`, `Direction`, and `Grid`.
- `searchAgents.py`: Where all your search-based agents will reside.
- `util.py`: Useful data structures for implementing search algorithms.

## Files you will not edit:
- `agentTestClasses.py`: Autograding test classes
- `graphicsDisplay.py`: Graphics for Pacman
- `graphicsUtils.py`: Support for Pacman graphics
- `textDisplay.py`: ASCII graphics for Pacman
- `ghostAgents.py`: Agents to control ghosts
- `keyboardAgents.py`: Keyboard interfaces to control Pacman
- `layout.py`: Code for reading layout files and storing their contents
- `autograder.py`: Project autograder
- `testParser.py`: Parses autograder test and solution files
- `testClasses.py`: General autograding test classes
- `test_cases/`: Directory containing the test cases for each question

This assignment is adapted from the Pacman AI projects developed at UC Berkeley, [http://ai.berkeley.edu](http://ai.berkeley.edu).

## Welcome to Pacman

After downloading the code (`search_and_games.zip`), unzipping it, and changing to the directory, you should be able to play a game of Pacman by typing the following at the command line:
```
python pacman.py
```

Pacman lives in a shiny blue world of twisting corridors and tasty round treats. Navigating this world efficiently will be Pacman's first step in mastering his domain.

The simplest agent in `searchAgents.py` is called the `GoWestAgent`, which always goes West (a trivial reflex agent). This agent can win:
```
python pacman.py --layout testMaze --pacman GoWestAgent
```

But things get ugly for this agent when turning is required:
```
python pacman.py --layout tinyMaze --pacman GoWestAgent
```

If Pacman gets stuck, you can exit the game by typing `CTRL-c` into your terminal.

Note that `pacman.py` supports a number of options that can each be expressed in a long way (e.g., `--layout`) or a short way (e.g., `-l`). You can see the list of all options and their default values via:
```
python pacman.py -h
```

Also, all of the commands that appear in this portion of the project also appear in `commands.txt`, for easy copying and pasting.
