# Class Diagram for the Online Blackjack Game
We’ll create the class diagram for the Blackjack game. In the class diagram, we will first design the classes, and then identify the relationship between classes according to the requirements for the Blackjack game problem.

## Components of Blackjack
In this section, we’ll define the classes for the Blackjack game. As mentioned earlier, we are following the bottom-up approach to designing a class diagram for the Blackjack game.

### Card
Card belongs to a suit and has a face value. The face value of the card is according to the card number. For example, if we have a number card 5, its face value is also 5. The face value for the King, Queen, and Jack is 10, and 1 or 11 for the Ace, depending on the situation.

[The class diagram of the Card class]

```
R3: Every card has points associated with it. The criteria to calculate the face value of the card is as follows:

Card	                          Face value
Ace	                              1 or 11
From 2 to 10	                   Equals the card number
Face cards (King, Queen, Jack)     	10
```
### Deck
Deck has 52 cards of four suits, and one suit contains nine number cards (2–10) and four face cards (King, Queen, Jack, and Ace). The Deck class contains a list of cards where the top card is in the first index.

[The class diagram of the Deck class]

```
R2: The deck will consist of 52 cards in four suits, where each suit contains 13 cards: Ace, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, Jack, Queen, and King.
```

### Shoe
Shoe is a device to hold multiple Deck, and it has a shuffle operation.

[The class diagram of the Shoe class]

```
R1: The Blackjack game contains the shoe of cards which contains one or more decks of cards in it.
```

### Hand
The Hand class represents a Blackjack hand used in this game which can contain multiple cards.

[The class diagram of the Hand class]

```
R8: The player can draw the additional card if their hand has less than 21 points.

R9: The dealer can draw an additional card if their hand is less than 17.

R10: If a player or the dealer’s hand is more than 21, they bust and lose the game.
```

### Players
Player is an abstract class. There are two types of players: BlackjackPlayer and Dealer. These classes can be derived from the Player class.

BlackjackPlayer: They place the first wager and update the stake with winning and losing sums. They can choose between hit and stand options.

Dealer: They are primarily in charge of dealing cards and following the Blackjack rules.

[The class diagram of Player and its derived classes]
```
R4: There can be two types of users that can play the Blackjack game, i.e., dealer and the player.
```

### Blackjack controller
### Blackjack game view
### Blackjack game
### Enumerations and custom data types
## Relationship between the classes
### Association
### Aggregation
### Composition
### Inheritance
## Class diagram for the Blackjack game
## Design pattern
