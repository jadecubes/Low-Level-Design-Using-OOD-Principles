# Use Case Diagram for the Vending Machine
Let’s build the use case diagram for the vending machine and understand the relationship between its different components.

First, we’ll define the different elements of our vending machine, followed by the complete use case diagram of the system.

## System
Our system is a "Vending machine."

## Actors
Now, we’ll define the main actors of our vending machine.

### Primary actors
- Customer: This actor can view, select and take products, insert money, and take out change from the machine.

- Operator: This actor can do everything a "Customer" can do. It can also add or remove products and remove cash from the machine.

### Secondary actors
- System: This actor can search for the selected product and dispatch it after validating money.

## Use cases
In this section, we will define the use cases for the vending machine. We have listed down the use cases according to their respective interactions with a particular actor.
```
Note: You will see some use cases occurring multiple times because they are shared among different actors in the system.
```
### Customer
- View products: To view all available products in the vending machine

- Select products: To select a product to buy from the vending machine

- Insert money: To insert money to buy products from the vending machine

- Take product: To take out products from the vending machine

- Take change: To take out change from the vending machine

### Operator
- Add product: To add new products inside the vending machine

- Remove product: To remove products from the vending machine

- Cash remove: To remove collected cash from the vending machine

### System
- Search product: To search for the selected product in the machine to dispatch it

- Validate money: To validate that the money is legal

- Dispense product: To dispense selected products so customers can take them

- Return change: To return the change to the customer if the inserted amount is less than the purchased product price

## Relationships
This section describes the relationships between and among actors and their use cases.

### Generalization
The customer and operator are two actors who interact with the vending machine. The consumer can only engage with the system to purchase a product. An operator can execute all the duties that a customer can, along with certain administrative responsibilities. Therefore, the “Operator” actor has a generalization relationship with the “Customer” actor.
### Associations
The below table shows the association relationship between actors and their use cases.
```
Customer                        Operator                    System

View products                  Add product               Search product

Select products               Remove product             Dispense product

Insert money                    Cash remove              Validate money

Take product                   View products              Return change

Take change                   Select products

                               Insert money

                               Take product

                                Take change
```
### Include
- When a customer selects a product to buy, the system then searches for the product’s location and dispatches it. Therefore, the “Select products” use case has an include relationship with the “Search product” use case.

- When a customer selects a product to buy, the system then validates the money that the customer inserted and then dispenses the product. Therefore, the “Validate money” use case has an include relationship with the “Dispense product” use case.
### Extend
When a customer selects a product to buy, the system then validates the money that the customer inserted and then returns the change if the amount is greater than the price of the purchased product. Therefore, the “Return change” use case has an extend relationship with the “Validate money” use case.

## Use case diagram

[The use case diagram of the vending machine]

In the next lesson, we’ll discuss the class diagram with a detailed explanation of all classes and their relationship with each other.
