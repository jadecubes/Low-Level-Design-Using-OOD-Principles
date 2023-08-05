# Getting Ready: The ATM System
## Problem definition
An Automated teller machine (ATM) allows a bank customer to perform financial transactions remotely without the need for a teller or a bank branch. These transactions include deposits, withdrawals, balance inquiries, and account transfers. ATMs are located in convenient locations such as banks, grocery stores, airports, and other public places.

To use an ATM, users need a bank card associated with an account at a financial institution to use an ATM. To access their account, users must also know the personal identification number (PIN). The user can follow the prompts on the ATM's screen to complete the desired transaction with the PIN.

## Expectations from the interviewee
There are several components in an ATM design, each with specific constraints and requirements. The following provides an overview of some of the main expectations that the interviewer will want to hear you discuss in more detail, during the interview.

### ATM components
To better understand an ATM system, you may ask the interviewer the following questions:

1. What are the components of an ATM?

2. Is the ATM necessarily placed inside a room?

3. Does an ATM have a fingerprint scanner?

### ATM features
Different ATMs may vary in terms of features which is why it is important to clear the following questions from the interviewer:

1. What is the withdrawal limit of an ATM?

2. Can we check our account balance using an ATM?

3. Can we set a PIN using an ATM?

### ATM processing
The interviewer would expect you to ask a question regarding the processing of transactions using an ATM. Therefore, you may ask the following questions:

1. What happens when the amount entered by the user for withdrawal is greater than the user's account balance?

2. What happens when the amount entered by the user for withdrawal is greater than the ATM's cash limit?

3. What happens when the amount entered by the user exceeds the total cash present in the ATM?

4. Can the ATM be used for online transactions?

## Design approach
We are going to design this ATM system using the bottom-up design approach. For this purpose, we will follow the steps below:

- Identify and design the smallest components first—the screen, keypad, cash dispenser, printer, and card reader.

- Use these small components to design bigger ATM components—the state, machine, and room.

- Repeat the steps above until we design the whole ATM system.

## Design patterns
It is always a good practice to discuss the design patterns under which the ATM system falls, during the interview. Stating the design patterns will give the interviewer a positive impression and shows that the interviewee is well-versed in the advanced concepts of object-oriented design.

The following design patterns are used to design the ATM system:

- The Singleton design pattern

- The State design pattern

Let's explore the requirements of the ATM system in the next lesson.
