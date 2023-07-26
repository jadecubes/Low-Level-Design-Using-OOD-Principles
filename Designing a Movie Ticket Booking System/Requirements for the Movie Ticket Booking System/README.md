# Requirements for the Movie Ticket Booking System
In this lesson, we’ll list the requirements of our movie ticket booking system. This is a very crucial step as requirements define the scope of a problem, so getting them right from the interviewer and understanding them well will make the design of the rest of the system smooth and easy.

We’ll use the notational convention to identify each requirement with a unique label "Rn", where "R" is short for Requirement and "n" is a natural number.


## Requirement collection
The following are the requirements that we have defined for the movie ticket booking problem:

R1: There exist multiple cinemas in the city, and the cinema has multiple halls.

R2: Each movie in the cinema can have multiple shows, however, one hall will only show one show at a time.

R3: The cinema displays all available showtimes of a movie.

R4: Users can search movies based on the following four criteria: title, language, genre, and release date.

R5: Users can make a booking at any cinema hall at the available showtime.

R6: The booking can either be made by the customer online or via a walk-in by the ticket agent.

R7: Online customers can only pay using a credit card, while walk-in customers can pay using cash or credit card through the ticket agent.

R8: Users can select multiple available seats for a show from a given seating arrangement.

R9: Each seat type has a fixed cost. There are three types of seats: silver, gold, and platinum.

R10: There can only be one ticket allocated per seat.

R11: No two customers should be able to reserve the same seat.

R12: The admin can perform the following five actions on the show times and the movie:

Add a show
Delete a show
Update a show
Add a movie
Delete a movie
R13: The system should be able to differentiate between available and booked seats.

R14: The system should generate a notification for the following three cases:

A new movie has been released.

A booking has been made.

A booking has been canceled.

We've identified our requirements for the problem, and in the next lesson, we will define different use cases of our movie booking system.
