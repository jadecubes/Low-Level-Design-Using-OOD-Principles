# Getting Ready: Vending Machine
## Problem definition
A vending machine is an automated machine. The machine provides items, including snacks, chocolates, and beverages to consumers. There are multiple racks inside the vending machine with products on each rack. A user inserts money into the machine, selects the rack number from which they want to buy a product, and presses the button. A vending machine dispenses the product to the users based on the amount of money inserted and the selection of the product.

Modern vending machines were first developed in England in the early 1880s and dispensed postcards. Today, there are specialized vending machines that provide specific products. The vending machine is a 24x7 standalone unit that requires a standard power supply connection to function. It consists of electromechanical systems that help automate the entire vending process. Therefore, its basic function is to flawlessly issue users with a diverse range of products.

The diagram below elaborates on the process of product purchasing using the vending machine:

[Vending](./process)

## Expectations from the interviewee
Although the vending machine problem is a simpler design problem asked in interviews, the interviewer still has some expectations. The following provides an overview of what the interviewer wants to hear you discuss in more detail during the interview.

### States of the vending machine
An interviewer would also expect you to discuss the different states of the vending machine. You may ask the following set of questions:

- What function do the vending machines perform? Alternatively, how many different states can the vending machines have?

- After inserting money into the machine, what does the system do?

- Who presses the vending machine button, and what happens after pressing it?

- What does the dispense function do?

- If the vending machine is in a dispense state, is it possible to insert money?

- If you are in NoMoneyInsertedState and try to select a product without paying money, would you be able to select a product?

### Money handling
One of the most significant attributes of the vending machine system is how it receives, calculates, and returns money. You may ask the interviewer the questions listed below:

- What should the system do if we pay less money than the product price?

- What should the system do if we pay more money than the product price?

- Can the credit card be used to input money or can only cash be used?

## Design approach
We’ll design this vending machine problem using the bottom-up design approach. For this purpose, we’ll follow the steps below:

- Identify and design the smallest components first, like, a product in the machine.

- Use these small components to design bigger components, for example, the inventory.

- Repeat the steps above until we design the whole system, which is the vending machine.

## Design patterns
It is always a good practice to discuss the design patterns that the vending machine falls under, during the interview. Stating the design patterns will give the interviewer a positive impression and shows that the interviewee is well-versed in the advanced concepts of object-oriented design.

The following design pattern is used to design the vending machine:

- State design pattern

- Singleton design pattern

Let’s explore the requirements of the vending machine problem in the next lesson.
