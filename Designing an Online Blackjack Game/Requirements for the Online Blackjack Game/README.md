# Requirements for the Online Blackjack Game
In this lesson, we’ll list the requirements of the online Blackjack game. This is a very crucial step since requirements define the scope of a problem, so getting them right from the interviewer and understanding them well will make the design of the rest of the system smooth and easy.

We’ll use the notational convention to identify each requirement with a unique label "Rn", where "R" is short for Requirement and "n" is a natural number.

## Requirement collection
The requirements for the Blackjack design problem are defined below:

R1: The Blackjack game contains the shoe of cards which contains one or more decks of cards in it.

R2: The deck will consist of 52 cards in four suits, where each suit contains 13 cards: The ace, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, Jack, Queen, and King.

R3: Every card has points associated with it. The criteria to calculate the face value of the card is as follows:

```
Card                       Face value

Ace                         1 or 11

From 2 to 10               Equals the card number

Face cards
(King, Queen, and Jack)       10
```

R4: There can be two types of users that can play the Blackjack game, i.e., the dealer and the player.

R5: The player places a bet at the start of the game.

R6: The dealer will deal two cards to themselves and two to each player at the start of the game.

R7: The player will have both cards exposed, while the dealer has one card facing up and the other card down.

[Game](./layout.png)

R8: The player can hit (Draw an additional card.)  if their hand has less than 21 points.

R9: The dealer can hit if their hand is less than 17.

R10: If a player or the dealer’s hand is more than 21, they bust and lose the game.

R11: The player can decide to not get a further card by standing pat.

R12: At the end, if the points of the player are more than that of the dealer but less than 21, then they win the game and get 100 percent profit.

R13: If a player gets 21 points by winning an ace and a face card or 10, then they are called a Blackjack and get 150 percent profit.

R14: If the player and the dealer have the same points at the end of the game, the player can take their bet money back or can replay the game.

R15: If the player left a game in the middle of the game, the dealer will win the game.

We've identified our requirements for the problem, and in the next lesson, we will define different use cases for the online Blackjack game design.
