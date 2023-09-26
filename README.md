# ISYE6644 – Team191 Final Project
## Distribution of a Coin and Dice Game Turns to Complete


### Set-Up:

The code for this project was developed in a jupyter lab environment (ipynb file) running Python version: 3.8.8
The code requires the following Python base libraries: random, math, statistics, collections

The following packages and specific versions were also used (other versions might work but haven't been tested):

Name                    Version 
matplotlib                3.6.2
pandas                    1.5.1
scipy                     1.9.3
statsmodels               0.13.5


### Project Description:

There are two players, A and B. At the beginning of the game, each starts with 4 coins, and there are 2 coins in the pot. A goes first,
then B, then A.... During a particular player’s turn, the player tosses a 6-sided die. If the player rolls a:

1, then the player does nothing.
2: then the player takes all coins in the pot.
3: then the player takes half of the coins in the pot (rounded down).
4,5,6: then the player puts a coin in the pot.


A player loses (and the game is over) if they are unable to perform the task (i.e., if they have 0 coins and need to place one in the pot). We define a cycle as A and then B completing their turns. 
The exception is if a player goes out; that is the final cycle (but it still counts as the last cycle). 
We are trying to determine the expected number (and maybe even the distribution) of cycles the game will last for. 
I’m guessing that you can use “first-step” analysis to get the expected value. Simulation seems the easiest thing to do to get the entire distribution.


### User-Guide:

This project was completed using a single Jupyter notebook file (CoinAndDiceGame.ipynb).

The Jupyter notebook starts off by reminding the user what the rules and objectives are for the base game in a text markdown cell.

Code Cell 1 imports dependencies.

Since a random roll of a die is the ciritcal component of this simulation we wanted to verify a good pseudo-random number generator is being used. While we trust that the random library has random number generators with good properties, we wanted to perform visual (Code Cell 2), goodness of fit (Code Cell 3),
and independence (Code Cell 4) tests just to verify (since this is a simulation class). 

Code Cell 5 defines the variables that control the start of the game. We can change these as needed to test other game scenarios and perform a deeper analysis:
player_starting_coins = 4
pot_starting_coins = 2
penalty = 1
dice_sides = 6
penalty_rolls = [4,5,6]

Code Cell 6 runs a single game iteration printing out the results after each turn. This was used during development and verification of code logic and running it is not needed for the actual simulation.

Code Cell 7 runs 1,000,000 simulations of the game gathering statistics on the number of turns and who won the game. This code can take a few minutes to run depending on the game parameters. The number of simulations can be decreased or increased as needed.

Code Cell 8 takes the output from 1,000,000 simulations and displays which player won the game the most, some general statistics on the number of turns before the game ended, and then displays a histogram of the distribution of the number of turns taken to complete the game.









