# Class Diagram for the Movie Ticket Booking System
In this lesson, we are going to identify and design the classes, abstract classes, and interfaces based on the requirements that we have previously gathered from the interviewer in our movie ticket booking system.

# Components of a movie ticket booking system
As mentioned earlier, we should design the movie ticket booking system using a bottom-up approach.

## Seat
Our movie ticket booking system should have a Seat object that will be an abstract class and can be of three types: silver, gold, and platinum. Each seat type will have a fixed cost and differs from one another.

The visual representation of these classes is as follows:

[The class diagram of Seat and its derived classes](./seat.png)

```
R9: Each seat type has a fixed cost. There are three types of seats:

- Silver
- Gold
- Platinum
R13: The system should be able to differentiate between available and booked seats.
```

## Show time
The ShowTime class represents a particular show of a movie and contains information like the start time, the date on which the show is airing, and the number of seats available for the show.

Here is what the class definition looks like:

[The class diagram of the ShowTime class](./showtime.png)

```
R5: Users can make a booking at any cinema at the available showtime.
```


## Hall
The Hall class is responsible for finding the current show airing. It contains the ID attribute as there can be multiple halls inside a cinema and is composed of a ShowTime object that specifies the currently airing show.

The UML representation of the class is shown below:

[The class diagram of the Hall class](./hall.png)

```
R2: Each movie in the cinema can have multiple shows, however, one hall will only show one show at a time.
```

## Cinema
The Cinema class consists of the number of halls present in the cinema along with the city in which it is located and an id attribute to identify the cinema in that particular city.

The class representation of the Cinema class is as follows:

[The class diagram of the Cinema class](./cinema.png)

```
R1: There exist multiple cinemas in the city and the cinema has multiple halls.
```

## City
The City class includes the name of the city, the state it is located in, and its zip code. In addition, it includes a list of all the cinemas available in the city.

The UML representation of the class is shown below:

[The class diagram of the City class](./city.png)

```
R1: There exist multiple cinemas in the city and the cinema has multiple halls.
```

## Movie
The Movie class contains all the various details of a particular movie, such as the title, genre, language, and release date. It is also composed of a list of running shows.

Here is what the class definition looks like:

[The class diagram of the Movie class](./movie.png)

```
R4: Users can search movies based on the following four criteria:

- Title
- Language
- Genre
- Release date
```

## Movie ticket
The MovieTicket class refers to a customer’s ticket for a particular movie with a ticketID as its unique identifier. It describes the details of the seat in the hall and the movie for which the ticket was bought, along with the show details.

The class representation of the MovieTicket class is as follows:

[The class diagram of the MovieTicket class](./ticket.png)

```
R10: There can only be one ticket allocated per seat.
```


## Payment
The Payment class will be an abstract class and will have two child classes: CreditCard, and Cash, since these are two payment methods of the movie ticket booking system.

The visual representation of these classes is as follows:

[The class diagram of the Payment class and its child classes](./payment.png)

```
R7: Online customers can only pay using a credit card, while walk-in customers can pay using cash or credit card through the ticket agent.
```

## Person
The Person class contains details like name, address, phone number, and email and is derived into the following three different classes:

- Customer

- Admin

- TicketAgent

The following goes into more depth in each of the derived classes mentioned above:

### Customer
The Customer class refers to a user trying to create an online booking for any movie. A customer can also update the booking details and cancel the booking.

### Admin
The Admin class is responsible for performing actions like adding, updating, and removing movies and shows.

### Ticket agent
The TicketAgent class is responsible for creating bookings on behalf of walk-in customers. However, unlike the Customer class, a ticket agent cannot update or cancel a booking.

The class diagram of all these is provided below:

[The class diagram of different people that interact with our system](./person.png)

```
R5: Users can make a booking at any cinema hall at the available showtime.

R6: Booking can either be made by the customer online or via walk-in by the ticket agent.

R12: The admin can perform the following five actions on the showtimes and the movie:

- Add a Show
- Delete a Show
- Update a Show
- Add a Movie
- Delete a Move
```

## Notification
Notification will be an abstract class since it can send a notification via email or phone (SMS). It is mainly responsible for sending notifications whenever any of the following conditions get met:

- A customer makes a new booking.

- The admin deletes a particular show, or a customer cancels their booking.

- The admin adds a new movie to the database.

The UML representation of the class is shown below:

[The class diagram of Notification and its child classes](./notification.png)

```
R14: The system should generate a notification for the following three cases:

- A new movie has been released.
- A booking has been made.
- A booking has been canceled.
```

## Catalog
The Catalog is the class where the search function is implemented. Each catalog will contain a list of movies sorted according to one of the given search techniques, i.e., based on the movie’s title, language, genre, or release date.

The class representation of the Catalog class is as follows:
[The class diagram of the Catalog class](./catalogue.png)

```
R4: Users can search movies based on the following four criteria:

- Title
- Language
- Genre
- Release date
```

## Search
The Search class will be an interface that allows customers to search for any particular movie and return the list of movies upon searching, by any of the following methods:

