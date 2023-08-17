# Getting Ready: Stack Overflow

## Problem definition
Stack Overflow is a Q&A website for programmers and developers, irrespective of their expertise level in the domain. It has a wide variety of questions on topics related to computer science and programming. Registered users can post new questions and answer questions from other users. Each user can collect reputation points. These points are affected by the upvotes or downvotes received by the user on their questions or answers. More reputation points allow users to perform additional functions like voting to close or delete a question. On achieving reputation milestones, users are awarded badges to highlight their credibility.

[A question page on the Stack Overflow](./stackoverflow.png)

## Expectations from the interviewee
It is important to narrow down the components to be included in your Stack Overflow design. The following section provides an overview of some of the main expectations that the interviewer will want to hear you discuss in more detail during the interview:

### Discoverability
You may want to ask the interviewer the following to get a better understanding of how Stack Overflow's discoverability works:

- How are users able to search for questions?

- Is there a way to filter questions using tags or users?

### Reputation
Reputation points affect user privileges. Therefore, it's important to ask the interviewer the following aspects of reputation points:

- How are reputation points calculated? Do users get points for asking or answering questions?

- How many points are required for users to get a moderator access?

### Voting
Voting is one of the main features of Stack Overflow. It gives insight on which questions or answers are more popular among users. Make sure to ask the following questions to understand how voting works in Stack Overflow:

- What are the different types of voting allowed on Stack Overflow? Are you allowed to upvote and downvote?

- How does voting work when a question has to be closed and deleted? Which user can vote in such circumstances?

### Bounty
Bounty is a special reputation placed on a question that is not being noticed or answered. Any user that answers a bounty question receives reputation points equal to the bounty value. You need to clarify the bounty requirements from the interviewer by asking the following questions:

- How are reputation points awarded on bounty questions?

- When do users start a bounty? How long does a bounty last before expiring?

## Design approach
We’ll design Stack Overflow using the bottom-up design approach. For this purpose, we’ll follow the steps below:

- Identify and design the smallest components first, like a question and answer.

- Use these small components to design additional components, for example, comments, bounty, and tags.

- Repeat the steps above until we design the complete Stack Overflow platform.

## Design pattern
It is always a good practice to discuss the design patterns that the Stack Overflow falls under, during the interview. Stating the design patterns will give the interviewer a positive impression and shows that the interviewee is well-versed in the advanced concepts of object-oriented design.

- The following design pattern is used to design Stack Overflow:

- Observer design pattern

Let’s explore the requirements of Stack Overflow in the next lesson.
