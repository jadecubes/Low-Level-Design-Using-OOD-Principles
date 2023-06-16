# Sequence Diagram for the Elevator System
A sequence diagram is a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for our elevator system. In this lesson, we will create sequence diagrams for the following two interactions:

- Elevator call: The passenger calls the elevator.

- Sequence challenge: The passenger rides the elevator to a floor.

## Elevator call
The sequence diagram for an elevator call should have the following actors and objects that will interact with each other:

- Actor: Passenger

- Objects: HallButton, HallButton, ElevatorSystem, Dispatcher, ElevatorCar, and Door

Here are the steps in the elevator call interaction:

1. The passenger presses the hall button to call the elevator.

2. The hall button signals the elevator system to call an elevator car to the passenger's floor.

3. The elevator system informs the dispatcher to select the best car.

4. The dispatcher returns the best car to the system.

5. The elevator system signals the elevator car to move to the passenger's floor.

6. The elevator car signals the system when it arrives on the floor.

7. The system signals the hall button that the elevator has arrived.

8. The hall button is unpressed.

9. The elevator system signals the doors to open.

10. The door opens for the passenger.

11. Based on the order above, the sequence diagram for an elevator call in the elevator system is given below.

[The sequence diagram for an elevator call]

## Sequence challenge: Elevator ride
You will complete a sequence diagram for an elevator ride from one floor to another. A skeleton of the sequence diagram for an elevator ride is given below:

[The sequence diagram for an elevator ride]

Notice that the arrows in the diagram above are numbered from 1 to 9. The message boxes shown below are the messages to be exchanged between the actor(s) and object(s). Can you rearrange the messages below in the correct sequence of order they should appear in the skeleton of the sequence diagram above?

Next, let’s look at the activity diagrams for the elevator system to understand the control flow of the system.

