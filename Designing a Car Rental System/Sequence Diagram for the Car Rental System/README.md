# Sequence Diagram for the Car Rental System
Sequence diagrams are a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for our car rental system. For the sake of this lesson, we will create sequence diagrams for the following two interactions:

- Vehicle reservation: The member reserves a vehicle.

- Sequence challenge: The member cancels their reservation.

## Vehicle reservation
The sequence diagram for vehicle reservation should have the following actors and objects that will interact with each other:

- Actor: Member

- Objects: Catalog, Reservation, and Payment

- System

Here are the steps in the reserve vehicle interaction:

1. The member searches for a vehicle.

2. If the vehicle is available:

    I. The catalog returns a list of available vehicles.

    II. The member selects a vehicle to reserve.

    III. The system creates a reservation against the vehicle.

    IV. The reservation fee is sent to the system.

    V. The system requests payment from the member.

    VI. The member initiates payment against the reservation fee.

    VII. The payment is processed.

    VIII. If the payment is successful:

        i. The system is informed that the payment is completed.

        ii. The system updates the reservation status to “confirmed”.

        iii. The member is informed that the vehicle is reserved.

    IX. Else if the payment is unsuccessful:

        i. The system is informed that the payment has failed.

        ii. The system deleted the reservation.

        iii. The system informs the member that the reservation is unsuccessful.

3. Else, if the vehicle is unavailable:

    I. Members are notified that no vehicles are available.

Based on the order above, the sequence diagram of a vehicle reservation in a car rental system is provided below:

[The sequence diagram for vehicle reservation]

## Sequence challenge: Cancel reservation

[The sequence diagram for cancel reservation]
