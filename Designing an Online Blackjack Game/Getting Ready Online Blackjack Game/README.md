# Getting Ready: Online Blackjack Game
## Problem definition
Blackjack is one of the most played games in casinos. In this game, several players play against the dealer. The objective of the game is to get closer to 21 than the dealer without exceeding the 21 points. This game is played with a deck of cards. Each card has a specific value associated with it, and these values are compared. The value of an ace card can be 1 or 11 points while cards of 10, Jack, Queen, and King value 10 points. Whereas, cards 2-9 have the same values as the number written on them. Hence, the player having one ace and a face card (King, Queen, or Jack card.) or a 10 card has 21 points. This is called Blackjack.

At the start of the game, a bet is placed by a player, and then the dealer will create hands (Each player and the dealer get two cards each.). All players have both cards exposed while the dealer has one card exposed and one card hidden. Now, both the dealer and the player can hit (Draw an additional card.) a card and ensure that they should not get over 21. Anyone exceeding 21 points, busts and loses the bet. The player can stand pat (Stop taking cards) at any time. When a player stops taking cards, if the player has more points than the dealer but less than 22, they win the bet.

The following slide represents how to play Blackjack:

[Game](./game)

## Expectations from the interviewee
There are several components in a Blackjack game, each with specific constraints and requirements placed on them. The following provides an overview of some of the main expectations that the interviewer will want to hear you discuss in more detail during the interview.

### Players in the game
To get a better understanding of the game and the players of the game, you may ask the interviewer the following set of questions:

1. How many players can play Blackjack?

2. Can players play the game against each other?

### Point dynamics
The rules related to the number of points also need to be clarified by the interviewer, therefore, you may ask questions listed below:

1. Upto how many points can the player or the dealer hit the card?

2. What will happen if the dealer and the player both get the same points?

### Card limit
The interviewer would expect you to ask a question related to the maximum number of cards the player can have. Therefore, you may ask a question listed below:

1. Is there a limit on the number of cards the player take?

## Design approach
We are going to design this Blackjack game system using the bottom-up design approach. For this purpose, we will follow the steps below:

- Identify and design the smallest components first–the card, and player.

- Use these small components to design bigger components, for example, the deck and controller.

- Repeat the steps above until we design the whole Blackjack game.

## Design patterns
It is always a good practice to discuss the design patterns that the online Blackjack game falls under, during the interview. Stating the design patterns will give the interviewer a positive impression and shows that the interviewee is well-versed in the advanced concepts of object-oriented design.

The following design patterns are used to design the online Blackjack game:

- Iterator design pattern

- State design pattern

Let's explore the requirements of the online Blackjack game in the next lesson.
