# Sequence Diagram for the Hotel Management System

Sequence diagrams are a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for our hotel management system. In this lesson, we will create sequence diagrams for the following two interactions:

- Book a room: The guest books a hotel room online.

- Sequence challenge: The guest checks out of their room at the reception.


## Book a room
The sequence diagram for the room booking should have the following actors and objects that will interact with each other:

- Actor: Guest

- Objects: Catalog, Booking, Room, and Payment

- System

Here’re the steps in the book room interaction:

1. The guest searches for a room based on some price and style.

2. The catalog returns a list of rooms.

3. The guest selects a room they wish to book.

4. If the room is available:

    I. The guest creates a booking for the room.

    II. The booking fetches the booking price for the room.

    III. The guest is informed that the booking is ready for payment.

    IV. The guest initiates a payment against the booking price.

    V. The payment is processed, and the guest is informed of the status.

    VI. If the payment is successful:

        i. The guest is informed that the payment has succeeded.

        ii. The system is informed that payment is complete.

        iii. The system updates the room status to reserved.

    VII. Else if the payment is unsuccessful:

        i. .The guest is informed that the payment has failed.

5. Else if the room is unavailable:

    I. The system informs the guest that the room is unavailable.

Based on the order above, the sequence diagram of booking a room in a hotel management system is given below:

[The sequence diagram for online room booking](./seq1.png)

## Sequence challenge: Check out
[checkout challenge](./checkout.png)

[checkout flow](./sequence.png)

[answer](./checkoutanswer.png)

