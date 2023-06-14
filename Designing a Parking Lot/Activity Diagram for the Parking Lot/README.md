# Activity Diagram for the Parking Lot
An activity diagram is a great way to visualize the flow of messages from one activity to the other in the system. There can be different activity diagrams that we can create for our parking lot system. For this lesson, we will create activity diagrams for the following two activities:

- The vehicle entering the parking lot

- Activity challenge: Customer pays the parking ticket

## Vehicle entering the parking lot
The following are the states and actions that will be involved in this activity diagram.

### States
Initial state: The customer enters the parking lot.

Final state: There are two final states present in this activity diagram, shown below:

- The customer receives the parking ticket through the system.

- There is no parking slot vacant, so the customer is denied access to the parking lot.

### Actions
The customer arrives at the parking lot entrance and selects their vehicle type. They are assigned their dedicated parking spot according to their select vehicle type. The parking lot then informs us about the availability of that parking spot and allows access accordingly.

Based on the order above, the activity diagram of a vehicle entering a parking lot is given below.
```
Note: Here we assume that only a car can be parked in the handicap spot. Access is only available if the car has a disabled person card present.
```
[The activity diagram for the vehicle entering a parking lot]

## Activity challenge: The customer pays the parking ticket
You will help us create an activity diagram of a customer paying a parking ticket at the exit panel.

The skeleton of the activity diagram below represents that the customer has a valid parking ticket available.
[The activity diagram for the vehicle entering a parking lot]

Notice that the actions in the diagram above are numbered from 1 to 11. The slots shown below represent the activities and the arrows represent the flow from one activity to the other. Can you rearrange the slots below in the correct order they should appear in the activity diagram above?

Based on the description above, can you fill in the missing slots with the correct order of actions in the activity diagram?
```
Note: If you get stuck, just click the “Show Solution” button for the correct answer.
```
[sequence](./seq.png)

[diagram](./seqdiagram.png)
