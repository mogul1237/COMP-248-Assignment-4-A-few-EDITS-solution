# COMP-248-Assignment-4-A-few-EDITS-solution

Download Here: [COMP 248 Assignment 4-A few EDITS solution](https://jarviscodinghub.com/assignment/comp-248-assignment-4-a-few-edits-solution/)

For Custom/Original Work email jarviscodinghub@gmail.com/whatsapp +1(541)423-7793

Purpose: The purpose of this assignment is to practice defining new
types/classes and then using them in your program.
CEAB/CIPS Attributes: Design/Problem analysis/Communication Skills
General Guidelines When Writing Programs:
See previous assignments.
Qwixx
You will write a version of the dice game Qwixx.
In this game there are 6 dice, 2 white dice and 4 colour dice: red, yellow,
green and blue and each player has a game board as shown below:
The goal of the game is to score as many points as possible. The more numbers you cross off the
higher your score. There are 4 rows of numbers, each a different color, and two of them go from
2-12 whereas the other two go from 12-2. The main rule is that you have to start on the left and
go to the right — and if you pass up a number, well you’re out of luck. In other words, you can
mark off a number only if it’s to the right of all marked-off numbers in the same row. So, if you
marked of say the 2, 3 and 6 on the red row, the next number you can mark is 7 (or higher). You
cannot mark off 4 and 5 anymore.
At the start of each new round:
 The player changes (this is now the players who’s turn it is).
 The dice are rolled.
 All players can use the total number of the two white dice to cross off that number in any
row on their sheet (as long as they follow the right left to left right rule).
 Next, the player who’sturn it is gets to choose a second number to cross off using 1 white
dice plus one colored dice. For example, if you had a white 3 and a red 6 you could cross
off a 9 in your red row. On your turn you must take a number or take a penalty (worth
-5 at the end of the game). Note that are no penalties for passing on the white dice total.
The game ends when:
 Any 2 of the colour rows have been locked out (by any player crossing off the 12 or 2 at
the far right of the score pad) or a player has passed 4 times (i.e. has -20 points).
Scoring to determine the winner:
 At the end of the game you count up how many numbers are crossed off in each row and
score accordingly based on the scoring grid shown below in the methods description
section.
 Subtract the number of negative points from the total.
 The winner is the player with the most points.
In order to get you started here are the classes, instance variables, and methods you should have.
You will create 4 classes: Dice, Move, Player, and Qwixx.
1. Define a Dice class:
a. A Dice object has 2 attributes: a String colour and an integer currentSide.
b. Default constructor which sets the colour to white and sets an initial currentSide using the
rollDice() method (see below).
c. A constructor that takes one input, a colour, and sets an initial currentSide using the
rollDice() method (see below).
d. A get/set (mutator/accessor) method for colour and a get method for currentSide.
e. A toString() method that returns the colour and current side of the dice as a String.
f. A rollDice() method which randomly assigns a number between 1 and 6 to currentSide
and return the result of the roll.
2. Define a Move class:
a. A Move object has 2 attributes: a character colour and an integer number.
b. Get/set (mutator/accessor) methods for colour and number.
c. A constructor that takes two inputs, a colour and a number and sets the attributes
accordingly.
d. A static methods convertColourtoNum(char colour) method that takes a char and converts it
to the index of the row for that colour (i.e. ‘R’ = 0, ‘Y’ = 1, G =’2’, ‘B’ = 3) and returns that
index. This method will help you index the right array element during the game to cross
it out.
3. Define a Player class:
a. A Player object has seven attributes: a String name, a 2D String[4][11] gameBoard (the col
will represent the colour (Red, Yellow, Green and Blue), and the row the numbers in that
colour row (from 12-2 or 2-12), 4 integers to keep track of the last number that was
crossed of in each colour row, and an integer negativePoints to keep track of how many
negative points they accumulated by passing.
b. A default constructor which initializes all of the attributes, the game board should be
initialized using the initializeGameboard() method described below.
c. A constructor which takes one parameter, a String for the player name.
d. Accessor/get methods for each of the attributes except the game board.
e. An initializeGameboard() which initializies each row of the gameboard; for Red and Yellow
from 12-2 2-12 and for Green and Blue from 2-12 12-2.
f. An addNegativePoints(int pts) method that takes a parameter pts and adds these to the
negativePoints of the player.
g. A printGameBoard() method that prints out the player’s gameboard (including the name of
the player who’s board is being printed.
h. A makeMove(Move m)method, that takes as input a move and crosses off the appropriate
colour/number combination on the player’s gameboard. Hint: you may wish to make use
of your convertColourtoNum(char colour) method.
i. A getBoardTotalMethod() which calculates the total for the gameboard based on the
following (the top row is how many numbers are crossed off, the bottom how many
points). You should calculate the points per each colour based on how many numbers
were crossed off and subtract the player’s negative points to get the total.
Note: In this version of the game there is no way to score 12 for any given color
4. A Qwixx class:
a. The Qwixx class is where all the action happens. In this class we have the following
attributes: an array of Dice[] that will contain each of the coloured dice and two white
dice. An array of Players[] that contains the players in the game, four boolean values that
keep track of whether a colour is locked and therefore no longer playable (recall a colour
is locked when any player crosses off the 12 or 2 at the far right of the score pad of that
colour), a static variable NEGPTS which is set to -5.
b. A constructor that takes an array of Players and initializes the Players[] with it. The
constructor should also initialize the Dice[].
c. The following methods: rollDice() which randomly assigns the current side of each of the
6 dice using the rollDice() method of the Dice class. A printRolledDice() method that prints
all of the dice and their current values.
d. A playWhiteDiceMove() which takes care of the moves on the white dice. Recall that all
players can use the total number on the two white dice to cross off a number in any row
on their sheet. This method should print the total of the white dice and ask each player if
they would like to use the total to cross of one of the numbers on the game board. If a
player wants to make a move, you should create a move, check if it’s valid and if it is
update the gameboard. For simplicity, you may loop through the players in the same order
each time. The method might make use of the following helper methods:
a. A getWhiteDiceTotal()method that returns the sum of the two white dice.
b. A checkValidMove(Player p, Move m) method that checks if the move the player
wants to make is valid and returns a boolean indicating whether it is or is not a valid
move. Remember a move is valid if it’s on the gameboard and if the number being
crossed off is further right then the last crossed off number AND the colour has
not been unlocked. Hint: the Player class keeps track of the last crossed of value
for each colour on their own gameboard.
c. A checkColourFinished(Player p, Char colour)method that returns true if the colour
the player has just crossed off a number in becomes finished. The method should
also update that colour to be locked for the game and output this to the console.
d. A checkGameFinished()method that checks if the game is finished. A game is
finished when all two of the colour rows have been locked out (by a player
crossing off the 12 or 2 at the far right of the score pad) or a player has passed 4
times (i.e. has -20 points).
e. A playColourDiceMoves(Player p) method which takes care of the moves on the colour dice.
Recall that the player who’s turned it is gets to choose a second number to cross off using
1 white die plus one colored die. This method should ask the player if they want to make
a move. If they do, it should ask which white dice they want to use and which colour they
want to cross out, create a move based on this, check if it’s valid and if so update the
gameboard. If they decide not to play, then you should give them -5 points. Again, you may
use the helper methods listed above.
f. A play() method which loops calling the rollDice(), printRolledDice(), playWhiteDiceMove(),
playColourDiceMove(), and checkGameFinished() methods until the game is done. Once the
game is done use a method (e.g. determineWinner()) to determine the winner.
4. A Driver class:
a. The main method in the driver class should ask the user how many players are playing the
game. Ensure this is between 2-5.
b. For each player ask the user the name and create the player.
c. Create a Qwixx game with the array of players and call the play() method.
*Note although you should check valid moves, you do not have to deal with input mismatch
errors.
Here is a sample output to illustrate the expected behavior of your program. Your formatting
may differ from the below but must demonstrate the behavior of the game and be easy to follow.
Note: user input is highlighted in yellow. Green is other points of interest in the program.
Please enter the number of players (2-5): 1
You must have between 2 and 5 players.
Please enter the number of players (2-5): 2
Please enter the name of player1: Nancy
Nancy’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: 2 3 4 5 6 7 8 9 10 11 12
Green: 12 11 10 9 8 7 6 5 4 3 2
Blue: 12 11 10 9 8 7 6 5 4 3 2
Please enter the name of player2: Marta
Marta’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: 2 3 4 5 6 7 8 9 10 11 12
Green: 12 11 10 9 8 7 6 5 4 3 2
Blue: 12 11 10 9 8 7 6 5 4 3 2
—– New Round —–
Red dice: 4 | Yellow dice: 4 | Green dice: 1 | Blue dice: 4 | White1 dice: 6 | White2 dice: 3 |
***** Move on white dice *****
The total for the white dice is 9
Nancy it’s your turn…
Nancy’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: 2 3 4 5 6 7 8 9 10 11 12
Green: 12 11 10 9 8 7 6 5 4 3 2
Blue: 12 11 10 9 8 7 6 5 4 3 2
Would you like to cross off a number on the game board using the white dice total? (anything other than ‘yes’ is taken
to mean no): yes
What colour would you like to cross out? (R = red, Y = yellow, G = green, B = Blue): G
Nancy’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: 2 3 4 5 6 7 8 9 10 11 12
Green: 12 11 10 X 8 7 6 5 4 3 2
Blue: 12 11 10 9 8 7 6 5 4 3 2
***** Move on white dice *****
The total for the white dice is 9
Marta it’s your turn…
Marta’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: 2 3 4 5 6 7 8 9 10 11 12
Green: 12 11 10 9 8 7 6 5 4 3 2
Blue: 12 11 10 9 8 7 6 5 4 3 2
Would you like to cross off a number on the game board using the white dice total? (anything other than ‘yes’ is taken
to mean no): yes
What colour would you like to cross out? (R = red, Y = yellow, G = green, B = Blue): B
Marta’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: 2 3 4 5 6 7 8 9 10 11 12
Green: 12 11 10 9 8 7 6 5 4 3 2
Blue: 12 11 10 X 8 7 6 5 4 3 2
Both players move on
the white dice.
Nancy it’s your turn…
***** Move on any colour dice *****
Nancy’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: 2 3 4 5 6 7 8 9 10 11 12
Green: 12 11 10 X 8 7 6 5 4 3 2
Blue: 12 11 10 9 8 7 6 5 4 3 2
Red dice: 4 | Yellow dice: 4 | Green dice: 1 | Blue dice: 4 | White1 dice: 6 | White2 dice: 3 |
Would you like to cross off a number on the game board using one of the coloured dice and a white dice? (anything
other than ‘yes’ is taken to mean no): yes
Which white dice would you like to you use? (White = 1, White2 = 2): 1
What colour would you like to cross out? (R = red, Y = yellow, G = green, B = Blue): B
Nancy’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: 2 3 4 5 6 7 8 9 10 11 12
Green: 12 11 10 X 8 7 6 5 4 3 2
Blue: 12 11 X 9 8 7 6 5 4 3 2
—– New Round —–
Red dice: 6 | Yellow dice: 1 | Green dice: 3 | Blue dice: 1 | White1 dice: 6 | White2 dice: 1 |
***** Move on white dice *****
The total for the white dice is 7
Nancy it’s your turn…
Nancy’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: 2 3 4 5 6 7 8 9 10 11 12
Green: 12 11 10 X 8 7 6 5 4 3 2
Blue: 12 11 X 9 8 7 6 5 4 3 2
Would you like to cross off a number on the game board using the white dice total? (anything other than ‘yes’ is taken
to mean no): yes
What colour would you like to cross out? (R = red, Y = yellow, G = green, B = Blue): G
Nancy’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: 2 3 4 5 6 7 8 9 10 11 12
Green: 12 11 10 X 8 X 6 5 4 3 2
Blue: 12 11 X 9 8 7 6 5 4 3 2
***** Move on white dice *****
The total for the white dice is 7
Marta it’s your turn…
Marta’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: 2 3 4 5 6 7 8 9 10 11 12
Green: 12 11 10 9 8 7 6 5 4 3 2
Blue: 12 11 10 X 8 7 6 5 4 3 2
Would you like to cross off a number on the game board using the white dice total? (anything other than ‘yes’ is taken
to mean no): yes
What colour would you like to cross out? (R = red, Y = yellow, G = green, B = Blue): B
Marta’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: 2 3 4 5 6 7 8 9 10 11 12
Green: 12 11 10 9 8 7 6 5 4 3 2
Blue: 12 11 10 X 8 X 6 5 4 3 2
Nancy’s turn, only she moves
on the coloured dice
Marta’s turn, now she moves
on the coloured dice
Marta it’s your turn…
***** Move on any colour dice *****
Marta’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: 2 3 4 5 6 7 8 9 10 11 12
Green: 12 11 10 9 8 7 6 5 4 3 2
Blue: 12 11 10 X 8 X 6 5 4 3 2
Red dice: 6 | Yellow dice: 1 | Green dice: 3 | Blue dice: 1 | White1 dice: 6 | White2 dice: 1 |
Would you like to cross off a number on the game board using one of the coloured dice and a white dice? (anything
other than ‘yes’ is taken to mean no): yes
Which white dice would you like to you use? (White = 1, White2 = 2): 2
What colour would you like to cross out? (R = red, Y = yellow, G = green, B = Blue): Y
Marta’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: X 3 4 5 6 7 8 9 10 11 12
Green: 12 11 10 9 8 7 6 5 4 3 2
Blue: 12 11 10 X 8 X 6 5 4 3 2
—– New Round —–
Red dice: 4 | Yellow dice: 2 | Green dice: 5 | Blue dice: 4 | White1 dice: 3 | White2 dice: 2 |
… (deleted some moves for brevity)
Nancy it’s your turn…
***** Move on any colour dice *****
Nancy’s Gameboard:
Red: 2 X 4 5 6 7 8 9 10 11 12
Yellow: 2 3 X 5 6 7 8 9 10 11 12
Green: 12 11 10 X 8 X 6 X 4 X 2
Blue: 12 11 X 9 8 7 6 5 4 3 2
Red dice: 1 | Yellow dice: 5 | Green dice: 5 | Blue dice: 5 | White1 dice: 2 | White2 dice: 1 |
Would you like to cross off a number on the game board using one of the coloured dice and a white dice? (anything
other than ‘yes’ is taken to mean no): yes
Which white dice would you like to you use? (White = 1, White2 = 2): 2
What colour would you like to cross out? (R = red, Y = yellow, G = green, B = Blue): G
Invalid move 3 is already crossed off in G
Would you like to cross off a number on the game board using one of the coloured dice and a white dice? (anything
other than ‘yes’ is taken to mean no): yes
Which white dice would you like to you use? (White = 1, White2 = 2): 1
What colour would you like to cross out? (R = red, Y = yellow, G = green, B = Blue): B
Nancy’s Gameboard:
Red: 2 X 4 5 6 7 8 9 10 11 12
Yellow: 2 3 X 5 6 7 8 9 10 11 12
Green: 12 11 10 X 8 X 6 X 4 X 2
Blue: 12 11 X 9 8 X 6 5 4 3 2
—– New Round —–
Red dice: 4 | Yellow dice: 1 | Green dice: 5 | Blue dice: 5 | White1 dice: 6 | White2 dice: 5 |
***** Move on white dice *****
The total for the white dice is 11
Nancy it’s your turn…
Nancy’s Gameboard:
Red: 2 X 4 5 6 7 8 9 10 11 12
Yellow: 2 3 X 5 6 7 8 9 10 11 12
Green: 12 11 10 X 8 X 6 X 4 X 2
Blue: 12 11 X 9 8 X 6 5 4 3 2
Would you like to cross off a number on the game board using the white dice total? (anything other than ‘yes’ is taken
to mean no): no
***** Move on white dice *****
The total for the white dice is 11
Marta it’s your turn…
Marta’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: X X 4 5 6 7 8 9 10 11 12
Green: 12 11 10 9 8 7 6 5 4 3 2
Blue: 12 11 10 X 8 X 6 X X X 2
Would you like to cross off a number on the game board using the white dice total? (anything other than ‘yes’ is taken
to mean no): no
Marta it’s your turn…
***** Move on any colour dice *****
Marta’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: X X 4 5 6 7 8 9 10 11 12
Green: 12 11 10 9 8 7 6 5 4 3 2
Blue: 12 11 10 X 8 X 6 X X X 2
Red dice: 4 | Yellow dice: 1 | Green dice: 5 | Blue dice: 5 | White1 dice: 6 | White2 dice: 5 |
Would you like to cross off a number on the game board using one of the coloured dice and a white dice? (anything
other than ‘yes’ is taken to mean no): yes
Which white dice would you like to you use? (White = 1, White2 = 2): 1
What colour would you like to cross out? (R = red, Y = yellow, G = green, B = Blue): G
Marta’s Gameboard:
Red: 2 3 4 5 6 7 8 9 10 11 12
Yellow: X X 4 5 6 7 8 9 10 11 12
Green: 12 X 10 9 8 7 6 5 4 3 2
Blue: 12 11 10 X 8 X 6 X X X 2
… (deleted some moves for brevity)
***** Move on any colour dice *****
Nancy’s Gameboard:
Red: 2 X 4 5 X 7 8 9 10 11 12
Yellow: 2 3 X 5 6 X X 9 10 11 12
Green: 12 11 10 X 8 X 6 X 4 X 2
Blue: 12 11 X 9 8 X X 5 4 3 2
Red dice: 1 | Yellow dice: 3 | Green dice: 4 | Blue dice: 5 | White1 dice: 2 | White2 dice: 4 |
Would you like to cross off a number on the game board using one of the coloured dice and a white dice? (anything
other than ‘yes’ is taken to mean no): no
For passing you get -5 points. You now have -5 points.
… (deleted some moves for brevity)
***** Move on white dice *****
The total for the white dice is 8
Nancy it’s your turn…
Don’t lose points for passing
on white dice moves
Nancy’s Gameboard:
Red: 2 X 4 5 X X X X 10 X 12
Yellow: 2 3 X 5 6 X X X 10 11 12
Green: 12 11 10 X 8 X 6 X 4 X 2
Blue: 12 11 X 9 8 X X X X 3 2
Would you like to cross off a number on the game board using the white dice total? (anything other than ‘yes’ is taken
to mean no): no
***** Move on white dice *****
The total for the white dice is 8
Marta it’s your turn…
Marta’s Gameboard:
Red: 2 3 X 5 6 7 8 9 X 11 12
Yellow: X X 4 5 6 X X 9 10 X 12
Green: 12 X 10 9 8 X X 5 4 X 2
Blue: 12 11 10 X 8 X 6 X X X 2
Would you like to cross off a number on the game board using the white dice total? (anything other than ‘yes’ is taken
to mean no): no
Marta it’s your turn…
***** Move on any colour dice *****
Marta’s Gameboard:
Red: 2 3 X 5 6 7 8 9 X 11 12
Yellow: X X 4 5 6 X X 9 10 X 12
Green: 12 X 10 9 8 X X 5 4 X 2
Blue: 12 11 10 X 8 X 6 X X X 2
Red dice: 1 | Yellow dice: 6 | Green dice: 2 | Blue dice: 6 | White1 dice: 6 | White2 dice: 2 |
Would you like to cross off a number on the game board using one of the coloured dice and a white dice? (anything
other than ‘yes’ is taken to mean no): yes
Which white dice would you like to you use? (White = 1, White2 = 2): 1
What colour would you like to cross out? (R = red, Y = yellow, G = green, B = Blue): Y
Marta’s Gameboard:
Red: 2 3 X 5 6 7 8 9 X 11 12
Yellow: X X 4 5 6 X X 9 10 X X
Green: 12 X 10 9 8 X X 5 4 X 2
Blue: 12 11 10 X 8 X 6 X X X 2
Yellow is no longer playable. Player Marta has locked it.
… (deleted some moves for brevity)
***** Move on any colour dice *****
Nancy’s Gameboard:
Red: 2 X 4 5 X X X X 10 X 12
Yellow: 2 3 X 5 6 X X X 10 11 12
Green: 12 11 10 X 8 X 6 X 4 X 2
Blue: 12 11 X 9 8 X X X X 3 2
Red dice: 5 | Yellow dice: 5 | Green dice: 5 | Blue dice: 2 | White1 dice: 2 | White2 dice: 4 |
Would you like to cross off a number on the game board using one of the coloured dice and a white dice? (anything
other than ‘yes’ is taken to mean no): no
For passing you get -5 points. You now have -15 points.
—– New Round —–
Red dice: 4 | Yellow dice: 4 | Green dice: 3 | Blue dice: 2 | White1 dice: 6 | White2 dice: 5 |
***** Move on white dice *****
The total for the white dice is 11
Nancy it’s your turn…
Nancy’s Gameboard:
Red: 2 X 4 5 X X X X 10 X 12
Yellow: 2 3 X 5 6 X X X 10 11 12
Green: 12 11 10 X 8 X 6 X 4 X 2
Blue: 12 11 X 9 8 X X X X 3 2
Would you like to cross off a number on the game board using the white dice total? (anything other than ‘yes’ is taken
to mean no): yes
What colour would you like to cross out? (R = red, Y = yellow, G = green, B = Blue): Y
Can’t move on Yellow, it’s locked.
Would you like to cross off a number on the game board using the white dice total? (anything other than ‘yes’ is taken
to mean no): no
… (deleted some moves for brevity)
Would you like to cross off a number on the game board using the white dice total? (anything other than ‘yes’ is taken
to mean no): no
Nancy it’s your turn…
***** Move on any colour dice *****
Nancy’s Gameboard:
Red: 2 X 4 5 X X X X 10 X 12
Yellow: 2 3 X 5 6 X X X 10 11 12
Green: 12 11 10 X 8 X 6 X 4 X 2
Blue: 12 11 X 9 8 X X X X 3 2
Red dice: 4 | Yellow dice: 3 | Green dice: 2 | Blue dice: 4 | White1 dice: 4 | White2 dice: 3 |
Would you like to cross off a number on the game board using one of the coloured dice and a white dice? (anything
other than ‘yes’ is taken to mean no): no
For passing you get -5 points. You now have -20 points.
Nancy has a total of: 36 points.
Marta has a total of: 47 points.
That’s all folks! Marta wins the game!
Submitting Assignment 4
Please check your course Moodle webpage on how to submit the assignment.
Evaluation Criteria for Assignment 4 (20 points)
Source Code
Comments for all 3 questions (2 pts.)
Description of the program (authors, date, purpose) 1 pts.
Description of variables and constants 0.5 pt.
Description of the algorithm 0.5 pts.
Programming Style for all 3 questions (2 pts.)
Use of significant names for identifiers 1 pt.
Indentation and readability 1 pt.
Helper Classes (5 points)
Proper constructors 1 pt.
Proper implementation of the toString() method 1 pt.
Proper access modifiers for the different methods 1 pt.
Proper implementation of helper methods 2 pt.
Game Class & Driver (11 points)
Prompting user/reading player data in driver class 1 pt.
Correct implementation of white dice algorithm 2 pts.
Correct implementation of colour dice algorithm 2 pts.
Play algorithm 3 pts.
Proper error handling for user input 1 pt.
Computing scores correctly 1 pt.
Detecting and displaying winners 1 pt.
TOTAL 20 pts.
