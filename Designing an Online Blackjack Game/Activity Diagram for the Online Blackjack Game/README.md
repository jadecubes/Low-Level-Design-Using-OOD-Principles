# Activity Diagram for the Online Blackjack Game
Activity diagrams are a great way to visualize the flow of messages from one activity to the other in the system. There can be different activity diagrams that we can create for our Blackjack game. In this lesson, we will create an activity diagram for the steps to play Blackjack.

## Blackjack gameplay
The following are the states and actions that will be involved in this activity diagram.

### States
Initial state: The player places the bets and the dealer deals the cards among themselves and the player.

Final state: There are four final states present in this activity diagram, shown below:

- The player wins with 3:2 of the bet.

- The player wins with an equal bet.

- The match is tied.

- The player loses.

### Actions
- The player places the bet.

- The dealer deals two cards among themselves and two for the player.

- If the total of the player's card is 21:

    - It is a Blackjack, and the player will win and get 150% of the bet.

- If the total is less than 21:

    - The player will lose, and the dealer will collect the bet.

- If the total of the player card is less than 21:

    - The player will have two options to either "Stand" or "Hit."

- If a player decides to "Hit":

    - The player gets another card from the dealer, and then we will check the player's card total again.

- If the player decides to "Stand":

    - The dealer's card total will be checked.

- If it is less than 17:

    - The dealer will get another card until its card total is more than 16.

- When the total is more than 16, we will compare the totals of the player and dealer’s cards.

- Whoever gets more wins, and if both cards' total is the same, it will be a tie.

Based on the order above, the activity diagram of a Blackjack game is given below:

[The activity diagram for the Blackjack game play](./activity.png)

We've looked at the activity diagrams of the Blackjack game. In the next lesson, we will present the code for our designed classes in some of the most popular languages.
