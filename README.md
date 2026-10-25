# Pirate Intelligent Agent (CS 370 Project Two)

**Author:** Sean Dwyer

This repository contains my Jupyter Notebook for the Treasure Hunt game. In the game, a pirate agent has to find the treasure in an 8x8 maze, and it learns to do this using deep Q-learning.

## Briefly explain the work that you did on this project

**What I was given:** The project came with a starter notebook and two Python classes. `TreasureMaze.py` represents the environment, which includes the maze as a matrix, the pirate's position, the moves, and the rewards. `GameExperience.py` stores the episodes (replay memory) that the agent learns from. The notebook also had helper code already written: the maze, a `show()` function to display it, `play_game()`, `completion_check()`, `build_model()` for the neural network, and a `train_step()` function. I did not change any of the `.py` files.

**What I created:** I wrote the `qtrain()` training function, which is the deep Q-learning algorithm. Each epoch it resets the maze to a random free cell and plays until the game ends. It chooses actions using epsilon-greedy selection (random valid moves to explore, the model's best move to exploit), calls `act()` to get the next state, reward, and game status, and tracks wins and losses. It stores each episode in replay memory and trains the network on a batch of stored episodes. It also updates a target network, lowers the exploration rate over time, and stops once the pirate wins from every starting cell. My pirate reached a 100% win rate at epoch 570. I also wrote a design defense explaining how the agent works and how it compares to how a person would solve the maze.

## Connect your learning to the larger field of computer science

**What do computer scientists do and why does it matter?**
Computer scientists solve problems by designing systems, algorithms, and software that people and organizations rely on. In this project, that meant building an agent that learns a path through a maze without being told the answer. The same ideas show up in navigation, robotics, games, and other places where a system has to make decisions. It matters because these systems affect how people work, travel, and communicate, so the quality of the work has real consequences.

**How do I approach a problem as a computer scientist?**
I start by understanding the problem and what is already given, then break it into smaller parts and build and test them. For this project I reviewed the starter code first, wrote the training loop, ran it, and found it was not finishing. I traced the problem back to how the agent picked its moves during training compared with how it was checked at the end, and I fixed that. The main lesson was to check my assumptions, read the results carefully, and adjust, rather than just trying random changes. I also learned to weigh tradeoffs, such as exploration versus exploitation and training time versus accuracy.

**What are my ethical responsibilities to the end user and the organization?**
To users, I am responsible for building software that is safe, honest, and respects their privacy and trust. To the organization, I am responsible for doing careful, accurate work, being honest about what my code can and cannot do, and giving credit to sources and tools I use. I should also think about how a system could be misused or cause harm, and speak up when something seems wrong. In this project, that meant being clear about which code I wrote and which was provided, and citing my sources in the design defense.

## Files

- `Dwyer_Sean_ProjectTwo.ipynb`: the completed notebook for the pirate intelligent agent
