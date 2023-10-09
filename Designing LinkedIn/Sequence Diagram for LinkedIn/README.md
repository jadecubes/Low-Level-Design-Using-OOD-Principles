# Sequence Diagram for LinkedIn
Sequence diagrams are a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for LinkedIn. In this lesson, we’ll create sequence diagrams for the following interaction:

- Send a connection invitation: A user sends a connection invitation to another user.

## Send a connection invitation
The sequence diagram for sending a connection invitation should have the following actors and objects that will interact with each other:

- Actors: UserA and UserB

- Objects: SearchCatalog and ConnectionInvitation

Here are the steps for the send a connection invitation interaction:
1. User A searches for user B in the catalog.

2. If User B exists:

    I. The catalog returns user B.

    II. User A adds user B as a connection.

    III. The connection invitation is sent to user B.

    IV. If the invitation is accepted:

        i. User B is added to user A's connections.

        ii. User A gets a notification that the connection invitation has been accepted.

    V. Else, the invitation is ignored.

3. Else, if user B does not exist:

I. User A receives a "user not found" error.

Based on the order above, the sequence diagram for sending a connection invitation on LinkedIn is given below:

[The sequence diagram for sending a connection invitation]
