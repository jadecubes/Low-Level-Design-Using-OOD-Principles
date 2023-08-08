# Use Case Diagram for the Hotel Management System
Let’s build the use case diagram for the hotel management system and understand the relationship between its different components.

First, we’ll define the different elements of our hotel, followed by the complete use case diagram of the system.

## System
Our system is a "hotel."

## Actors
Now, we will define the main actors of our hotel management system.


### Primary actors
- Guest: This is the hotel's primary actor who can book a room, make payment, and change or cancel the reservations.

- Receptionist: This actor acts as the admin of the system and can perform any task a “Guest” can perform. This can also add, remove, or update the room, check in/check out guests, and issue room keys for guests.

- Manager: This actor can add or modify an employee and issue a card to an employee of the hotel.

- Housekeeper: This can add or update the room’s housekeeping status.

### Secondary actors
- System: This can send booking notifications to guests.

- Server: This can add or update room status according to the room change request.

## Use cases
In this section, we will define the use cases for the hotel. We have listed the use cases according to their respective interactions with a particular actor.
```
Note: You will see some use cases occurring multiple times because they are shared among different actors in the system.
```
### Guest
- Book room: To book a room in the hotel

- Update booking: To update a room booking in the hotel

- Login/Logout: To log in and out of the hotel management system

- Cancel booking: To cancel a room booking in the hotel

- View booking: To view and verify a room booking

- Print booking: To print booking details from the hotel management system

- Search room/booking: To search for a room or a booking in the hotel management system

- Payment: To pay the room rent to the hotel

- View account: To view account details and booking status

- Register new account: To register a new account for new guests

- Return room key: To return the room key before checkout
### Receptionist
- Add room: To add rooms to the hotel management system so guests can book them

- Update room: To update room status from available to booked or vice versa

- Remove room: To remove a room from the hotel management system so guests can't book it

- Book room: To book a room in the hotel

- Update booking: To update a room booking in the hotel

- Login/Logout: To log in and out of the hotel management system

- Cancel booking: To cancel a room booking in the hotel

- View booking: To view and verify a room booking

- Print booking: To print booking details from the hotel management system

- Search room/booking: To search for a room or a booking in the hotel management system

- View account: To view account details and booking status

- Register new account: To register a new account for new guests

- Check in guest: To check in guests to the hotel

- Check out guest: To check out guests from the hotel

- Issue room key: To issue room keys to guests who checked in

### Manager
Issue employee card: To issue employee cards so one can be identified

Add/modify employee: To add a new employee to the hotel management system or to modify the employee's status

Add room: To add rooms to the hotel management system so guests can book them

Update room: To update room status from available to booked or vice versa

Remove room: To remove a room from the hotel management system so guests can't book it

Book room: To book a room in the hotel

Update booking: To update a room booking in the hotel

Login/Logout: To log in and out of the hotel management system

Cancel booking: To cancel a room booking in the hotel

View booking: To view and verify a room booking.

Print booking: To print the booking details from the hotel management system

Search room/booking: To search for a room or a booking in the hotel management system

View account: To view account details and booking status

Register new account: To register a new account for new guests

Check in guest: To check in guests to the hotel

Check out guest: To check out guests from the hotel

Issue room key: To issue room keys to guests who checked in
### System
Add/update room charge: To update the status of the room charge

Send booking notification: To send booking notification to guests

### Housekeeper
Add/update room housekeeping: To update the housekeeping status of rooms


## Relationships
We describe the relationships between and among actors and their use cases in this section.


### Generalization
- The manager is the boss of the receptionist and has access to everything a receptionist has. Therefore, “Manager” has a generalization relationship with “Receptionist.”

- “Cash” and “Credit card” use cases are used for payments. Hence, both have a generalization relationship with the “Pay ticket” use case.


### Associations
The below table shows the association relationship between actors and their use cases.
```
Guest                   Receptionist                 Manager                System                   Housekeeper

Book room               Book room                 Issue employee card       Send booking notification     Add/update room housekeeping

Payment                 View account              Add/modify employee       Add/update room charge

View account            Register new account      Book room

Register new account    Print booking             View account

Print booking           Cancel booking            Register new account

Cancel booking          Login/Logout              Print booking

Login/Logout            Check in guest            Cancel booking

Search room/booking     issue room key            Login/Logout

Update booking          Search room/booking       Check-in guest

View booking            Update booking            Issue room key

Return room key         Check out guest           Search room/booking

                        View booking              Update booking

                        Add room                  Check-out guest

                        Remove room               View booking

                        Update room               Add room

                                                  Remove room

                                                  Update room
```
### Include
- Whenever a guest books a room, the payment will be processed. Hence, the “Book room” use case has an include relationship with “Payment.”

- When a receptionist checks in a guest, a key is issued to the guest. Hence, “Check-in guest” has an include relationship with “Issue room key.”

- When a guest checks out, the key is returned to the receptionist. Hence, “Check-out guest” has an include relationship with “Return room key.”

- If a booking is canceled, the payment will be refunded. Hence the “Cancel booking” use case has an include relationship with “Refund payment.”
  
## Use case diagram
