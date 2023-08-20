# Getting Ready: An Online Stock Brokerage System
## Problem definition
An online stock brokerage system acts as as an intermediary between the buyer and seller during the trade of the stocks. The system facilitates its users to buy and sell stocks online. It enables users to monitor and carry out their transactions and displays performance graphs for the various stocks in their portfolios. It also offers protection for client transactions and notifies them when stock changes reach certain levels.

The automated online stock brokerage system uses computers and the internet to speed up and reduce the cost of traditional stock trading. Additionally, this method provides quicker access to stock information, current market trends, and current stock prices.

## Expectations from the interviewee
An online stock brokerage system consists of multiple components. Each component has its own functionality and constraints. The following section provides an overview of some of the main expectations that the interviewer will want to hear you discuss in more detail during the interview.

### Discoverability
For an online stock brokerage system, discoverability is one of the key features. You can ask the following questions to know more about the system:

- How do the members search the stock inventory?

- How will the search surface result?

### Visibility
To get a better understanding of how the data is visible to the different users, you may ask the following questions:

- Can every member see the current levels of stock positions at any time?
  
### Order type
You may ask the interviewer about the types of orders the system should be able to handle by simply asking the question listed below:

- How many types of stock trade orders are the users able to place, for example, a market order, loss order, etc?


### Multiplicity
You may ask the interviewer questions related to the multiplicity of the system. These questions are listed below:

- Can the members have multiple watchlists containing multiple stock quotes?

- Can a member buy multiple lots of the same stock at different times?

## Design approach
We'll design this online stock brokerage system using the bottom-up design approach. For this purpose, we will follow the steps below:

- Identify and design the simple components first, like the stock and stock position.

- Use these small components to design bigger components, such as the order and stock inventory that can be composed of multiple stock items.

- Repeat the steps above until we design the whole stock brokerage system.

## Design patterns
It is always a good practice to discuss the design patterns that the online stock brokerage system falls under, during the interview. Stating the design patterns will give the interviewer a positive impression and shows that the interviewee is well-versed in the advanced concepts of object-oriented design.

The following design patterns can be used to design the online stock brokerage system:

- Singleton design pattern

- Observer design pattern

Let's explore the requirements of the online stock brokerage system in the next lesson.
