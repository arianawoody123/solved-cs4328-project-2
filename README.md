Download Link: https://assignmentchef.com/product/solved-cs4328-project-2
<br>
5/5 - (2 votes)

<span style="font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen-Sans, Ubuntu, Cantarell, 'Helvetica Neue', sans-serif;">1 Overview</span>

In this project, we are going to build “Card Matching Fight”. Card matching fight is a simple card game with one dealer, 3 players, and a single deck of cards. The game is composed of three rounds. At the beginning of each round, the dealer shuffles the cards, deals the first three cards and waits for the round to finish, before repeating the same process for the next round. A winner in a round is the first player to get a match (i.e., two cards of equal rank). In each round, a different player is given the privilege to start.

Initially, the dealer shuffles the deck of cards and hands each player a single card in a round robin fashion (say starting from player 1 in round 1). Once the dealer is done handling the cards, the dealer places the remaining deck of cards on the table and the first round begins. Each player (starting from player 1), draws a card from the deck and compares it to the card he/she has. If they match, the player shows the hand, declares him/herself as a winner and the round completes. Otherwise, the player will discard one card (at random) by placing it at the end of the deck of cards on the table and the next player proceeds. Once a round ends, the dealer will shuffle the deck and hands a card to each player. In the second round, the second player starts drawing a card from the deck. In the third round, the third player starts drawing a card from the deck.

2 Implementation

This project is to implemented in C using POSIX threads. You can check:

<pre>https://computing.llnl.gov/tutorials/pthreads</pre>

for a tutorial on the POSIX thread library. The main function should create a thread for the dealer and 3 threads for the players. Notice that we want to keep the threads synchronized and to protect any shared objects. Also, when a player wins, he/she needs to inform other players that the round is complete. Each thread should print a message when it finishes (e.g., “Player 1 wins and round completed”, “Player 2 round completed”, etc. The main program takes a seed as an argument for the random number generation (which will be used in shuffling and in discarding cards ).

3 The Output

The dealer and the players will write into a log file each action they talk. The log file should be able to describe exactly what is happening at each step. The log file should look something like this:

PLAYER 1: hand 5PLAYER 1: draws 7PLAYER 1: discards 7PLAYER 1: hand 5DECK: contents of the deck, separated by spaces (e.g., 1 2 3)

Page 2 of 3

CS4328 (Mina Guirguis ): Project #2

4 SUBMISSION

The final messages for a round should look something like:

PLAYER 2: hand 3 PLAYER 2: draws 3 PLAYER 2: hand 3 3 PLAYER 2: winsPLAYER 2: round completed PLAYER 1: round completed PLAYER 3: round completed DEALER: shuffle

The output of the program to the screen (not in the log file) should indicate the hand for each player, the status (win, lost) and the remaining deck of cards:

HAND card1 card2WIN yes (or no)DECK contents of the deck, separated by spaces (e.g., 1 2 3)

The hand of the winner would show two cards (the winning matching cards) and the hands of the other players would show only one card. A single run of the program should have 3 rounds with 3 winners.

4 Submission

Submission will be done through TRACS. Submissions will include the code, a report containing a brief overview of the design and implementation, the results of 5 independent runs of the program with different seeds, and instructions on to how to compile and run the simulator. Please upload a single zip file including all your files.