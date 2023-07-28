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
The table below shows the association relationship between actors and their use cases.
```
Admin               Customer                       Ticket Agent                     System

Add show            Search movie                   Search movie                    Send new movie notification

Modify show         Create/view/modify/cancel      Create/view booking             Send booking notification
                    booking

Delete show         Reserve a seat                 Reserve a seat                  Send cancellation notification

Add movie           Pay using credit card/cash

Search movie

Delete movie
```
## Include
- The “Create booking” use case has an include relationship with the “Reserve seat” use case, since the booking creation process includes reserving a seat on a seating map.

- The “Pay using cash” and “Pay using credit card” use cases have an include relationship with the “Send booking notification” use case, since once the payment has been made and verified, only then will the system generate a notification.

- The “Cancel booking” use case has an include relationship with the “Refund payment” use case, since this is part of the process.

- The “Add movie” use case has an include relationship with the “Send new movie notification” use case, since a notification will only be sent when an admin adds a new movie.

- The “Cancel booking,” “Delete movie,” and “Delete show” use cases have an include relationship with the “Send cancellation notification” use case, since a notification will only be sent when an admin cancels the show or the movie or a customer cancels their booking.

# Use case diagram

[Use case diagram of movie ticket booking system.](./usecase.png)
