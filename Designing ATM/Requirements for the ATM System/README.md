# Requirements for the ATM System
In this lesson, we’ll list the requirements of the ATM design. This is a very crucial step, since requirements define the scope of a problem. Therefore, getting them right from the interviewer and understanding them well will make the design of the rest of the system smooth and easy.

We’ll use the notational convention to identify each requirement with a unique label, "Rn" where "R" is short for Requirement, and "n" is a natural number.


# Requirement collection
R1: Each user has a single account at the bank that they can access by inserting their card into the ATM.

R2: The main components of the ATM system that facilitate interactions between the user and the machine are listed below:

- Card reader: To read the user's ATM card

- Keypad: To enter information such as the user's PIN

- Screen: To display messages to the user, such as prompts or error messages

- Cash dispenser: To dispense cash to the user

- Printer: To print receipts for the user

- Network infrastructure: To connect with the bank's computer system in order to access account information and complete transactions

R3: The ATM system must authenticate the user based on the PIN they enter to ensure that only authorized users can access their accounts.

R4: All transactions are possible after the successful authentication of the ATM card.

R5: The user can have two types of accounts—current and savings—and can perform the following operations on the ATM:

- Balance inquiry

- Cash withdrawal

- Funds/money transfer

R6: At the end of a transaction, the user has the option to start another transaction or end their session.

[ATM components](./atm.png)

We've identified our requirements for the problem. Let’s define different use cases of the ATM system in the next lesson.
