# Class Diagram for the Car Rental System
Now, we’ll create the class diagram for the car rental system on the basis of the given requirements. In the class diagram, we will first identify classes (concrete, abstract, or associated) and interfaces for the system. Then, we will determine the relationship between them, according to the requirements in the previous lesson.

## Components of a car rental system
As mentioned earlier, we’ll design the car rental system using a bottom-up approach.

### Address and person
The Address is a custom data type that is required to store any address. The Address contains attributes like a street address, city, state, etc. In the car rental system, this class will be used to specify the address of any person or a car rental location or branch. The Person class stores information related to a person like a name, email, phone number, and address. In the Person class, there is an object of the Address type to specify the person’s address. The class representation of Address and Person is given below:

[The class diagram of the Address and Person classes]

### Account
Account is an abstract class that is used to store the account information of a person. This class has members like account ID, password, the status of an account, etc. There can be two types of accounts, i.e., customer and receptionist. The Customer class represents the customers who reserve the vehicle for themselves, while the Receptionist class represents the receptionist in the car rental system. Both of them can create any vehicle reservation and can cancel the reservation as well. The class representation of Account and its subclasses is given below:

[The class diagram of the Account class]

```
R1: There can be two types of users in the car rental system, i.e., customers and receptionists.
```

### Driver
### Vehicle
### Equipment
### Service
### Notification
### Parking stall
### Vehicle log
### Vehicle reservation
### Payment
### Fine
### Search interface and vehicle inventory class
### Car rental system and branch
### Enumerations
## Relationship between the classes
### Association
#### One-way association
#### Two-way association
### Composition
### Aggregation
### Inheritance
## Class diagram of the car rental system
## Design pattern
## Additional requirements
