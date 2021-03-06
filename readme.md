
# Trifoil

Trifoil is a long-form, 2 player turn based strategy game in the vein of chess or go that can be played with 6 or more blinks.
Players take turns placing links, pushing them, and rotating sections of the board to try to build a long chain before their opponent can.

The rules are flexible along with the initial board state, so the game can evolve to be simple, complex, or even just different depending on what you want to play!

## Setup

You can play the game the [Blinks simulator](https://move38.github.io/Blinks-Simulator/) (though one person will have to screen share and the other will need to dictate their moves) or with "online multiplayer" by duplicating [this presentation](https://docs.google.com/presentation/d/1zNeIM4jhh3tsyYy73fLiq9a-cftgsKfThUjC3I1FVD8/edit?usp=sharing).
All features work in the simulator and it prevents you from accidentally making illegal moves but because of its instability, tendency to eat blinks, and lack of networking we recommend playing in Google Slides.

To use the simulator copy the code from `trifoil.ino` into the simulator and press "Run Code" on the top right.

## How to play

The base board setup with 6 blinks is as follows:

![board_6](https://github.com/aaronsantiago/trifoil/blob/master/images/board_6.png?raw=true)

There are 2 players, red and blue. The board's background color is lit up with the current player's color.
Each turn, players can use up to 2 actions (see available actions), except for the first turn of the game where a player can only use one action.

A player wins when they have a chain of 5 links of their own color!
The game also ends when either player has placed 9 links, in which case the player with the longest chain wins (see end game rules).

### Available actions

On the first turn of the game, the player going first only gets 1 action.
Every turn afterwards each player gets 2 actions.
Note: You cannot make a move which returns the board to the previous board state.

#### Place a link

You can place a link by first clicking the blink you wish to place on, then clicking the blink touching the face that you want to place!  
![input_move](https://github.com/aaronsantiago/trifoil/blob/master/images/input_move.gif?raw=true)

This means that you can't place any links facing outwards from the formation.

#### Spin 

You can disconnect, rotate, and reattach one of 3-blink triangles that form the corners of the board as one of your actions.
They are labelled "Δ", "Ω", and "θ" in the board above!

Players are allowed to do this ONLY if they have less links on that triangle than their opponents.
This is referred to as the "minority rule."
If they have the same amount of links as the opponent, they cannot spin it.  
![spin](https://github.com/aaronsantiago/trifoil/blob/master/images/spin.gif?raw=true)

#### Push

You can push a link outwards from a Blink the using the same input as placing a link.
E.g. if you attempt to place a link where a link already exists, you will instead push it--pushing any other links in the way in a straight line as well!
You can only push links of your own color.  
![push](https://github.com/aaronsantiago/trifoil/blob/master/images/push.gif?raw=true)  
![push_multiple](https://github.com/aaronsantiago/trifoil/blob/master/images/push_multiple.gif?raw=true)

If your push would result in a link being deleted off of the edge of the board, it is considered invalid and will do nothing.  
![push_wall](https://github.com/aaronsantiago/trifoil/blob/master/images/push_wall.gif?raw=true)


### After your move

#### Switching turns

Once you have made your moves, double click any Blink to commit a move and switch turns.  
![switch_turn](https://github.com/aaronsantiago/trifoil/blob/master/images/switch_turn.gif?raw=true)

#### Undoing moves

If you made a mistake, triple click any Blink <ins>before</ins> you commit your move to undo the board to the beginning of your turn!  
![undo](https://github.com/aaronsantiago/trifoil/blob/master/images/undo.gif?raw=true)

#### Resetting the game

Once the game ends, you can long press any Blink to reset the game.  
![reset](https://github.com/aaronsantiago/trifoil/blob/master/images/reset.gif?raw=true)


### End Game Rules
#### Win condition
A player instantly wins if they have a chain of at least 5 links.  
In the following picture, the red player has just won!  
![red_win](https://github.com/aaronsantiago/trifoil/blob/master/images/red_win.png?raw=true)

Each Blink can contribute at most 2 links to a chain.  
In this picture, the blue player has *not* won, they only have a chain of 4 pieces.  
![blue_notwin](https://github.com/aaronsantiago/trifoil/blob/master/images/blue_notwin.png?raw=true)

#### End conditions
If no possible move can be made the game ends and whoever has the longest chain wins.

## Variations

The rulebook and the board are flexible, so use your imagination--the possibilities are endless!

### Rule Variations

 - Try limiting number the total number of links you can place to 
 . If either player runs out of links, the player with the longest chain wins.
 - Try playing until any one Blink is filled with 6 links of any color. When that happens, the longest chain wins.
 - Try playing with 3 moves instead of 2! You might need to increase the winning chain length.
 - Removing the limit of links that a Blink can contribute to a chain creates a much more defensive game!

### Map Variations

Here are a few variations that we have come up with!
You can experiment with different rotatable shapes, different numbers of blinks, different arrangements, and different win lengths!

#### 8 Blinks

Winning Chain Length: 5  
Available links per player: 11   
![board_8](https://github.com/aaronsantiago/trifoil/blob/master/images/board_8.png?raw=true)

#### 9 Blinks

Winning Chain Length: 6  
Available links per player: 12  
![board_9](https://github.com/aaronsantiago/trifoil/blob/master/images/board_9.png?raw=true)

#### 10 Blinks

Winning Chain Length: 6   
Available links per player: 13  
![board_10](https://github.com/aaronsantiago/trifoil/blob/master/images/board_10.png?raw=true)

#### 12 Blinks

Winning Chain Length: 7  
Available links per player: 15  
![board_12](https://github.com/aaronsantiago/trifoil/blob/master/images/board_12.png?raw=true)
