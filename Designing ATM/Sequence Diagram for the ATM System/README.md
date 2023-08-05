# Sequence Diagram for the ATM System
A sequence diagram is a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for our ATM. For the sake of this lesson, we will create sequence diagrams for balance inquiry from ATM.


## Balance inquiry
The sequence diagram for how to complete the balance inquiry using an ATM should have the following actors and objects that will interact with each other:

- Actors: Cardholder, Card issuer

- Objects: ATM and Printer

Here are the steps for balance inquiry from ATM:

1. The cardholder inserts their ATM card into the ATM.

2. The ATM then asks the cardholder for their PIN.

3. The cardholder enters their PIN code, and the ATM sends the code to the card issuer for verification.

4. The card issuer verifies the PIN code:

I. If the PIN is valid, the card issuer sends a message back to the ATM indicating that the verification was successful.

    i. The ATM then displays the main menu to the cardholder.

    ii. The cardholder selects the balance inquiry option.

    iii. The ATM sends a message to the card issuer to get the account balance, and the card issuer returns the balance to the ATM.

    iv. The ATM displays the balance to the cardholder and asks if they would like a receipt printed.

        i. If the cardholder selects "yes," the ATM sends a message to the printer to print a receipt and ejects the ATM card.

        ii. If the cardholder does not want a receipt, the ATM card is simply ejected.

II. If the PIN is not verified, and the ATM card is simply ejected.

Based on the order above, the sequence diagram of balance inquiry from ATM is given below.

[The sequence diagram for how to complete a balance inquiry from an ATM]

In the next lesson, we will create activity diagrams for the ATM.


