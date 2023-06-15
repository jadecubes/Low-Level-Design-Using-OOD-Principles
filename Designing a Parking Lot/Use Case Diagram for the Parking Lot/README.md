# Use Case Diagram for the Parking Lot
Let’s build the use case diagram of the parking lot system and understand the relationship between its different components.

First, let’s define the different elements of our parking lot, followed by the complete use case diagram of the system.

## System
Our system is a "parking lot."

## Actors
Here are the main actors of our parking lot system.

### Primary actors
- Customer: This actor can park the vehicle in the allocated parking space according to the vehicle type and pay for the parking before exit.

- Parking agent: The parking agent will assist the customer and perform all the tasks that a customer can do, such as paying the parking ticket on behalf of the customer.

### Secondary actors
- Admin: This can add, remove, or update a spot, agent, entry/exit panels, and view/update accounts.

- System: This is responsible for giving details of parking spot availability and assigning a parking spot to a vehicle.

## Use Cases
In this section, we will define the use cases for the parking lot. We have listed down the use cases according to their respective interactions with a particular actor.
```
Note: You will see some use cases occurring multiple times because they are shared among different actors in the system.
```
### Admin
- Add spot: To add a parking spot

- Add agent: To add a new agent

- Add/modify rate: To add/modify hourly rate

- Add entry/exit panel: To add and update exit/entry panel at each entry/exit

- Update account: To update account details and payment information

- Login/Logout: To login/logout to/from agent or admin account

- View account: To view account details like payment status or unpaid amount
### Customer
- Take ticket: To take a ticket at the entrance, that contains information regarding the vehicle and its entrance time

- Scan ticket: To scan the ticket at the exit and get the parking fee

- Pay ticket: To pay the parking fee at the exit panel via cash or a credit card

- Cash: To pay the parking fee via cash

- Credit card: To pay the parking fee via credit card

- Park vehicle: To park the vehicle at the assigned destination

### Parking agent
- Update account: To update account details and payment information

- Login/Logout: To log in/log out to/from the agent or admin account

- View account: To view account details like payment status or unpaid amount

- Take ticket: To take a ticket at the entrance, that contains information regarding the vehicle and its entrance time

- Scan ticket: To scan the ticket at the exit and get the parking fee

- Pay ticket: To pay the parking fee at the exit panel via cash or a credit card

- Cash: To pay the parking fee via cash

- Credit card: To pay the parking fee via credit card

- Park vehicle: To park the vehicle at the assigned destination

### System
- Assigning parking spots to vehicles: To check the vehicle type and associate a free spot according to it

- Remove spot: To remove a parking spot if it is not available for parking

- Show full: To display the status of the parking lot as full

- Show available: To show the details of available parking spots

## Relationships
This section describes the relationships between and among actors and their use cases.

### Generalization
- The “Parking agent” has a generalization relationship with the “Customer” since the parking agent can perform all those tasks that a customer can perform.

- “Cash” and “Credit card” use cases are used for payments. Hence, both have a generalization relationship with the “Pay ticket” use case.

### Associations
The table below shows the association relationship between actors and their use cases.
```
Admin                    Customer                  Parking Agent              System

Add spot                Take ticket                Update account            Assigning parking spots to vehicles

Add agent               Scan ticket                Login/Logout              Remove spot

Add/modify rate         Pay ticket                 View account              Show full

Add entry/exit panel    Cash                       Take ticket               Show available

Update account          Credit card                Scan ticket               

Login/Logout            Park vehicle               Pay ticket              

View account                                       Cash

                                                   Credit card

                                                   Park vehicle
```
### Include
The “Scan ticket” has an include relationship with the “Pay ticket” since it is necessary to scan a ticket and get the total payable fee of parking a vehicle before the actual payment.

## Use case diagram

[The use case diagram of parking lot system](./usecasediagram.png)

In the next lesson, we will discuss the class diagram with a detailed explanation of all classes and their relationship with each other.
