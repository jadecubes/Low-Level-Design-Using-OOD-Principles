# Getting Ready: The Hotel Management System
## Problem definition
The hotel management system is a software used to manage all hotel activities efficiently and smoothly. Almost all popular hotels have an online management system to digitize the process of booking rooms, managing staff, and performing other necessary hotel management features. Through this system, the notification and payment process is made flexible and automated. In the hotel, there is usually a fixed number of rooms, and the booking system has information about all rooms present and their availability.

For the hotel manager, controlling all the hotel activities manually is a difficult task. With the help of an online hotel management system, the manager can keep track of rooms, customers, and workers through a single portal. The manager can also post available rooms to the system and generate bills. The system also allows customers to search for and book a room of their choice and cost range. The system provides complete information about rooms to the customers so they can view the available rooms and book them online. The guest is charged on the basis of the time duration the hotel room is booked. In this way, the system facilitates both customers and the manager of the hotel.

## Expectations from the interviewee
Numerous components are present in the hotel management system, each with specific constraints and requirements placed on them. The following provides an overview of some of the main things that the interviewer will want to hear you discuss in more detail during the interview.

### Room booking
Booking a room is an essential part of the hotel management system. The system has to ensure that no two people can book the same room. The interviewer expects you to ask questions to identify how the system will work in such situations:

- How will the system ensure that multiple users do not book the same room?

- What type of users are allowed to book a room in the hotel?

- Can users book a room in advance?

### Payment handling
One of the hotel management system's most significant attributes is its payment structure to its customers. This can vary, so the interviewer would expect you to ask the questions listed below:

- What payment methods can the customer use (for example, credit card or cash)?

- How is the payment performed? Does the customer pay online or through a receptionist at the hotel?

- Will the customer be able to pay in advance for a room booking, or is a just-in-time(JIT) payment system available?


### Price variance
We touched upon the payment methods of the hotel management system. Now, the pricing model needs to be clarified by the interviewer. Therefore, you may ask the questions listed below:

- How will the booking price be calculated? Or which factors affect the price of a room in the hotel?

- How does the location and size of the room affect its price?

- How does the booking duration affect the payment?

### Booking cancelation
There will be many duplicate instances in our system. The interviewer expects you to ask the questions provided below:

- Can the user cancel a room booking?

- Which type of users are allowed to request a room booking cancelation?



## Design approach
We’ll design this hotel management system using the bottom-up design approach. For this purpose, we will follow the steps below:

- Identify and design the smallest components first, such as a room.

- Use these small components to design bigger components, such as building a hotel that can be composed of multiple rooms.

- Repeat the steps above until we design the whole hotel management system.
## Design pattern
It is always a good practice to discuss the design patterns that a hotel management system falls under, during the interview. Stating the design patterns will give the interviewer a positive impression and shows that the interviewee is well-versed in the advanced concepts of object-oriented design.

The following design patterns can be used to design the hotel management system:

- Strategy design pattern

- Singleton design pattern

- Factory design pattern

Let’s explore the requirements of the hotel management system in the next lesson.
