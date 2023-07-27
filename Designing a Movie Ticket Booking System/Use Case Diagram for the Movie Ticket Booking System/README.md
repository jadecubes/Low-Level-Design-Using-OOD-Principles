# Use Case Diagram for the Movie Ticket Booking System
Let’s build the use case diagram of the movie ticket booking system and understand the relationship between its different components.

First, we’ll define the different elements of our movie ticket booking system, followed by the complete use case diagram of the system.

# System
Our system is the “movie ticket booking system.”

# Actors
Now, we are going to define the main actors of our movie ticket booking system.

## Primary actors
- Customer: This actor can book one or more movie tickets for any movie as well as modify and cancel the booking. They also need to pay for the movie tickets that they booked.

- Ticket agent: The ticket agent will assist the customer and perform almost all the tasks that a customer can do, such as creating a booking of the movie ticket on behalf of the customer, except for modifying and canceling a booking.
## Secondary actors
- Admin: This can add, remove, or update a show and movie.

- System: This is responsible for sending out notifications for new movies, bookings, cancellations, etc.
# Use Cases
In this section, we will define the use cases for movie ticket booking systems. We have listed the use cases according to their respective interactions with a particular actor.
```
Note: You will see some use cases occurring multiple times because they are shared among different actors in the system.
```
## Admin
- Add show: To add a new show for any particular movie

- Modify show: To modify a show

- Delete show: To delete or cancel a show

- Add movie: To add a new movie to the calendar

- Search movie: To search for any particular movie based on the given criteria (title, language, genre, release date)

- Delete movie: To delete any particular movie

## Customer
- Search movie: To search for any particular movie based on the given criteria (title, language, genre, release date)

- Create/Modify/View/Cancel booking: To create or cancel a booking for any show of a movie, and to view or modify the booking details for any show of a movie

- Reserve a seat: To reserve a seat from the available seats on a seating map for any show of a movie

- Pay using credit card/cash: To pay the movie ticket fee via credit card or cash

## Ticket agent
- Search movie: To search for any particular movie based on the given criteria (title, language, genre, release date)

- Create/View booking: To create a booking for any show of a movie and view its details

- Reserve a seat: To reserve a seat from the available seats on a seating map for any show of a movie

## System
- Send new movie notification: To send a notification of any new movie launched

- Send booking notification: To send a notification of the bookings made

- Send cancellation notification: To send a notification of any canceled bookings

# Relationships
We describe the relationships between and among actors and their use cases in this section.

## Generalization
We can search for a movie with the title, language, genre, or release date. This shows that the “Search movie” use case has a generalization relationship with the “By movie title,” “By movie language,” “By movie genre,” and “By movie release date” use cases.

## Associations
## Include
# Use case diagram
