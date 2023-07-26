# Getting Ready: Movie Ticket Booking System
## Problem definition
The movie ticket booking system is a system that allows customers to book shows for their favorite movies. The booking system has information on all cinemas present in different cities and the hall information for each cinema. There are numerous movies stored in the system database. Each movie can have multiple shows playing in a particular cinema. The customer can search and select a movie for which they wish to book a show. The system displays a seating layout that identifies booked and available seats so that the customer can choose to reserve available seats. Once the customer completes the payment for the booking, the seat booking is confirmed and the customer receives an email notification.

[Customers lining up to book tickets for a show]

## Expectations from the interviewee
Numerous components are present in a typical movie ticket booking system, each with specific constraints and requirements placed on them. The following provides an overview of some of the main expectations that the interviewer will want to hear you discuss in more detail during the interview.

### Seat selection
Selecting a seat is an essential part of the movie ticket booking system. The system has to make sure that no two people can book the same seat. The interviewer expects you to ask questions to identify how the system will work in these situations:

- How will the system make sure that multiple users do not book the same seat?

- Will there be a timeout session that reserves seats temporarily? Will the system use a first come, first serve algorithm?

- Will there be transaction locks involved in the system?

### Payment handling
One of the most significant attributes of the movie ticket booking system is the payment structure that it provides to its customers. This can vary, so the interviewer would expect you to ask the questions listed below:

- What payment methods can the customer use (for example, credit card or cash)?

- How is the payment performed? Does the customer pay themselves online or through a ticket agent on the location?


### Price variance
We touched upon the payment methods of the movie ticket booking system, now, the pricing model needs to be clarified by the interviewer, and therefore you may ask questions like these:

- How will the price of the booking be calculated? Will it vary based on the popularity of the show?

- Does the seat type affect the pricing?

- Will there be discount coupon codes?

### Duplication
There will be many duplicate instances in our system. The interviewer expects you to ask questions like these:

- How are we handling these instances, such as the same cinema having multiple cinema halls showing different movies simultaneously?

- Is the same movie being shown at different times in the same cinema/hall?

## Design approach
We’ll design this movie ticket booking system using the bottom-up design approach. For this purpose, we’ll follow the steps below:

- Identify and design the smallest components first, such as a cinema hall.

- Use these small components to design bigger components, such as building a cinema that can be composed of multiple halls.

- Repeat the above steps until we design the whole system.

## Design pattern
It is always a good practice to discuss the design patterns that a movie ticket booking system falls under, during the interview. Stating the design patterns will give the interviewer a positive impression and shows that the interviewee is well-versed in the advanced concepts of object-oriented design.

The following design pattern can be used to design the movie ticket booking system:

Strategy design pattern

Let’s explore the requirements of the movie ticket booking system in the next lesson.
