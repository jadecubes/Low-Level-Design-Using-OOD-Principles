# Getting Ready: Parking Lot
## Problem definition
A parking lot is a designated area for parking vehicles and is a feature found in almost all popular venues such as shopping malls, sports stadiums, offices, etc. In a parking lot, there are a fixed number of parking spots available for different types of vehicles. Each of these spots is charged according to the time the vehicle has been parked in the parking lot. The parking time is tracked with a parking ticket issued to the vehicle at the entrance of the parking lot. Once the vehicle is ready to exit, it can either pay at the automated exit panel or to the parking agent at the exit using a card or cash payment method.

[The layout of the parking lot]

## Expectations from the interviewee
In a typical parking lot system, there are several components each with specific constraints and requirements. The following section provides an overview of some major expectations the interviewer will want an interviewee to discuss in more detail during the interview.

### Payment flexibility
One of the most significant attributes of the parking lot system is the payment structure that it provides to its customers. An interviewer would expect you to ask questions like these:

- How are customers able to pay at different exit points (i.e., either at the automated exit panel or to the parking agent) and by different methods (cash, credit, coupon)?

- If there are multiple floors in the parking lot, how will the system keep track of the customer having already paid on a particular floor rather than at the exit?

### Parking spot type
Another topic of discussion that an interviewer would expect you to be aware of is the different parking spot types—handicapped, compact, large, and motorcycle—regarding which you can ask the following questions:

- How will the parking capacity of each lot be considered?

- What happens when a lot becomes full?

- How can one keep track of the free parking spots on each floor if there are multiple floors in the parking lot?

- How will the division of the parking spots be carried out among the four different parking spot types in the lot?

### Vehicle types
Similar to the parking spot, an interviewer would also expect you to discuss the different vehicle types—car, truck, van, motorcycle—which can have the following set of questions:

- How will capacity be allocated for different vehicle types?

- If the parking spot of any vehicle type is booked, can a vehicle of another type park in the designated parking spot?

### Pricing
We touched upon the payment structure offered by the parking lot system. Now, the pricing model needs to be clarified from the interviewer, and therefore you may ask questions like these:

- How will pricing be handled? Should we accommodate having different rates for each hour? For example, customers will have to pay $4 for the first hour, $3.5 for the second and third hours, and $2.5 for all the subsequent hours.

- Will the pricing be the same for the different vehicle types?

## Design approach
We are going to design this parking lot system using the bottom-up design approach. For this purpose, we will follow the steps below:

- Identify and design the smallest components first, like, the vehicle and parking spot types.

- Use these small components to design bigger components, for example, the payment system at the exit.

- Repeat the steps above until we design the whole system like the parking lot.

## Design pattern
It is always a good practice to discuss the design patterns that a parking lot system falls under, during the interview. Stating the design patterns will give the interviewer a positive impression and shows that the interviewee is well-versed in the advanced concepts of object-oriented design. The following design patterns can be used to design the parking lot system:

- Singleton design pattern

- Abstract Factory design pattern

- Factory design pattern
