# Use Case Diagram for the Airline Management System
Let's build the use case diagram of the airline management system and understand the relationship between its different components.

First, we’ll define the different elements of our airline, followed by the complete use case diagram of the system.

## System
Our system is an "airline."

## Actors
Now, we’ll define the main actors of the airline management system.

### Primary actors
- Customer: The customer is the airline's primary actor who can search for flights, create an itinerary, make a payment, and update or cancel the flight reservation.

- Front desk officer: This actor can perform all the actions that the customer can. The front desk officer can create an itinerary, make payment, update or cancel the flight reservation on behalf of customers, assign them seats, and search for flights.

- Admin: The admin is in charge of performing numerous operations, like adding aircraft to the system, adding or modifying flights, flight instances, and their schedules, canceling any flight, and assigning crew to the flight.

### Secondary actors
- System: This actor is responsible for sending notifications for flight status updates, itinerary changes, and reservation cancellations.

- Crew: This actor can view the schedules of the assigned flights.

## Use cases
In this section, we’ll define the use cases for an airline management system. We have listed the use cases according to their respective interactions with a particular actor.
```
Note: You’ll see some use cases occurring multiple times because they are shared among different actors in the system.
```
### Customer/front desk officer
Update/cancel reservation: To update or cancel a flight reservation of the customer

Login/logout: To log in or log out of the airline system

Reset password: To reset the password of the account

Create itinerary: To create an itinerary for the customer

Assign seat: To assign a seat to the passenger for the flight

Search flights: To search for flights in the airline management system

Make payment: To pay for the itinerary or flight reservation

View itinerary: To view the details of an itinerary

Cancel itinerary: To cancel the itinerary for the customer

### Admin
Add aircraft: To add a new aircraft to the airline management system

Add/modify flight: To add a new flight or modify it

Assign crew: To assign crew to the flight instance

Block/unblock user: To block or unblock a user in an airline management system

Cancel flight: To cancel the instance of a flight

Search flights: To search for flights in the airline management system

### System
New itinerary notification: To send a notification of a new itinerary to the customer

Flight status notification: To send the flight status update notification to the customer

Reservation cancel notification: To send a reservation cancellation notification to the customer

### Crew
View flight schedule: To view the schedule of the assigned flights


## Relationships
We describe the relationships between and among actors and their use cases in this section.

### Associations
The below table shows the association relationship between actors and their use cases.
```
Customer                      Front desk officer               Admin                 System                             Crew

Cancel reservation            Cancel reservation               Add aircraft          New itinerary notification         View flight schedule

Login/logout                  Login/logout                     Add/modify flight     Reservation cancel notification

Reset password                Reset password                   Block/unblock users   Flight status notification

Create itinerary              Create itinerary                 Assign crew

Assign seat                   Assign seat                      Cancel flight

Search flights                Search flights                   Search flights

Make payment                  Make payment

View itinerary                View itinerary

Cancel itinerary              Cancel itinerary
```

### Include
To create an itinerary, one or more flight reservations should be created to add the passengers to the itinerary. Therefore, the “Create itinerary” use case has an include relationship with both “Create flight reservation” and “Add passenger” use cases.

While creating a flight reservation, the seat should be assigned to the customer. Therefore, the “Create flight reservation” use case has an include relationship with the “Assign seat” use case.

Whenever the flight is canceled, its related flight reservations should also be canceled. Hence the “Cancel flight” use case has an include relationship with the “Cancel reservation” use case.

When an itinerary is created, a notification is sent to the customer. Therefore, the “Create itinerary” use case has an include relationship with the “New itinerary notification” use case.

If an itinerary is canceled, the payment will be refunded, and a reservation cancellation notification will be sent to the customer. Hence, the “Cancel itinerary” use case has an include relationship with both “Refund payment” and “Reservation cancellation notification” use cases.

When the flight is canceled, the payment will be refunded, and a reservation cancellation notification will be sent to the customer. Hence, the “Cancel reservation” use case has an include relationship with both “Refund payment” and “Reservation cancellation notification” use cases.

### Extend
When modifying the flight instance, the admin can assign the crew to the flight instance. Therefore, the “Modify flight instance” use case has an extend relationship with the “Assign crew” use case.

## Use case diagram
[The use case diagram of the airline management system](./ucd.png)
