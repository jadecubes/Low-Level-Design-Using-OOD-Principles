# Class diagram for the Restaurant Management System
We’ll create the class diagram for the restaurant management system. In the class diagram, we will first design the classes and then identify the relationship between classes according to the requirements for the restaurant management system design problem.

## Components of the restaurant management system
As mentioned earlier, we’ll follow the bottom-up approach to design a class diagram for the restaurant management system design.

### Account
An Account contains an ID for the user. It also stores the address, account status, and password that can be reset.

[The Account class]

### Person
The Person class is extended by the Employee and Customer classes and stores the person's name, email, and phone number.

- Employee: This derived class stores the employee ID and the joining date of the employee. It is extended by Chef, Waiter, Receptionist, and Manager.

    - Chef: Prepares the order taken by a waiter

    - Waiter: Takes an order from the customer

    - Receptionist: Creates a reservation

    - Manager: Can add new employees

- Customer: This derived class keeps track of the last visited date of the customer.

[Person and its derived classes]

```
R3: The waiter should be able to create an order for a table and add items for each person seated.

R6: The system should allow for the reservation of tables.

R7: The receptionist should be able to search for available tables by date and time and make a reservation.
```

### Table and table seat
Table: This class is identified by an ID, a limited seating capacity, a specific location, and status. A table may have multiple seats.

TableSeat: It is identified by a seat number and has a type that can be updated.

[The Table and TableSeat classes]

```
R5: The system should be able to provide information about tables currently available for walk-in customers.

R6: The system should allow for the reservation of tables.
```

### Meal and meal item
Meal: It has a unique meal ID and may or may not be present as a MealItem.

MealItem: It is identified by a meal item ID and has a specific quantity that can be updated.

[The Meal and MealItem classes]

```
R4: Each person’s order can consist of multiple items, each corresponding to a menu item.
```

### Menu, menu section, and menu item
Menu: It has a unique ID and title, a description, and may have several sections.

MenuSection: This class represents a section of the menu that has an ID, a title, and a description. It may have multiple menu items.

MenuItem: It is identified by an ID and has a title, description, and price that can be updated.

[The Menu, MenuSection, and MenuItem classes]

```
R2: Each branch will offer a menu with various sections and items.
```

### Order
Order is identified by an ID and has a status that can be updated regarding adding or removing meals.

[The Order class]

```
R3: The waiter should be able to create an order for a table and add items for each person seated.

R4: Each person’s order can consist of multiple items, each corresponding to a menu item.
```

### Kitchen
The Kitchen class has a name and an assigned chef.

[The Kitchen class]

### Reservation
A Reservation is made by the receptionist for the customer and has a reservation ID, reservation time, count and information of the customers, status, notes, and check-in time.

[The Reservation class]

```
R6: The system should allow for the reservation of tables.

R8: The system should allow customers to make and cancel their reservations.

R9: The system should send notifications as the reservation time approaches.
```
### Payment
Payment is an abstract class extended by CreditCardPayment, CashTransaction, and CheckTransaction as its child classes. This class stores a payment ID, the total amount, and the payment date.

- CreditCardPayment: This derived class represents a credit card transaction.

- CashTransaction: This derived class represents a payment made in cash.

- CheckTransaction: This derived class represents a payment made through a check. The check has a check number that belongs to a specific bank.

[Payment and its derived classes]

```
R10: Customers should be able to pay their bills with credit cards, checks, or cash.
```

### Bill
The Bill class represents the total amount a customer has to pay based on the items ordered from the menu. This class stores an ID, the total amount to be paid, the tip, and the tax. Moreover, it holds the record of whether or not the bill was paid.

[The Bill class]

```
R10: Customers should be able to pay their bills with credit cards, checks, or cash.
```
### Notification
A Notification is a message sent to a customer from the restaurant. Every Notification has a specific ID, the date on which it was sent, and the content written by the customer. It is extended by SMSNotification and EmailNotification:

- SMSNotification: This derived class represents a notification sent to a customer's phone number. Therefore, it stores the phone numbers of all the customers.

- EmailNotification: This derived class represents a notification sent to a customer's email. Therefore, it stores the email addresses of all the customers.

[The Notification and its derived classes]

```
R9: The system should send notifications as the reservation time approaches.
```


