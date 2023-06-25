# Requirements for the Vending Machine
In this lesson, we’ll list down the requirements of our vending machine problem. This is a very crucial step as requirements define the scope of a problem, so getting them right from the interviewer and understanding them well will make the design of the rest of the problem smooth and easy.

We’ll use the notational convention to identify each requirement with a unique label "Rn", where "R" is short for Requirement and "n" is a natural number.

## Requirement collection
The requirements for the vending machine problem are defined below:

R1: There are different products placed at different positions in the vending machine.

R2: The vending machine can be in one of these three states:

- NoMoneyInsertedState: There is no money inserted into the machine.

- MoneyInsertedState: Money is inserted into the machine.

- DispenseState: The machine gives out the product.

R3: There can be two actors in the system. One is the user and the other is the admin.

R4: The admin can add a product to the machine or remove a product from the machine.

R5: The system should allow the users to select a product they want to purchase from the machine by specifying the rack number.

R6: The user can insert money into the machine in the form of cash.

R7: The system should be able to calculate the money inserted into the machine.

R8: The system should check whether the user inserted the exact amount required for the specific product into the machine.

R9: If the amount is greater than the product price, the system should change back the user and dispense the product.

R10: If the amount is less than the product price, the system should display an error message and return the money.

We've identified our requirements for the problem, and in the next lesson, we will define the class diagram of our vending machine system.
