# Use Case Diagram for Stack Overflow
Let’s build the use case diagram of Stack Overflow and understand the relationship between its different components.

First, we’ll define the different elements of our Stack Overflow system, followed by the complete use case diagram of the system.

## System
Our system is "Stack Overflow."

## Actors
Now, we’ll define the main actors of Stack Overflow.


### Primary actors
- User: This actor can create, answer, and flag questions. This actor can add bounty, tags, and comments to questions, and vote to close or delete questions or answers.

### Secondary actors
- Guest: The guest can only search and view questions and their answers but needs to register an account to ask and answer questions.

- Admin: The admin is in charge of performing numerous operations, such as blocking or unblocking users.

- Moderator: The moderator is in charge of performing numerous operations, such as closing, reopening, deleting, and restoring questions.

- System: This is responsible for awarding badges to users and sending out notifications whenever a new answer is added to a question asked by a user.

## Use cases
In this section, we’ll define the use cases for Stack Overflow. We have listed the use cases according to their respective interactions with a particular actor.
```
Note: You will see some use cases occurring multiple times because they are shared among different actors in the system.
```
### User
- Login/Logout: To log in or log out from the Stack Overflow account

- Reset password: To reset the password of the Stack Overflow account

- Add/modify/flag question: To create a new question or modify or flag an existing question

- Add/modify/flag answer: To create a new answer or modify or flag an existing answer

- Add comment: To add a comment to a question or answer

- Vote to close/delete question: To vote to either close or delete an existing question

- Upvote/downvote: To either offer support or register disapproval for a post

### Guest
- Search/view question: To search for a question from Stack Overflow and view its contents

- Register account: To register an account

### Admin
Block/unblock user: To block or unblock a user

### Moderator
- Close/reopen/delete/restore question: To close or delete an existing question, reopen a closed question or restore a deleted question

- Delete answer: To delete an existing answer

### System
- Award badge to a user: To award an earned badge to a user

- Send notification: To send a notification if any new answer or comment is added to a question followed by a user, and if there is an upvote or downvote on a question/answer

## Relationships
We describe the relationships between and among actors and their use cases in this section.


### Generalization
- "Moderator" has a generalization relationship with "User" as the moderator can perform all those tasks that a normal user can perform.

- "User" has a generalization relationship with "Guest" as the normal user can perform all those tasks that a guest user can perform.
### Associations

The below table shows the association relationship between actors and their use cases.
```
User                        Guest                        Admin                    Moderator                               System

Search/view question        Register account             Block/unblock user       Search/view question                    Award badge to user

Login/Logout                Search/view question                                  Login/Logout                            Send notification

Reset password                                                                    Reset password

Add/modify/flag question                                                          Add/modify/flag question

Add/modify/flag answer                                                            Add/modify/flag answer

Add comment                                                                       Add comment

Upvote/downvote                                                                   Upvote/downvote

Vote to close/delete question                                                     Close/reopen/delete/restore question

                                                                                  Delete answer
```

### Include
The “Send notification” use case also has an include relationship with the “Add answer,” “Add comment,” and “Add question” use cases, since a notification is sent whenever an interaction is made for any of these.

### Extend
- The “Modify question” use case has an extend relationship with the “Modify tag” and “Modify bounty” use cases, since the modification of a question can involve the steps to modify the tags and bounties.

- The “Add question” use case has an extend relationship with the “Add bounty” and “Add tag” use cases, since a user can either add a bounty or tag when creating a question.

- The “Modify question” use case also has an extend relationship with the “Add tag” and “Add bounty” use cases, since a user can decide to add tags and bounties after creating a question as well.

## Use case diagram

[The use case diagram for Stack Overflow](./ucd.png)
