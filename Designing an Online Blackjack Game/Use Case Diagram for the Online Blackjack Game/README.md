# Use Case Diagram for the Online Blackjack Game
Let's build the use case diagram of the Blackjack game and understand the relationship between its different components.

First, we’ll define the different elements of our Blackjack game, followed by the complete use case diagram of the system.

## System
Our system is a "Blackjack game."

## Actors
Now, we’ll define the main actors of our Blackjack game.

### Primary actors
- Player: This actor is the main player of the game. This actor plays the game, which includes placing a bet, hit or stand, or quitting the game. This can also create, edit, or update its account.

### Secondary actors
- Dealer: This is the secondary actor of the game, who manages the Blackjack table, dealing cards, and completing the payout of earnings. This actor can also manage the accounts and memberships of members.

## Use cases
In this section, we will define the use cases for the Blackjack game. We have listed the use cases according to their respective interactions with a particular actor.
```
Note: You will see some use cases occurring multiple times because they are shared among different actors in the system.
```
### Player
- Join a game: To join a new Blackjack game

- Place bet: To place a bet for the game

- View open games: To view open games that are waiting for the player to start

- Resigns a game: To leave a game in the middle of the game

- Hit: To request an extra card from the dealer

- Stand: To hold your cards and skip your turn

- Create account: To create a new account in the Blackjack game

- Update account: To update account information or password in the Blackjack game

- Reset password: To update the account password in the Blackjack game

- Cancel membership: To cancel membership in the Blackjack game

- Login/Logout: To log in and out of the Blackjack game

### Dealer
- Create a new game: To start a new Blackjack game

- View open games: To view open games that are waiting for the player to start

- Create hands: To give two cards to the player and two cards to the dealer

- Draw card: To add cards from the deck to the player and dealer's hand

- Collect or payout: To give or take money after the game ends, depending upon the game's result

- Block member: To block any member to ensure they can't play the game

- Create account: To create a new account in the Blackjack game

- Update account: To update account information or password in the Blackjack game

- Reset password: To update the account password in the Blackjack game

- Cancel membership: To cancel membership in the Blackjack game

- Login/Logout: To log in and out of the Blackjack game

## Relationships
This section describes the relationships between and among actors and their use cases.

### Associations
The below table shows the association relationship between actors and their use cases.

```
Player                  Dealer

Join a game           Create a new game

Place bet              View open games

View open games        Create hands

Resigns a game           Draw card

Hit                    Collect or payout

Stand                   Block member

Create account          Create account

Update account          Update account

Reset password          Reset password

Cancel membership       Cancel membership

Login/Logout            Login/Logout

```

### Include
- The "Create hand" use case and the "Hit" use case has an include relationship with the "Draw card" use case because, at the start of the game, we draw cards to create hands, and in the middle, we draw cards when the player chooses to "Hit."

- Whenever a player chooses to "Stand," their turn is skipped. Then, if the dealer card total is more than 16, the dealer and player's card total is compared with each other. According to the result of the game, the dealer either collects or pays the money. So the "Stand" use case has an include relationship with the "Collect or payout" use case.

### Extend
- The "Cancel membership" use case and "Block member" use case have an extend relationship with the "Modify member" use case, because whenever we cancel someone's membership or block someone, we modify the member status.

- Whenever the account password is changed, the account is updated. Hence, the "Reset password" use case has an extend relationship with the "Update account" use case.

## Use case diagram

[The use case diagram for the Blackjack game](./usecasediagram.png)

In the next lesson, we will discuss the class diagram with a detailed explanation of all classes and their relationship with each other.
