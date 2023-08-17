# Sequence Diagram for Stack Overflow

Sequence diagrams are a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for Stack Overflow. In this lesson, we will create sequence diagrams for the following two interactions:

- Close question: A user votes to close a question authored by a different user.

- Sequence challenge: A user creates a question and adds a bounty.

## Close question
The sequence diagram for closing a question should have the following actors and objects that will interact with each other:

- Actors: User and Author

- Object: Question

Here are the steps in the close question interaction:

1. A user votes to close a question with some remark.

2. If the user is a moderator:

    I. The question is closed.

    II. The author of the question is notified about the question.

3. Else if they are a regular user:

    I. If the user's reputation is greater than or equal to 3000:

        i. A close vote is added.

        ii. If there are 3 close votes, the question closes, and the author is notified.

    II. Else if the user's reputation is less than 3000:

        ii. The vote is considered invalid.

Based on the order above, the sequence diagram for closing a question in Stack Overflow is provided below:

[The sequence diagram for closing a question](./seq1.png)

## Sequence challenge: Create question

[The sequence diagram for creating a question](./seq2.png)

[flow](./flow.png)

[Answer](./answer.png)
