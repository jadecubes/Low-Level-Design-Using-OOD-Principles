# Class Diagram for the Airline Management System
In the class diagram, we will first design and create the classes, abstract classes, and interfaces for the system. Then, we’ll identify the relationship between classes in accordance with all the requirements of the airline management system.

## Components of an airline management system
In this section, we’ll define the classes for an airline management system. As mentioned earlier, we will design the airline management system using a bottom-up approach. We will create the classes of small components first. Next, we will integrate these components and create the class diagram for the entire airline management system.

### Account
The Account class identifies the username and ID of an airline management system user. . The class definition is represented below:
[The Account class]

### Person
Person is an abstract class used to store information related to a person like a name, email, phone number, etc. In this class, the Address object type specifies the person’s address. There can be four types of accounts in the system:

- Admin: This class keeps track of the overall system and flight and aircraft records.

- Crew: This class views assigned flights in the system.

- FrontDeskOfficer: This class manages passenger reservations.

- Customer: This class views flight schedule, and reserves or cancels flight reservations.

The relationship diagram for these classes is shown below:

[Person and its derived classes]

```
R4: The system should allow the customer to check flight details, such as available seats, flight schedules, and departure/arrival times.

R5: The system admin should be able to add new flights and aircraft. The admin should be able to cancel previous flights.

R11: The front desk officer should be able to reserve tickets, create itineraries, and make flight payments for the customer.

R12: The flight crew should be able to view the schedule for their assigned flights.
```

### Airline, airport, and aircraft
The Airline class has attributes like a name and an airline code to distinguish the airline from other airlines. It is an essential part of the airline management system.

Each airline operates out of different airports. Therefore, we need the Airport class to keep track of all the airports in the system.

Airlines own or hire aircraft to carry out their flights. The Aircraft class has attributes like name, model, manufacturing year, etc.

Here’s a visual representation of these classes:

[The Airline, Airport, and Aircraft classes]

```
R6: An airline should be able to own multiple aircrafts. The admin should be able to add these aircrafts to the system.

R7: An airline should be able to operate its flights from different airports.
```

### Seat and flight seat
The Seat class represents a physical seat in the aircraft. It contains basic information like seat number, seat type, and class. The FlightSeat class is derived from the Seat class and represents the seat assigned to a specific flight instance. It contains the fare for that particular seat and its reference number.

The relationship diagram for these classes is shown below:

[Seat and its derived class]

### Flight and flight instance
The Flight class contains information about a particular flight, including the flight number, departure and arrival airports, and the duration of the flight. The FlightInstance class represents a single occurrence of a flight, since a flight can fly multiple days in a week.

These classes are represented below:

[The Flight and FlightInstance classes]

```
R1: A customer should be able to search for flights by date, departure, and destination airport.

R4: The system should allow the customer to check flight details, such as available seats, flight schedule, and departure/arrival times.
```


### Flight reservation
The FlightReservation class manages the reservations made by the customer against a flight instance. It has attributes like unique reservation number, passengers and their assigned seats, and the reservation status.

The UML diagram for this class is given below:

[The FlightReservation class]

```
R2: A customer should be able to reserve tickets for available flights. Customers should also be able to book multiple flights at once.
```

### Itinerary and passenger
Customers create an itinerary for their travel that contains flight reservations. The Itinerary class keeps track of all the reservations made, the list of passengers, and the departure/arrival airport.

The Passenger class keeps a record of all individuals with the reservation. It also includes the basic travel information of the passenger.

Here’s the class diagram for these classes:

[The Itinerary and Passenger classes]

```
R2: A customer should be able to reserve tickets for available flights. Customers should also be able to book multiple flights at once.
```
### Search and catalog
Search and catalog
The Search interface allows the customers to search for any flight using the following criteria:

- Departure and arrival date and time

- Source and destination airports

The SearchCatalog implements the search functionality and contains a list of all flights of the airline. The two classes are shown below:

[The Search interface and the SearchCatalog class]

```
R1: A customer should be able to search for flights by the date, departure, and destination airport.
```

### Payment
The Payment class will be an abstract class and will have two child classes: CreditCard, and Cash.

The visual representation of these classes is as follows:

[The Payment and its derived classes]

```
R9: The customer should be able to make payments against their flight reservations.
```

### Notification
Notification is an abstract class, since it can send a notification via email or SMS. It is mainly responsible for sending notifications whenever required.

The UML representation of the class is shown below:

[Notification and its derived classes]

```
R13: The system should send the customer a notification whenever a reservation has been made or canceled or when there is an update for their flight.
```

### Enumerations
The enumerations required in the airline management system design are listed below:

AccountStatus: The account status tells us about the status of a customer's account—whether it is active, deactivated, closed, or blocked.

SeatStatus: The seat status tells us whether the seat is available, booked, or a chance seat.

SeatType: The seat type tells us whether the seat is of a regular, accessible, emergency exit, or extra legroom type.

SeatClass: The seat class tells us whether the seat is economy, economy plus, business, or first class.

FlightStatus: The flight status keeps track of the flight instance—whether it is factive, scheduled, delayed, departed, landed, canceled, diverted, or unknown.

ReservationStatus: The reservation status tells us about the status of the reservation—whether it is requested, pending, confirmed, checked in, or canceled.

PaymentStatus: The payment status tells us about the status of the payment—whether it is pending, completed, canceled, failed, declined, or refunded.

[Enums in the airline management system]


### Custom data type
We need to create a custom data type, Address, that will store the physical location of any place.

[The Address custom data type]

## Relationship between classes
Now, we’ll discuss the relationships between the classes we have defined above in our airline management system.

### Association
The class diagram has the following association relationships:

#### One-way association
Both FrontDeskOfficer and Customer classes have a one-way association with the Itinerary class.

The FlightReservation class has a one-way association with the FlightInstance, Payment, and Notification classes.

The FlightSeat class has a one-way association with the FlightReservation class.

The Person class has a one-way association with the Search interface.

#### Two-way association
The Airport class has a two-way association with the Flight class.

Both the Aircraft and Crew classes have a two-way association with the FlightInstance class.

The Airline class has a two-way association with the Crew class.

[Association relationship between classes]

### Aggregation
The class diagram has the following aggregation relationship:

The Itinerary class contains the Passenger class.

[The aggregation relationship between classes]

### Composition
The class diagram has the following composition relationships:

The Person class is composed of the Account class.

The Airline class is composed of the Aircraft class.

The Aircraft class is composed of the Seat class.

The Flight class is composed of the FlightInstance class.

The FlightInstance class is composed of the FlightSeat class.

The Itinerary class is composed of the FlightReservaion class.

[The composition relationship between classes]

### Inheritance
The following classes show an inheritance relationship:

The Admin, Crew, FrontDeskOfficer, and Customer classes extend the Person class.

The FlightSeat class extends the Seat class.

The CreditCard and Cash classes extend the Payment class.

The EmailNotification and SmsNotification classes extend the Notification class.
```
Note: We have already discussed the inheritance relationship between classes in the component section above one by one.
```
## Class diagram of the airline management system
[The class diagram of the airline management system]

## Design pattern
The Airline class follows the Singleton design pattern because there will only be a single instance of the Airline class as it is the main organizational class.

The airline management system can also implement the Observer design pattern because all the passengers flying in a particular flight instance must be updated about any changes in their flight schedule. The passengers here will act as subscribers and be notified whenever the flight status changes.

We have successfully designed the class diagram for the airline management system. Let’s see how we can construct the sequence diagram for the system in our next lesson.
