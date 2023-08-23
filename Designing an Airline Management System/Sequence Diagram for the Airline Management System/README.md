# Sequence Diagram for the Airline Management System
Sequence diagrams are a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for our airline management system. In this lesson, we will create sequence diagrams for the following two interactions:

- Reserve a flight: The customer reserves a flight online.

- Sequence challenge: The customer cancels a reservation.

## Reserve a flight
The sequence diagram for reserving a flight should have the following actors and objects that will interact with each other:

Actor: Customer

Objects: SearchCatalog, FlightReservation, FlightSeat, and Payment

System

Here’re the steps in the reserve flight interaction:

1. The customer searches for flights flying from an airport on a particular date.

2. The catalog returns a list of flights that satisfy the search query.

3. The customer selects a flight.

4. If seats are available:

    I. The system requests the customer to select seats.

    II. The customer selects a seat.

    III. The system requests to add passenger details.

    IV. The customer adds passenger details.

    V. The system creates a reservation for the customer.

    VI. Payment is requested against the reservation.

    VII. The customer initiates a transaction, and the payment is processed.

    VIII. If the payment is successful:

        i. The customer and system are informed that the payment is successful.

        ii. The system updates the seat status to booked.

        iii. The system updates the reservation status to confirmed.

        iv. The reservation details are sent to the customer.

    IV. Else, if the payment is unsuccessful:

        i. The customer is informed that the payment has failed.

5. Else, if seats are unavailable:

    I. The customer is informed that no seats are available.
```
Note: We assume that the customer performs a valid search that will result in a list of flights.
```
Based on the order above, the sequence diagram for reserving a flight in the airline management system is given below.

[The sequence diagram for the reserve a flight interaction]

## Sequence challenge: Cancel a reservation

[challenge]

[flow]

[answer]
