# Class Diagram for Stack Overflow
In this lesson, we’ll identify and design the classes, abstract classes, and interfaces based on the requirements we have previously gathered from the interviewer in our Stack Overflow system.

## Components of Stack Overflow
As mentioned earlier, we will design the Stack Overflow system using a bottom-up approach.

### Account
The Account class is used to identify a Stack Overflow user using their username, email, and id. Users with an account will have the option to create questions and add answers and comments to questions.

Here's what the class definition looks like:

[The class diagram of the Account class](./account.png)

### Guest
The Guest class is a user that can only search and view questions and their answers. The user needs to register an account to ask questions or answer them.

The visual representation of the Guest class is provided below:

[The class diagram of the Guest class](./guest.png)

```
R1: Any guest can view questions and search questions by tag, username, or words
```

### Question
The Question class is used to enter the details of the question being asked by a user, such as its title, content, tags, etc. It can also allow users to add comments and bounties.

Here is what the class definition looks like:

[The class diagram of the Question class](./question.png)

```
R2: Users should be able to post new questions and add answers to an open question.

R4: A user can upvote, downvote, and add comments to a question or answer, while they can only upvote a comment.
```

### Answer
The Answer class represents a user's answer to a question asked and will contain elements like the content, upvotes, downvotes, etc.

The UML representation of the class is shown below:

[The class diagram of the Answer class](./answer.png)

```
R2: Users should be able to post new questions, as well as add an answer to an open question.

R4: A user can upvote, downvote, and add comments to a question or answer. However, they can only upvote a comment.
```

### Comment
The Comment class refers to an opinion or remark provided by a user on either a question or an answer. It can only be upvoted and flagged but not downvoted.

The UML representation of the class is shown below:

[The class diagram of the Comment class](./comment.png)

```
R4: A user can upvote, downvote, and add comments to a question or answer. However, they can only upvote a comment.
```

### Bounty
The Bounty class refers to an award of granting reputation points on a question to attract more attention from other users. It will have an expiry date of seven days and needs to stay on for a minimum of one day.

The class diagram of the Bounty class is shown below:

[The class diagram of the Bounty class](bounty.png)

```
R6: Any user can add a bounty to their question to attract more answers.
```
### Badge
The Badge class refers to badges on a user's profile that show a reputation-worthy user.

The class diagram of the Badge class is shown below:

[The class diagram of the Badge class](./badge.png)

```
R9: Users can earn badges for their helpful answers or comments.
```

### Tag and tag list
The Tag and TagList classes represent the keywords or labels to categorize questions. The TagList class will contain a key-value pair to keep track of the tags count.

The class diagram for these two classes is provided below:

[The class diagram of the Tag and TagList classes](./tag.png)

```
R10: The system should also be able to determine the most popular tags used in questions.

R11: Users can add tags to their questions. A tag is a word or phrase that describes the topic of the question.
```

### User
The User class is the main class of Stack Overflow and is responsible for making various kinds of operations such as creating, answering, and flagging questions, voting to delete or close questions, and various other operations.

The User class is the parent class of the following two classes:

- Admin

- Moderator

The details of these is provided below:

#### Admin
The Admin is responsible for performing operations such as blocking or unblocking users.

#### Moderator
The Moderator is responsible for performing operations such as closing, deleting, restoring, and reopening questions.

The class diagram of these classes is provided below:

The class diagram of User and its child classes

```
R2: Users should be able to post new questions and add answers to an open question.

R4: A user can upvote, downvote, and add comments to a question or answer. However they can only upvote a comment.

R7: Moderators can close a question or restore an already deleted question. Moderators can also delete answers.
```

### Notification
The Notification class will send a notification within the Stack Overflow platform whenever a new answer is added to a question asked by a user.

The UML representation of the class is shown below:

[The class diagram of the Notification class](./notification.png)

```
R8: The system should send the user a notification whenever there has been an interaction with them, such as the user’s question receiving an answer, earning a badge, or someone upvoting or downvoting their post.
```


### Search interface
The Search interface allows users to search for a particular question using tags, usernames, and a string of words.

The UML representation of the interfaces is shown below:

[The class diagram of the Search interface](./search.png)

```
R1: Any guest can view questions and search questions by tag, username, or words.
```

### Search catalog
The SearchCatalog is the class where the search functionality is implemented. The catalog will contain a list of questions that can be accessed using either the tags, usernames, or a string of words.

The class representation of the SearchCatalog class is provided below:

[The class diagram of the SearchCatalog class](./searchcatalog.png)

```
R1: Any guest can view questions and search questions by tag, username, or words.
```
### Enumerations
The enumerations required in the Stack Overflow design are provided below:

- AccountStatus: The account status tells us about the status of a user's account whether it is active, disabled, or blocked.

- QuestionStatus: The question status describes the status of an existing question, whether it is still active, closed, flagged, or bountied.

- ClosingDetails: The closing details enumeration outlines the reason that a question was closed.

[Enums in Stack Overflow](./enums.png)


## Relationship between the classes
Now, we are going to discuss the relationships between the classes we have defined above in our Stack Overflow system.


### Association
The class diagram has the following association relationships:

- The User class has a one-way association with the Question, Comment, Badge, Notification, and Search classes.

- The Guest class has a one-way association with the Search class.

- The Answer, Comment, Question classes have a one-way association with the Notification class.

[The association relationship between classes](./association.png)

### Composition
The class diagram has the following composition relationships:

- The Account class is composed of the User class.

- The Question class is composed of the Bounty, Comment, and Answer classes.

- The TagList class is composed of the Tag class.

[The composition relationship between classes](./composition.png)

### Generalization
The following classes show a generalization relationship:

- The SearchCatalog class implements the Search interface.

[The generalization relationship between classes](./generalization.png)

### Inheritance
The following classes show an inheritance relationship:

- Both Admin and Moderator extend the User class.
```
Note: We have already discussed the inheritance relationship between classes in the component section above one by one.
```

## Class diagram of Stack Overflow
[The class diagram of Stack Overflow](./classdiagram.png)

## Design pattern
We can use the Observer design pattern to implement the notification functionality. By default, users that post a question or answer are set as subscribers for that question or answer.

In addition, all users that choose to follow a question or answer also become subscribers. These users are added to a list of followers for both the question and answer. If there is a new activity for that question or answer, all subscribers are notified.

## Additional requirements
The interviewer can introduce some additional requirements in the Stack Overflow system, or they can ask some follow-up questions. Let’s see some examples of additional requirements:

Save questions or answers: Users can save questions or answers and view them later from the “Saves” section in their profile:

[The class diagram of save functionality in Stack Overflow](./additional.png)

We have completed the class diagram of Stack Overflow according to the requirements. Now, let’s design the sequence diagram of Stack Overflow in the next lesson.



