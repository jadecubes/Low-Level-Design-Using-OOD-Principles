# Sequence Diagram for the Restaurant Management System
Sequence diagrams are a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for our restaurant management system. In this lesson, we will create sequence diagrams for the following two interactions:

- Modifying an order

- Sequence challenge: The guest pays for the order.

## Modifying an order
The sequence diagram for modifying an order should have the following actors and objects that will interact with each other:

Actor: Waiter

Objects: Order, Kitchen, and bill
```
Note: Let us assume that the meal is not yet prepared.
```
Here’re the steps in the order modification interaction:

1. The waiter initiates the process by adding a meal item to the order.

2. The order is then updated. The updated order is sent to the kitchen for preparation.

3. The order is started to be prepared in the kitchen.

4. Simultaneously, the waiter updates the bill, as per the modified order.

5. After that, bill is updated.

6. The kitchen sends a message about the order indicating that it is prepared.

7. The order status is updated to "prepared."

8. The waiter serves the order.

Based on the order above, the sequence diagram of modifying an order in a restaurant management system is given below:

[The sequence diagram for modifying an order]

## Sequence challenge: The guest pays for the order

[The sequence diagram for order payment]

[Flow]

[Answer]
