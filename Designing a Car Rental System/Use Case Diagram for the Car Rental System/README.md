# Use Case Diagram for the Car Rental System
Let’s build the use case diagram for the car rental system and understand the relationship between its different components.

First, we’ll define the different elements of our system, followed by the complete use case diagram of the system.

## System
Our system is “rent a car.”

## Actors
Now, we’ll define the main actors of our car rental system.

### Primary actors
Member: This is the primary actor of the system who can reserve a vehicle, make payment, and change or cancel the reservations of the vehicle.

### Secondary actors
- Receptionist: This actor acts as the system’s admin and can perform any task a “Member” can perform. This can also add, remove, or modify the vehicle or its reservations and update logs.

- Worker: This actor can update logs, return vehicles, and pay bills.

- System: This can send notifications related to reservation to members.

## Use cases
This section will define the use cases for "Rent a car." We have listed the use cases according to their respective interactions with a particular actor.
```
Note: You’ll see some use cases occurring multiple times because they are shared among different actors in the system.
```
### Member
- Create a new account: To create a new account on the system

- Update/cancel account: To update account information or to cancel an account

- Login/Logout: To log in and out of the car rental system

- Search vehicle inventory: To search for vehicles from the inventory

- Make a reservation: To make a reservation for a vehicle

- Cancel reservation: To cancel the reservation of the vehicle

- Update reservation: To update the reservation information of the vehicle

- Return vehicle: To return the vehicle to the car rental facility

- Pickup vehicle: To pick up the vehicle from the car rental facility

- Pay bill: To pay vehicle rent



### Receptionist
- Create a new account: To create a new account on the system

- Update/cancel account: To update account information or to cancel an account

- Login/Logout: To log in and out of the car rental system

- Search vehicle inventory: To search for vehicles from the inventory

- Make a reservation: To make a reservation for a vehicle

- Cancel reservation: To cancel the reservation of the vehicle

- Update reservation: To update the reservation information of the vehicle

- Add vehicle: To add a new vehicle to the car rental system

- Remove vehicle: To remove a vehicle from the car rental system

- Modify vehicle: To modify a vehicle status or information from the car rental system

- Update log: To update the vehicle log

### System
- Send overdue notification: To send a notification if the date and time for vehicle return are passed

- Send reservation notification: To send a notification of the reservation made

- Send reservation canceled notification: To send a notification of any canceled reservation

## Relationships
We describe the relationships between and among actors and their use cases in this section.

### Generalization
We’ll use the generalization relationship if we want to add, remove, or modify a vehicle. We also need to specify the vehicle type we want to add, remove or modify.

- “Add vehicle” has a generalization relationship with the “Add car,” “Add truck,” “Add van,” and “Add motorbike” use cases.

- “Remove vehicle” has a generalization relationship with the “Remove car,” “Remove truck,” “Remove van,” and “Remove motorbike” use cases.

- “Modify vehicle” has a generalization relationship with the “Modify car,” “Modify truck,” “Modify van,” and “Modify motorbike” use cases.

### Associations
The table below shows the association relationship between actors and their use cases.

```
Member                                   Receptionist                           System

Create a new account                     Create a new account                   Reservation canceled notification

Update/cancel account                    Update/cancel account                  Send reservation notification	

Login/Logout                             Login/Logout                           Overdue notification

Search vehicle inventory                 Search vehicle inventory

Make a reservation                       Make a reservation

Cancel reservation                       Cancel reservation

Update reservation                       Update reservation

Pickup vehicle                           Add vehicle

Return vehicle                           Remove vehicle

Pay bill                                 Modify vehicle

                                         Update log
```


### Include
When a car is returned, the bill is paid. Therefore, “Return vehicle” has an include relationship with “Pay bill.”

### Extend
Whenever a reservation is made, we need to add its details like rental insurance, additional driver, service, and equipment. Therefore, the “Add rental insurance,” “Add additional driver,” “Add service,” and “Add equipment” use cases have an extend relationship with “Make a reservation.”

## Use case diagram

[The use case diagram of the car rental system]

In the next lesson, we’ll discuss the class diagram with a detailed explanation of all classes and their relationship with each other.


