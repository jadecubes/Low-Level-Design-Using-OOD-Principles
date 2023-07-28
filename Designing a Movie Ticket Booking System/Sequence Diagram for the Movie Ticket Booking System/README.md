# Sequence Diagram for the Movie Ticket Booking System

A sequence diagram is a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for our movie ticket booking system. In this lesson, we will create sequence diagrams for the following three interactions:

- Create a booking: The customer creates a booking for a show.

- Payment for the booking: The customer pays for the booking.

- Sequence challenge: The customer cancels their booking.

## Create a booking
The sequence diagram for creating a booking should have the following actors and objects that will interact with each other:

- Actor: Customer

- Objects: Catalog, Movie, and ShowTime

- System

Here’re the steps of the interaction to create a booking interaction:

1. The customer searches for a movie from the catalog.

2. The catalog returns the required movie.

3. They request show times for the movie they wanted to book.

4. The available show times for the movie are returned.

5. The customer requests available seats for the show.

6. If seats are available:

    I. The customer receives a list of available seats.

    II. The customer books their desired seats using the system.

    III. The seat status is set to book.

    IV. The system requests payment against the booked seats from the customer.

7. Else if the seats are not available:

    I. The customer is informed that no seats are available.

Based on the order above, the sequence diagram for creating a booking in the movie ticket booking system is given below.

[The sequence diagram to create a booking](./createbooking.png)

## Payment of a booking
The sequence diagram for payment of a booking should have the following actors and objects that will interact with each other:

- Actor: Customer

- Object: Payment, Seat

- System

Here are the steps in the payment of a booking interaction:

1. The customer initiates a payment against the booking fee.

2. The payment processes the payment and informs the system.

3. If the payment is complete:

    I. The payment informs the customer about the completed payment.

    II. The system creates an object for the booking.

    III. The booking status is updated and the system is informed.

    IV. The system sends a notification to the customer containing the booking information.

4. Else if the payment is declined:

    I. The payment informs the customer about the declined payment.

    II. The system requests to revert the seat status.

    III. The seat status is updated to available and returned to the system.

    IV. The system informs the customer that the booking is declined.

Based on the order above, the sequence diagram for payment of a booking in the movie ticket booking system is given below.

[The sequence diagram for the payment of a booking interaction](./bookingpayment.png)

## Sequence challenge: Cancel booking
You will complete a sequence diagram for a booking canceled by the customer. A skeleton of the cancel sequence diagram is given below:

[The sequence diagram for canceling the booking](./cancelbooking.png)

[Sequence](./seq.png)

[Answer](./cancelbookinganswer.png)

