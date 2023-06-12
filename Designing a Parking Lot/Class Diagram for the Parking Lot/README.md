# Class Diagram for the Parking Lot
In this lesson, we will identify and design classes, abstract classes, and interfaces based on the requirements we have previously gathered from the interviewer in our parking lot system.

## Components of a parking lot system
As mentioned earlier, we should design the parking lot system using a bottom-up approach. Therefore, we will first identify and design the classes of the smaller components like vehicles and parking spots. Then, we will create the class of the entire parking lot system, including these smaller components.

### Vehicle
Our parking lot system should have a vehicle object according to the requirements. The vehicle can be a car, a truck, a van, and a motorcycle. There are two ways to represent a vehicle in our system:

- Enumeration

- Abstract class

#### Enumeration vs. abstract class
The enumeration class creates a user-defined data type that has the four vehicle types as values.

This approach is not proficient for object-oriented design because if we want to add one more vehicle type later in our system, then we would need to update the code in multiple places in our code, and this would violate the Open Closed principle of the SOLID design principle. This is because the Open Closed principle states that classes can be extended but not modified. Therefore, it is recommended not to use the enumeration data type as it is not a scalable approach.
```
Note: Using enums isn’t prohibited, but just not recommended. Later, we will use the PaymentStatus enum in our parking lot design as it won’t require further modifications.
```
An abstract class cannot instantiate the object and can only be used as a base class. The abstract class for Vehicle is the best approach. It allows us to create derived child classes for the Vehicle class. It can be extended easily in case the vehicle type changes in the future.

[The class diagram of Vehicle and its derived classes]

```
R4: Four types of vehicles should be allowed to park in the parking lot, which are as follows:

- Car
- Truck
- Van
- Motorcycle
```

### Parking spot
Similar to the Vehicle class, the ParkingSpot should also be an abstract class. There are four types of parking spots: handicapped, compact, large, and motorcycle. These classes can be derived from the parking spot abstract class.

[The class diagram of the ParkingSpot and its derived classes]

```
R2: There are four different types of parking spots: handicapped, compact, large, and motorcycle.
```

### Account
Similar to the Vehicle and ParkingSpot classes, Account should also be an abstract class. There are two child classes: Admin and ParkingAgent. These classes can be derived from the account abstract class.
[The class diagram of Account and its derived classes]

### Display board
This class represents the free parking spot types and the number of empty slots.
[The class diagram of the DisplayBoard class]

```
R5: The parking lot should have a display board that shows free parking spots for each parking spot type.

R7: If the parking lot is completely occupied, the system should show a message on the entrance and on the parking lot display board.
```

### Entrance and exit
The Entrance class is responsible for returning the parking ticket whenever a vehicle arrives. It contains the ID attribute, since there are multiple entrances to the parking lot. It also has the getTicket() method.

The Exit class is responsible for validating the parking ticket’s payment status before allowing the vehicle to exit the parking lot. It contains the ID attribute, since there are multiple exits to the parking lot. It also has the validateTicket() method.

[The class diagram of the Entrance and Exit classes]

```
R8: Customers should be able to collect a parking ticket from the entrance and pay at the exit.
```

### Parking ticket
The ParkingTicket class is one of the central classes of the system. It keeps track of the entrance and exit times of the vehicles, the amount, and the payment status.
[The class diagram of the ParkingTicket class]
```
R8: Customers should be able to collect a parking ticket from the entrance and pay at the exit.
```

### Payment
The Payment class will be an abstract class and will have two child classes, card and cash, since these are two payment methods of the parking lot system.
[The class diagram of the Payment class]

```
R9: The customer can pay for the ticket either with an automated exit panel or pay the parking agent at the exit.

R10: The payment can be made using either a credit/debit card or cash.
```

### Parking rate
The ParkingRate class is responsible for calculating the final payment based on the time spent in the parking lot.
[The class diagram of the ParkingRate class]

```
R11: The payment should be calculated at an hourly rate.
```


### Parking lot
### The enumerations and custom data types
#### Address
### Person
## Relationship between the classes
### Association
### Composition
### Inheritance
## Class diagram of the parking lot system
## Design pattern
## Additional requirements