### Seating chart, branch, restaurant
SeatingChart: This class represents the seating plan of a restaurant that can also be printed. It is identified by a unique ID.

Branch: This class represents the branches of a restaurant. Every Branch has a specific name and location.

Restaurant: This class has a name and maintains a list of branches that can be updated.

[The SeatingChart, Branch, and Restaurant classes]

```
R1: The restaurant can have multiple branches.

R2: Each branch will offer a menu with various sections and items.

R11: Each branch may have different configurations of tables.
```
### Enumerations and custom data types
AccountStatus: This enumeration keeps track of an account's current status—whether it is active, closed, canceled, or blocklisted.

TableStatus: This enumeration checks whether a table is reserved, occupied, or free.

OrderStatus: This enumeration keeps track of a customer's order status.

PaymentStatus: This enumeration keeps track of an order's payment status by the customer.

ReservationStatus: This enumeration represents the reservation status of a table for a customer.

SeatType: This enumeration represents the type of seat for the customer and keeps track of it.

[Enums in the restaurant management system]

Address: This custom datatype represents the address of the restaurant's branch or a person.

[Class diagram of the Address custom data type]


## Relationship between the classes
Now, we’ll discuss the relationships between the classes we have defined above in our restaurant management system.

### Association
The class diagram has the following association relationships:

#### One-way Association
- The Employee class has a one-way association with Branch.

- The Meal class has a one-way association with TableSeat.

- The MealItem class has a one-way association with MenuItem.

- The Waiter class has a one-way association with Order.

- The Order class has a one-way association with Table.

- The Chef class has a one-way association with Order and Kitchen.

- The Receptionist class has a one-way association with Reservation.

- The Reservation class has a one-way association with Table.

[The one-way association relationship between classes]

#### Two-way Association
- The Branch and Menu classes are associated with each other.

- The Customer and Reservation classes are associated with each other.

- The Reservation and Notification classes are associated with each other.

- The Payment and Bill classes are associated with each other.

- The Bill and Order classes are associated with each other.

[The two-way association relationship between classes]

### Composition
- The class diagram has the following composition relationships.

- The Branch class is composed of SeatingChart and Kitchen.

- The Restaurant class is composed of Branch.

- The Employee class is composed of Account.

- The Table class is composed of TableSeat.

- The Meal class is composed of MealItem.

- The Order class is composed of Meal.

- The MenuSection class is composed of MenuItem.

- The Menu class is composed of MenuSection.

[The composition relationship between classes]

### Inheritance
The following classes show an inheritance relationship:

- Both, Employee and Customer, extend the Person class, where the Employee class is extended by Chef, Manager, Waiter, and Receptionist.

- SMSNotification and EmailNotification extend the Notification class.

- Payment class is extended by CreditCardPayment, CashTransaction, and CheckTransaction.
```
Note: We have already discussed the inheritance relationship between classes in the component section above one by one.
```
## Class diagram for the Restaurant Management System
[The class diagram of restaurant management system]

## Design pattern
The following design patterns have been used in the class diagram:

- The Singleton pattern: This pattern ensures that a class has only one instance and provides a global point of access to that instance. This can be useful for the RMS’s database connection, for example, to ensure that there is only one connection to the database, and to make it easy for other parts of the system to access the connection.

- The Command pattern: This pattern encapsulates a request as an object, which allows the request to be parametrized with different data. In the context of an RMS, this pattern could be used to encapsulate requests to the database, such as add, delete or modify entries. This way the views or other components don’t need to know how to handle the request. They just need to know how to execute it.

- The Observer pattern: This pattern allows objects to be notified of changes to other objects. In the context of an RMS, this pattern could be used to notify the viewers of changes to the model so that they can update themselves accordingly.

- The Factory pattern: This pattern provides a way to create objects without specifying the exact class of object that will be created. In an RMS, this pattern could be used to create different types of menu items, for example, without having to specify the exact class of each item.


## Additional requirements
The interviewer can introduce some additional requirements in the given restaurant management system, or they can ask some follow-up questions. Let's see examples of the additional requirements:

Discount: A discount will be applied to the payment depending on special events such as the New Year, an anniversary, a branch opening, and so on. The class diagram provided below shows the relationship of Discount with the Payment class:

[The relationship of the Discount class with the Payment class]

We have completed the class diagram of the restaurant management system according to the requirements. Now, let's design its sequence diagram in the next lesson.


