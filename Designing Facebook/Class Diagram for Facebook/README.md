# Class Diagram for Facebook
## Components of Facebook
As mentioned earlier, we will design the Facebook social network using a bottom-up approach.

### Account
The Account class identifies a Facebook user using their username and ID. Users with an account will have the option to create groups, pages, posts, comments, and like other comments and posts.

A representation of the class definition is provided below:

[The class diagram of the Account class](./account.png)

```
R1: Users should be able to set the privacy of their profile page. They should also be able to create their profile page and add information such as work experience, education, and place of living.
```

### Admin
The Admin class comes into existence in a group or page created and is responsible for performing operations such as blocking or unblocking users, enabling or disabling pages.

The class diagram of this class is shown below:

[The class diagram of the Admin class](./admin.png)

```
R10: Users should be able to create their own groups and pages. Users can later set privacy or delete the groups or pages they own.
```

### Person
The Person class contains details like the name, address, phone number, and email. It is derived into the User class.

#### User
The User class is the main class of Facebook and is responsible for making various kinds of operations such as sending messages or friend requests to other users, creating or joining groups or pages, and numerous other operations.

The class diagram of these two classes are provided below:

[The class diagram of the Person and User classes](./user.[ng)

```
R4: Users should be able to send as well as respond to friend requests of other users. Users should also be able to unfriend or block other users.

R8: A user should be able to send messages and receive messages from other users.

R9: Users should be able to follow existing pages and join existing groups. They should also be able to unfollow or leave joined groups or followed pages.
```

### Profile
The Profile class contains the personal information of a Facebook user, like their profile and cover pictures, their work and education details, and the list of places they’ve visited.

The visual representation of the Profile class is given below:

[The class diagram of the Profile class](./profile.png)

```
R1: Users should be able to set the privacy of their profile page. They should also be able to create their profile page and add information such as work experience, education, and place of living.
```

### Work, education, and places
The Work, Education, and Places classes are used to provide relevant information and are involved in the Profile class.

The class representation of these classes is given below:

[The class diagram of the Work, Education, and Places classes](,/work.png)

```
R1: Users should be able to set the privacy of their profile page. They should also be able to create their profile page and add information such as work experience, education, and place of living.
```
### Page
The Page class represents a particular page that exists on the Facebook platform that will contain the name, description, likes count, and a particular ID to uniquely identify the page.

The UML representation of the class is shown below:

[The class diagram of the Page class](./page.png)

```
R9: Users should be able to follow existing pages and join existing groups. They should also be able to unfollow or leave joined groups or followed pages.
```

### Group
The Group class represents a particular group that exists on the Facebook platform. This will contain the name, description, total users, and a particular ID to uniquely identify the group. In addition, it will have methods, using which, new users can be added to the group, and the group’s description can be updated.

The UML representation of the class is shown below:

[The class diagram of the Group class](./group.png)

```
R9: Users should be able to follow existing pages and join existing groups. They should also be able to unfollow or leave joined groups or followed pages.
```

In the Facebook design problem, the Group class implements the GroupFunctions interface.

[The GroupFunctions interface as a subscriber](./groupfunctions.png)

### Post
The Post class indicates a post by any user that will contain its content, the number of likes and shares the post has, as well as the owner of the post. Each post will have a specific setting as to who can view the post.

The class diagram of the Post class is shown below:

[The class diagram of the Post class](./post.png)

```
R3: Users should be able to write a new post and set its privacy.
```

### Comment
The Comment class indicates a comment by any user on a post that will contain its content, the number of likes, and the owner of the comment.

The class diagram of the Comment class is shown below:

[The class diagram of the Comment class](./comment.png)

```
R6: Users should be able to like, share and/or comment on a post, they should also be able to like or comment on an existing comment.
```

### Friend request
The FriendRequest class describes the details of a friend invitation. It will contain the status of the friend invite and the methods that indicate whether the request was accepted or rejected.

The class diagram of the FriendRequest class is shown below:

[The class diagram of the FriendRequest class](./friendrequest.png)

```
R4: Users should be able to send as well as respond to the friend requests of other users. Users should also be able to unfriend or block other users.
```

### Message
The Message class represents the message sent by a user to other users and will, therefore, contain the content and the multimedia elements like images or videos.

The class diagram for the Message class is shown below:

[The class diagram of the Message class](./message.png)

```
R8: A user should be able to send messages and receive messages from other users.
```

### Profile privacy
There will be a privacy class for the profile on Facebook. The following represents the class diagram:

[The Class diagram of the ProfilePrivacy class](profileprivacy.png)

```
R1: Users should be able to set the privacy of their profile page. They should also be able to create their profile page and add information such as work experience, education, and place of living.

R3: Users should be able to write a new post and set its privacy.
```

### Notification
The Notification class will be a class, since it can send a notification using the built-in notification option. It is mainly responsible for sending notifications whenever any of the following conditions are met:

A friend request is received.

A new message is received.

A new comment is added to a post that a user has created or is following.

A new post has been created either by a user or a page that another user is following.

The UML representation of the class is shown below:

[The class diagram of the Notification class](./notification.png)

```
R7: The system should send the user a notification whenever there has been an interaction with them, such as receiving a message, a friend request, or a comment on their post.
```

### Interfaces implemented by the user
There will be several interfaces that will exist in the Facebook class, and each will play a separate role in implementing different functionality. The following provides an overview of these:

- PageFunctionsByUser: This interface will contain the functions that a user will perform while interacting with pages.

- GroupFunctionsByUser: This interface will contain the functions that a user will perform while interacting with groups.

- PostFunctionsByUser: This interface will contain the functions that a user will perform while interacting with posts.

- CommentFunctionsByUser: This interface will contain the functions that a user will perform while interacting with comments.

- Search: This interface allows customers to search for any particular user, group, page, and post and return the list of respective components.

The UML representation of the interfaces is shown below:

[The class diagram of interfaces to be implemented by users in Facebook](./interface.png)

### Search catalog
SearchCatalog is the class where the search functionality is implemented. Each catalog will contain a list of users, groups, pages, and posts, and can add new users, groups, pages, and posts to the catalog.

The class representation of the SearchCatalog class is shown below:

[The class diagram of the SearchCatalog class](./searchcatalog.png)

```
R2: Users of our system should be able to search for groups, pages, and other users.
```

### Enumerations
The enumerations required in the Facebook design are listed below:

- AccountStatus: The account status tells about the status of a member’s account whether it is active, disabled, or blocked.

- FriendInviteStatus: The friend invite status describes the status of a friend request, whether it is pending, accepted, rejected, or canceled.

- PostPrivacySettings: The post-privacy settings enumeration outlines the audience that can view the posts.

[Enums in the Facebook](./enums.png)

### Custom data type
We need to create a custom data type, Address, that will store the location of a Facebook user.

[The class diagram of the custom Address data type](./classdiagram.png)

## Relationship between the classes
Now, we’ll discuss the relationships between the classes we have defined above in our Facebook social network system.

### Association
The class diagram has the following association relationships:

The User class has a one-way association with:

- Itself

    - The Page, Group, FriendRequest, Message, Comment, Post, ProfilePrivacy, and PostPrivacy classes.

    - The PageFunctionsByUser, GroupFunctionsByUser, CommentFunctionsByUser, PostFunctionsByUser, and Search interfaces.

    - The Profile class has a one-way association with ProfilePrivacy.

- The Post class has a one-way association with PostPrivacy and Notification.

- The Notification class has a one-way association with FriendRequest, Message, and Comment.

[The association relationship between classes](./association.png)

### Composition
The class diagram has the following composition relationships:

- The Account class is composed of the User class which is composed of the Profile class.

[The composition relationship between classes](./composition.png)

### Aggregation
The following classes show an aggregation relationship:

- The Profile class contains the Work, Education, and Places classes.

[The aggregation relationship between classes](./aggregation.png)

### Generalization
The following classes show a generalization relationship:

- The SearchCatalog class implements the Search interface.

- The User class implements the Admin class.

- The Group class implements the GroupFunctions interface

[The generalization relationship between classes](./generalization.png)

### Inheritance
The following classes show an inheritance relationship:

- The User class extends the Person class.

- Both EmailNotification and PhoneNotification extend the Notification class.
```
Note: We have already discussed the inheritance relationship between classes in the component section above one by one.
```
## Class diagram of Facebook
[The class diagram of Facebook](./classdiagram.png)

## Design pattern
We know that Facebook has a group feature that allows multiple users to join a group. By default, when a user joins a group, they get notified of any new posts in the group. To effectively map this behavior in our design, we can use the Observer design pattern.

On Facebook, all members of the group are set as subscribers by default. Whenever there is a new activity in the group, the subscribers are notified. The members also have the option to opt out of these notifications, which will remove them from the subscriber list.

## Additional requirements
The interviewer can introduce some additional requirements in the Facebook social network system, or they can ask some follow-up questions. Let's see some examples of additional requirements:

- Recommendations: Users can send recommendations of pages and groups to other users. The class diagram provided below shows the relationship of Recommendation with the other classes:

[The class diagram of the Recommendation functionality](./additional.png)

We have completed the class diagram of Facebook according to the requirements. Now, let’s design the sequence diagram of Facebook in the next lesson.


