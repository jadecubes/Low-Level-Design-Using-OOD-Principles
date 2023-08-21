# Sequence Diagram for the Online Stock Brokerage System
Sequence diagrams are a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for the online stock brokerage system. In this lesson, we will create a sequence diagram for the following interaction:

- Selling a stock: A member wants to sell a stock to the stock market.


## Selling a stock
The sequence diagram for selling a stock should have the following actors and objects that will interact with each other:

- Actor: Member

- Objects: StockInventory and StockExchange

Here are the steps involved in selling a stock:

1. A member selects a stock and its selling parameters: order type, stock quantity, time price limit, and time enforcement.

2. If the stock is available in the stock inventory:

    I. The stock quantity is deducted from the stock inventory.

    II. The stock order details will be sent to the stock exchange.

    III. The stock exchange acknowledges it.

    IV. The member will be notified about the order placement.

3. Else if, enough stock is not available:

    I. The member will be notified about stock unavailability.

Based on the order above, the sequence diagram for selling a stock in an online stock brokerage system is provided below.

[The sequence diagram for selling a stock](./sequence.png)
