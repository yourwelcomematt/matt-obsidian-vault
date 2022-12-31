## Basic Gameplay

- Each player chooses a secret code:
	- The code must be 4 digits long
	- Each digit must be from 0-9
	- Each digit must be different
- The goal of the game is to guess the other player's secret code, with each player taking turns to guess their opponent's secret code
	- The opponent responds by telling the player:
		- The number of matching digits in the right positions (i.e. the number of bulls)
		- The number of matching digits in the wrong positions (i.e. the number of cows)


## Requirements

- A single player must be able to play against the computer
- Two secret codes are stored - one for the player and one for the computer
- Both the player and the computer only have 7 attempts to guess the other's secret code
- If the player enters an invalid input, they should be prompted to try again
- The player can choose from one of three difficulty levels:
	- Easy
	- Medium
	- Hard
- The game can read from a text file that contains multiple guesses from the player
- The game can save the results to another text file


![[Screen Shot 2022-12-25 at 5.57.19 PM.png]]