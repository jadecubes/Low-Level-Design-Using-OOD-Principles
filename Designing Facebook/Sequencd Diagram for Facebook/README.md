# Sequence Diagram for Facebook

Sequence diagrams are a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for Facebook. In this lesson, we will create sequence diagrams for the following interaction:

- Send a friend request: A user sends a friend request to another user.

## Send a friend request
The sequence diagram for sending a friend request should have the following actors and objects that will interact with each other:

Actors: User A and User B

Objects: Catalog and FriendRequest

Here’re the steps for the “send a friend request” interaction:

1. User A searches for user B in the catalog.

2. If User B exists:

    I. The catalog returns user B

    II. User A adds user B as a friend.

    III. The friend request is sent to user B.

    IV. If the request is accepted:

        i. User B is added to user A's friend list.

        ii. User A gets a notification that the friend request has been accepted.

    V. Else, the request is rejected.

3. Else, if user B does not exist:

    I. User A receives a "user not found" error.

Based on the order above, the sequence diagram for sending a friend request on Facebook is given below:

[The sequence diagram for sending a friend request](./seq.png)
