# Activity Diagram for the Online Stock Brokerage System
Activity diagrams are a great way to visualize the flow of messages from one activity to the other in the system. There can be different activity diagrams that we can create for our online stock brokerage system. In this lesson, we will create an activity diagram for the following activity.

## Buying a stock
The states and actions involved in this activity diagram are listed below.

### States
Initial state: The member selects a stock to buy.

Final state: There are two final states present in this activity diagram, shown below:

- The member successfully buys a stock from the online stock brokerage system.

- Due to the unavailability of a sufficient deposit, members aren't able to buy the stocks.

### Actions
The member selects the stock to buy, order type, stock quantity, time price limit, and time enforcement. Then, the system will check if the member has a sufficient deposit in the account. If available, the system then deducts funds from the account, sends order details to the stock exchange, and notifies the member about order success when it receives acknowledgment from the stock exchange.

Based on the order above, the activity diagram for buying a stock at the online stock brokerage system is provided below:

[The activity diagram for buying a stock](./activity.png)

We've looked at the activity diagram of our online stock brokerage system. In the next lesson, we will present the code for our designed classes in some of the most popular languages.
