# Class Diagram for LinkedIn
In this lesson, we’ll identify and design the classes, abstract classes, and interfaces based on the requirements we have previously gathered from the interviewer in our LinkedIn system.

## Components of LinkedIn
As mentioned earlier, we will design the LinkedIn system using a bottom-up approach.

### Account
The Account class identifies a LinkedIn user through their username and ID. Users with an account will have the option to create groups, pages, posts, comments, and like other comments and posts.

The class definition is represented below:

[The Account class](./account.png)

### Education, experience, and skill
The Education, Experience, and Skill classes provide relevant information and make up the Profile class.

These classes are represented below:

[The Education, Experience, and Skill classes](./experience.education.skill.png)

```
R1: Users should be able to add information to their profile including education, experiences, achievements, and skills.
```
### Recommendation, achievement, and analytics
The Recommendation, Achievement, and Analytics classes are used to provide relevant information and make up the Profile class.

These classes are represented below:

[The Recommendation, Achievement, and Analytics classes](./recommendation.achievement.analytics.png)

```
R1: Users should be able to add information to their profile including education, experiences, achievements, and skills.

R5: Users should be able to view their number of connections, profile views, post impressions, and search appearances.

R6: Users should be able to request and give recommendations to other users.
```

### Profile
The Profile class contains the personal information of a LinkedIn user—their profile, cover photo, experiences, education details, skills, and achievements.

The visual representation of the Profile class is given below:

[The Profile class](./profile.png)

```
R1: Users should be able to add information to their profile including education, experiences, achievements, and skills.
```

### Company page, job, and group
The CompanyPage class represents a particular page for a company that exists on LinkedIn. It contains the name, description, company size, etc.

The Job class contains information about a job posting at a specific company and current job openings.

The Group class represents a particular group that exists on the LinkedIn platform. This will contain the name, description, total users, and a particular ID to uniquely identify the group.

The representation of these classes is given below:

[The CompanyPage, Job, and Group classes](companyPage.job.png)

```
R11: Users should be able to create company pages. Users should be able to follow other company pages.

R12: Company pages should have a list of job openings that users can apply for.

R13: A user should be able to create and join groups.
```

### Post, comment, and message
The Post class indicates a post made by a user. It contains information regarding its content, the number of reacts and shares of the post, and the owner of the post.

The Comment class indicates a comment made by a user on a post. It includes information regarding its content, the number of reacts, and the owner of the comment.

The Message class represents the message sent by a user to other users. Therefore, it contains the content and multimedia elements like images or videos.

The representation of the classes is shown below:

[The Post, Comment, and Message classes](post.comment.message.png)

```
R7: Users should be able to write a new post.

R8: Users should be able to react, share, and comment on a post. They should also be able to react or comment on an existing comment.

R9: A user should be able to send and receive messages from other users.
```

### Connection invitation
The ConnectionInvitation class describes the details of a connection invitation. It will contain the status of the connection invite and the methods that indicate whether the request was accepted or ignored.

The class diagram of the ConnectionInvitation class is shown below:

[The ConnectionInvitation class](./connectionInvitation.png)

```
R3: Users should be able to send and cancel connection requests. They should also be able to respond to the connection requests of other users by either accepting or ignoring them.
```

### Person
The Person is an abstract class that contains details like the name, address, phone number, and email. It is derived into the Admin and the User class.

#### Admin

The Admin class is responsible for performing operations such as blocking or unblocking users.

#### User

The User class is the main class of LinkedIn. It is responsible for making various kinds of operations such as applying for jobs, sending messages or friend requests to other users, creating posts and pages or joining groups, and numerous other operations.

These three classes are represented below:

[The Person and its derived classes](./person.user.admin.png)

### Notification
The Notification class sends a notification using the built-in notification option. It is mainly responsible for sending notifications whenever any of the following conditions are met:

- A connection invitation is received.

- A new message is received.

- A new comment is added to a post that a user has created or is following.

- A new post has been created by a user or a company page that another user is following.

The UML representation of the class is shown below:

[The Notification class](./notification.png)

```
R10: The system should send a notification to the user to inform them about messages, connection requests, or comments on their post.
```
### Search interface and search catalog
The Search interface allows users to search for any particular user, company, group, and job opening. It also returns the list of respective components.

The search functionality is implemented using the SearchCatalog class. The catalog will contain a list of users, pages, and jobs, and can add new users, pages, and jobs to the catalog.

The representation of the SearchCatalog class and the Search interface is given below:

[The SearchCatalog class and the Search interface](./search.png)

```
R2: Users should be able to search for as well as view, pages, groups, and other users.
```

### Enumerations
The enumerations required in the LinkedIn design are provided below:

- AccountStatus: The account status tells us about the status of a user's account, i.e., whether it is active, deactivated, or blocked.

- ConnectionInviteStatus: The connection invite status describes the status of a connection invitation—whether it is pending, accepted, or ignored.

- JobStatus: The job status describes the current status of a job posting—whether it is open, on hold, or closed.

[Enums in LinkedIn](./enum.png)

### Custom data type
We need to create a custom data type, Address, which stores the location of a LinkedIn user.

[The Address custom data type](./address.png)

## Relationship between the classes
Now, we’ll discuss the relationships between the classes we have defined above in our LinkedIn system.

### Association
The class diagram has the following association relationships:

- The User class has a one-way association with the following:

    - Itself

    - The CompanyPage, Group, Job, Post, Comment, Message, and ConnectionInvitation classes

    - The Search interface

- The Notification class has a one-way association with the Message, Post, Comment, ConnectionInvitation, and Recommendation classes.

[The association relationship between classes](./interfaces.png)

### Composition
The class diagram has the following composition relationships:

- The Person class is composed of the Account class.

- The User class is composed of the Profile class.

- The Profile class is composed of Experience, Education, Skill, Achievement, Recommendation, and Analytics classes.

- The Post class is composed of the Comment class.

- The CompanyPage class is composed of the Job class.

[The composition relationship between classes](./inheritance.png)
### Inheritance
The following classes demonstrate an inheritance relationship:

- Both the Admin and User classes extend the Person class.
```
Note: We have already discussed the inheritance relationship between classes in the component section above one by one.
```
## Class diagram of LinkedIn
Here’s the complete class diagram for LinkedIn:

[The class diagram of LinkedIn](./map.png)

## Design pattern
We know that LinkedIn allows its users to follow company pages and join a group. By default, when a user follows or joins a page or group, they get notified of any new posts. To effectively map this behavior in our design, we can use the Observer design pattern.

All members of the page or group are set as subscribers, by default, on LinkedIn. Whenever there is a new activity, the system notifies the subscribers. The members also have the option to opt out of these notifications and to remove themselves from the subscriber list.

We have completed the class diagram of LinkedIn according to the requirements. Now, let’s design the sequence diagram of LinkedIn in the next lesson.
