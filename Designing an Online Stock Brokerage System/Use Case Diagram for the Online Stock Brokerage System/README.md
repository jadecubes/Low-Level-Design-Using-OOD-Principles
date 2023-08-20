# Use Case Diagram for the Online Stock Brokerage System
Let's build the use case diagram of the online stock brokerage system and understand the relationship between its different components.

First, we’ll define the different elements of our online stock brokerage, followed by the complete use case diagram of the system.

## System
Our system is a "stock brokerage."

## Actors
Now, we’ll define the main actors of our online stock brokerage system.

### Primary actors
- Member: This actor can search the stock, place an order to buy or sell stocks, create an account, start a membership, add stocks to the wishlist, add buying and selling limits as well as perform transactions in three ways. It can also create and update accounts, perform login and logout, and cancel membership.

### Secondary actors
- Admin: This can create and update accounts, perform login and logout, cancel membership, and block or unblock members.

- System: This is responsible for notifying the member about the order status and transactions. It can also fetch stock quotes from the stock exchange.

## Use cases
In this section, we will define the use cases for the online stock brokerage system. We have listed down the use cases according to their respective interactions with a particular actor.
```
Note: You will see some use cases occurring multiple times, because they are shared among different actors in the system.
```

### Member
- Create account: To create a new account in the online stock brokerage system

- Cancel membership: To cancel an old online stock brokerage system membership

- Update account: To update account details in the online stock brokerage system

- Login/Logout: To log in and out of the online stock brokerage system account

- Cancel order: To cancel any buying or selling stock order in the online stock brokerage system

- View stock positions: To view live positions and pricing of stocks in the stock exchange

- Add stock to wishlist: To add a stock to a member's wishlist

- Create/update wishlist: To add and remove stocks from the existing or new wishlist

- Search stock inventory: To search for a stock in the stock inventory

- Place order: To place an order to buy or sell the order

- Deposit/withdraw money: To deposit or withdraw money to and from your account

### Admin
- Create account: To create a new account in the online stock brokerage system

- Cancel membership: To cancel an old online stock brokerage system membership

- Update account: To update account details in the online stock brokerage system

- Login/Logout: To log in and out of the online stock brokerage system account

- Block/unblock member: To block and unblock a member from the online stock brokerage system

### System
- Fetch stocks quotes from stock exchange: To fetch stock price from the stock inventory in the online stock brokerage system

- Send order status change notification: To notify about the change in the order status in the online stock brokerage system

- Send deposit/withdrawal status change notification: To notify about the deposit and withdrawal of money

## Relationships
This section describes the relationships between and among actors and their use cases.


### Generalization
- The "Electronic bank transfer," "Wire transfer," and "Check Transfer" use cases are used for transactions. Hence, they have a generalization relationship with the "Transaction" use case.

- When an order is placed, it could be the market, limit, stop-loss or stop-limit order. Therefore, the "Place market order," "Place limit order," "Place stop-limit order," and "Place stop-loss order" use cases have a generalization relationship with the "Place order" use case.

### Associations
The below table shows the association relationship between actors and their use cases.

```
Member                                     Admin                                      System

Create account                            Create account             Fetch stocks quotes from stock exchange

Cancel membership                         Cancel membership          Send order status change notification

Update account                            Update account              Send deposit/withdrawal status change notification

Login/Logout                              Login/Logout

Cancel order                              Block/unblock member

View stock positions

Add stock to wishlist

Create/update wishlist

Search stock inventory

Place order

Deposit/withdraw money
```
### Include
The "Deposit/withdraw money" use case has an include relationship with the "Transaction" use case, since a money transaction takes place when money is deposited or withdrawn.

## Use case diagram
Here's the use case diagram of the online stock brokerage system:

[The use case diagram of the online stock brokerage system]
