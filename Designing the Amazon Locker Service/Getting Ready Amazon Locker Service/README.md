# Getting Ready: Amazon Locker Service
## Problem definition
Amazon is an online retail platform that allows its customers to place orders and buy products online. There are times when the customer is not available in the particular location to pick up the order. In such a case, Amazon Locker can be one of the most secure way of delivery.

Amazon Locker is also known as Amazon Hub or Amazon Hub Locker. It is a fully automated package delivery service provided by Amazon. Customers can choose any locker location as their delivery address and pick up the package from that location at no additional cost. In particular, when a customer places an order and chooses to get their item delivered to locker service, the system suggests the nearest available locker based on preferences. The order is packaged and placed in the locker. The customer gets the notification containing the code to open the locker, and they can pick up the package using that code within a valid amount of time. This is how the Amazon Locker service functions.

This problem is applicable to any retailer who wants to deliver goods safely to their customers.
[The Amazon Locker service]

## Expectations from the interviewee
The Amazon Locker service consists of multiple components. Each component has its own functionality and constraints. The following section provides an overview of some of the main expectations that the interviewer will want to hear you discuss in more detail during the interview.

### Locker size
Every locker is of a specific size in the Amazon Locker system. The interviewer expects you to ask questions listed below:

- Will every locker be of the same size?

- Is there any size restriction on an item that can be kept in the locker?

### Locker selection
The most significant part of the Amazon Locker service is the selection of the locker. The system has to make sure that more than one customer should not be able to access a locker at a single time. The interviewer expects you to ask the questions listed below to identify how the system will work in such situations:

- How will the system make sure that multiple customers do not get the same locker?

- Will the customer choose the locker of his own choice, or will the system assign him a locker based on availability?

- Can a customer get two lockers for different orders at the same time?

- Will the system keep in mind the locker and package sizes while assigning the locker to the customer?

### Locker status
Since this problem revolves around the locker, you may ask the questions listed below about the locker status:

- Is there any time constraint on the package that can be kept in the locker?

- What will happen if the customer does not come to pick up his package within the valid time period?

### Returning an item
Similar to the order delivery process, the item can also be returned through the Amazon Locker service. Therefore, you may ask the questions listed below:

- Can the customer return an item through the Amazon Locker service?

- If yes, will they get the same locker from which they picked up the item?

- How will the locker be assigned to the customer while returning an item?

## Design approach
We will design this Amazon Locker service using the bottom-up design approach. For this purpose, we will follow the steps below:

- Identify and design the simple components first, like the locker and item.

- Use these small components to design bigger components, such as the locker location and order that can be composed of multiple lockers and items, respectively.

- Repeat the steps above until we design the whole system.

## Design pattern
It is always a good practice to discuss the design patterns that the Amazon Locker service falls under, during the interview. Stating the design patterns will give the interviewer a positive impression and shows that the interviewee is well-versed in the advanced concepts of object-oriented design.

The following design patterns can be used to design the Amazon Locker service:

- Strategy design pattern

- Repository design pattern

Let's explore the requirements of the Amazon Locker service in the next lesson.