- Search movies by their title.

- Search movies by their language.

- Search movies by their genre.

- Search movies by their release date.

The UML representation of the class is shown below:

[The class diagram of the Search interface](./search.png)

```
R4: Users can search movies based on the following four criteria:

- Title
- Language
- Genre
- Release date
```
## Booking
The Booking class is the main class of our movie ticket booking system and contains a reference to the number of seats and tickets that a customer booked. In addition, it includes information about the payment status, the booking status, the show time, and the total amount that was charged for the booking.

The UML representation of the Booking class is as follows:

[The class diagram of the Booking class](./booking.png)

```
R5: Users can make a booking at any cinema at the available showtime.
```


## Enumerations
The following is the list of enumerations required in the movie ticket booking system:

- PaymentStatus: The payment status checks if the customer's payment falls in any of the following stages: confirmed, declined, pending, or refunded.

- BookingStatus: The booking status describes the status of a particular movie booking of a customer, whether it is pending, confirmed, canceled, declined, or refunded.

- SeatStatus: The seat status tells about the status of a particular seat in the hall, whether it is currently available, booked, or already reserved.

These enumerations can be represented using the following class diagram:

[Enums in the movie ticket booking system](./status.png)

# Relationship between the classes
Now, we are going to discuss the relationships between the classes we have defined above in our movie ticket booking system.

## Association
The class diagram has the following association relationships:

- The City class has a one-way association with Cinema.

- The Admin class has a one-way association with ShowTime, Movie, and Notification.

- Both Customer and TicketAgent have a two-way association with Notification.

- The Booking class has a one-way association with ShowTime, MovieTicket, and Seat.

- The Booking class has a two-way association with Payment.

- The ShowTime class has a one-way association with Seat and MovieTicket.

- The Movie class has a one-way association with ShowTime and MovieTicket.

[The association relationship between classes](./association.png)

## Composition
The class diagram has the following composition relationships:

- The Cinema class is composed of the Hall class, which is composed of the ShowTime class.

[The composition relationship between classes](./composition.png)

## Aggregation
The following classes show an aggregation relationship:

- The Movie class contains the Catalog class.

[The aggregation relationship between classes](aggregation.png)

## Generalization
The following classes show a generalization relationship:

- The Catalog class implements the Search class.

[The generalization relationship between classes](./generalization.png)

## Inheritance
The following classes show an inheritance relationship:

- The Gold, Platinum, and Silver classes extend the Seat class.

- The Admin, Customer, and TicketAgent classes extend the Person class.

- Both Cash and CreditCard extend the Payment class.

- Both EmailNotification and PhoneNotification extend the Notification class.
```
Note: We have already discussed the inheritance relationship between classes in the component section above one by one.
```
# Class diagram of the movie ticket booking system

[The class diagram of the movie ticket booking system](./classdiagram.png)

# Handle concurrency
One of the major requirements of the movie ticket booking system is that no two customers can book the same seat in the same show of a movie. This is to prevent the case of double booking where two people have the same seats allocated to them.

To handle concurrent seat allocations, we can use the concept of locks, more specifically, optimistic locks or versioning.

The entire process has been summarized in the illustration given below:

- Customer 1 tries to select some seats on the seat selection map and gets assigned a version number V1.
- At the same time, customer 2 also tries to select some seats on the seat selection map and gets assigned a version number V1. However, both customers select the same seat.
- A lock time gets assigned that keeps track of the timestamps related to the customers entering in the payment section.
- The mutex lock gets acquired and the expiration time period starts. Since customer 1 took less time, it starts the payment process while customer 2 needs to wait.
- Customer 1 successfully completes the payment. The mutex lock also gets released.
- Versions of both customer 1 and the system get updated. Since the lock has been released, customer 2 can now perform the action of booking the tickets again.
- However, since the system version has been updated, customer 2 would need to perform the entire task from the beginning.
- The previous seat has become unavailable so customer 2 selects a new seat.

[Handle Concurrency]

# Design pattern
In the movie ticket booking system, there can be multiple seat types for a cinema hall, and each seat type will have its own formula to calculate the ticket fare. Therefore, the Strategy design pattern can be applied here, which will design a separate strategy or algorithm to calculate the price of each seat type. It is applied through the definition of a function that provides the implementation of the rates for each seat type using different strategies. This strategy can also differ based on a movie’s popularity or taxes

# Additional requirements
The interviewer can introduce some additional requirements in the movie ticket booking system, or they can ask some follow-up questions. Let’s see some examples of additional requirements:

Discount: Customers can use a coupon to add a discount to their payment. The class diagram provided below shows the relationship of Discount with the Payment class:

[The relationship between the Discount class and the Payment class]

Customer and the guest users: There should be two types of users in our system. The guest user can search for movies and choose to register. The customer should be an authenticated user and is able to search movies and book shows. The class diagram below shows how we can implement separate functionality for different users:

[The class diagram of different users of our system]

We have completed the class diagram of the movie ticket booking system according to the requirements. Let’s now design the sequence diagram of the movie ticket booking system in the next lesson.

