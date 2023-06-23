# Sequence Diagram for the Amazon Locker Service
Sequence diagrams are a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for our Amazon Locker system. In this lesson, we will create sequence diagrams for the following interaction.

## Return package
The sequence diagram for the package return should have the following actors and objects that will interact with each other:

- Actor: Customer

- Object: Locker

- System

Here are the steps in the return package interaction:

1. The customer requests the system to return a package.

2. If the package return request is approved:

    I. The system requests an available locker.

    II. The locker is returned to the system.

    III. The system sends an OTP code to the customer.

    IV. The customer verifies their code.

     V. If verification is successful:

        i. The system assigns a locker to the customer.

        ii. The customer places their package in the locker.

     VI. Else:

         i. The customer receives an error message.

3. Else, if the package return request is not approved:

    I. The customer is informed that the return request is not approved.

Based on the order above, the sequence diagram of package return in the Amazon Locker system is given below:

[The sequence diagram for returning a package]

Next, let's look at the activity diagrams for the Amazon Locker system to understand the control flow of the system.
