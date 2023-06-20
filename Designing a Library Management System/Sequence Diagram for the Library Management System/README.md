# Sequence Diagram for the Library Management System

Sequence diagrams are a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for our library management system. For the sake of this lesson, we will create sequence diagrams for the following two interactions:

- Lend a book: The member requests the librarian to lend them a book.

- Sequence challenge: The member returns a book.

## Issue a book
The sequence diagram for issuing a book should have the following actors and objects that will interact with each other:

- Actors: Member and Librarian

- Object: Book

Here are the steps in the sequence to issue a book:

1. The member requests to issue a book.

2. The librarian verifies the lending quota of the member.

3. If the lending quota is equal to the maximum quota:

    I. The librarian informs the member that the maximum quota is reached. No more books can be issued.

4. Else if the lending quota is less than the maximum quota:

    I. The librarian gets the book status.

    II. If the book is available:

        i. The librarian issues the book to the member.

    III. If the book is reserved:

        i. The librarian cancels the member’s request to issue the book.

Based on the order above, the sequence diagram below demonstrates the issuance of a book in the library management system.

[The sequence diagram for issuing a book](./issuebook.png)

## Sequence challenge: Return a book
You will complete a sequence diagram for the return of a book to the library. The sequence diagram below demonstrates a skeleton for the return of a book to the library.

[The sequence diagram for returning a book](./returnbook.png)

Notice that the arrows in the above diagram are numbered from 1 to 13. The message boxes shown below are the messages to be exchanged between the actor(s) and object(s). Can you rearrange the below messages in the correct sequence of order they should appear in the sequence diagram’s skeleton above?
```
Note: If you get stuck, just click the “Show Solution” button to check out the correct answer.
```

[rearrange](./process.png)

[answer](./answer.png)

In the next lesson, we will create activity diagrams for our library management system.


