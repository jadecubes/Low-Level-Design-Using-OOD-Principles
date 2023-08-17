# Sequence Diagram for the Amazon Online Shopping System

Sequence diagrams are a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for the Amazon online shopping system. For this lesson, we’ll create sequence diagrams for the following two interactions:

- Checkout and payment: The user checks out and pays for their order using a credit card.

- Sequence challenge: The user searches and adds an item to the shopping cart.

## Checkout and payment
The sequence diagram for order checkout and payment should have the following actors and objects that will interact with each other:

- Actor: Customer

- Objects: ShoppingCart, Order, Item, and Payment

Here’re the steps in the order checkout and payment interaction:

1. The customer requests the shopping cart items and amount.

2. The customer then places the order for the requested items.

3. The items are verified for availability.

4. If the item quantity is less than the available count:

    I. The order status is updated.

    II. The customer is informed that the order is ready for payment.

    III. The customer initiates a payment against the order amount using their card.

    IV. The payment is processed.

    V. The customer is informed of the updated payment status.

5. Else if the item quantity is greater than the available count:

    I. The item in the order is unavailable.

    II. The customer receives an error for the unavailable item.

Based on the order above, the sequence diagram below represents the order checkout and payment process in an online shopping system.

## Sequence challenge: Search and add items to the cart

[The sequence diagram for search and add items to the cart](./seq1.png)

[challenge](./seq2.png)

[flow](./flow.png)

[answer](./answer.png)
