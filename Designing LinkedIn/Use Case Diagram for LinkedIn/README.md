# Use Case Diagram for LinkedIn
Let's build the use case diagram of LinkedIn and understand the relationship between its different components.

First, we’ll define the different elements of our LinkedIn system, followed by the complete use case diagram of the system.

## System
Our system is "LinkedIn."

## Actors
Now, we’ll define the main actors of LinkedIn.

### Primary actors
- User: This actor can create a profile including their professional information. They can create posts, apply for jobs, follow pages, and join groups. They can also interact with other users by sending them connection invitations and messages, commenting on their posts, etc.

- Admin: The admin is in charge of performing numerous operations, including blocking or unblocking users, enabling/disabling pages, deleting an existing group, etc.

### Secondary actors
System: This is responsible for sending out notifications for new connection requests, messages, comments, posts, recommendations, etc.

## Use cases
In this section, we’ll define the use cases for LinkedIn. We have listed the use cases according to their respective interactions with a particular actor.
```
Note: You’ll see some use cases occurring multiple times because they are shared among different actors in the system.
```
### User
- Add/update profile: To add information like education, experience, skill, and achievement to update an existing profile

- Follow/unfollow user: To follow or unfollow other users

- Send message: To send a message to other users

- Send connection invitation: To send a connection invitation to other users

- Accept/ignore connection invitation: To accept or ignore a connection invitation from another user

- Create/follow/unfollow page: To either create a new page or perform actions including update, delete, or follow an existing page

- Create/join/leave a group: To either create a new group or perform actions like joining or leaving an existing group

- Add/share post: To add a new post or share an existing post

- Update/delete/react post: To update a post, delete a post, or react to the post

- Comment on post/comment: To comment on the post, or to add a comment on an existing comment

- Update/delete/react comment: To update the content of the comment, react to a particular comment, or delete a comment

- Search users/groups/pages/jobs: To search for other users, or any existing groups, company pages, or jobs

- Post a job: To post the job on the page

- View analytics: To see the number of connections, post impressions, profile views, and search appearances of the user

- Request recommendation: To send a recommendation request to other users

- Accept recommendation: To accept a recommendation request from the user

- Delete recommendation: To delete a recommendation request from the user

### Admin
- Block/unblock user: To block or unblock a user on LinkedIn

- Enable/disable page: To enable or disable a page

- Delete group: To delete an existing group

### System
- New post notification: To send a notification of any new posts

- New comment notification: To send a notification whenever another user comments on a user's post or comment

- Connection invitation notification: To send a notification of any connection invitation sent by any user

- Message notification: To send a notification of any new messages

- Recommendation notification: To send a notification of recommendation requested by any user

- Add recommendation: To add a recommendation to the user's profile

## Relationships
This section describes the relationships between and among actors and their use cases.

### Generalization
- The user can add/update their profile by either adding or updating their education, experience, skill, or achievement. This shows that the “Add/update profile” use case has a generalization relationship with “Add/update education,” “Add/update experience,” “Add/update skill,” and “Add/update achievement” use cases.

### Associations
The table below shows the association relationship between actors and their use cases.
```
User                                          Admin                             System

Add/update profile                         Block/unblock user              New post notification

Follow/unfollow user                       Enable/disable page             New comment notification

Send message                               Delete group                    Connection invitation notification


Send connection invitation                                                 Message notification                                                 

Accept/ignore connection invitation                                        Recommendation notification

Create/follow/unfollow page                                                Add recommendation

Create/join/leave a group

Add/share post

Update/delete/react post

Comment on post/comment

Update/delete/react comment

Search users/groups/pages/jobs

Post a job

View analytics

Request recommendation

Accept recommendation

Delete recommendation
```
### Include
- The “Send message” use case has an include relationship with the “Message notification” use case, because whenever a user receives a message, the user is notified.

- The “Send connection invitation” use case has an include relationship with the “Connection invitation notification” use case. Whenever a user receives the connection invitation, the system notifies the user.

- When the user accepts the recommendation request, the system adds that recommendation in the user's profile. Therefore, the “Accept recommendation” use case has an include relationship with the “Add recommendation” use case.

- The “Add/share post" use case has an include relationship with the “New post notification.” Whenever a user creates a post or shares it, the system notifies the connected users.

- The “Comment on post/comment” use case has an include relationship with the “New comment notification” use case. Whenever a new comment is made by another user on a post either created by the default user or followed by the default user, the system notifies the default user.

- The “Request recommendation” use case has an include relationship with the “Recommendation notification” use case. Whenever a user gets a recommendation request, the system notifies the user.

### Extend
- When users get the recommendation request, they can either accept or delete the request. Therefore, the “Request recommendation” use case has an extend relationship with the “Accept recommendation” and "Delete recommendation" use cases.

- Whenever the users get a connection invitation request, they can either accept or ignore the request. Therefore, the “Send connection invitation” use case has an extend relationship with the “Accept/ignore connection invitation” use case.

## Use case diagram

[The use case diagram of LinkedIn](./daigram.png)
