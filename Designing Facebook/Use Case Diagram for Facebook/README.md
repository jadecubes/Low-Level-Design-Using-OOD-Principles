# Use Case Diagram for Facebook
Let's begin building the use case diagram of Facebook and understand the relationship between its different components.

First, we are going to define the different elements of our Facebook system, followed by the complete use case diagram of the system.

## System
Our system is "Facebook."

## Actors
Now, we’ll define the main actors of Facebook.

### Primary actors
- User: This actor can create a profile of themselves containing their personal information. They can create posts, pages, and groups, and add various sorts of multimedia like images or videos. They can also interact with other users by sending them friend requests and messages, commenting on their posts, etc.

### Secondary actors
- Page/Group Admin: The admin is in charge of performing numerous operations, including blocking or unblocking users from groups or pages, deleting an existing group, changing the group’s privacy, etc.

- System: This is responsible for sending out notifications for new friend requests, messages, comments, etc.

## Use cases
In this section, we’ll define the use cases for Facebook. We have listed the use cases according to their respective interactions with a particular actor.
```
Note: You’ll see some use cases occurring multiple times because they are shared among different actors in the system.
```

### User
- Add/update profile: To add information like work, education, and places of visit details or to update an existing profile

- Follow/unfollow user: To follow or unfollow other users

- Send message: To send a message to other users

- Send friend request: To send a friend request to other users

- Create/like/follow/share page: To either create a new page or perform actions including liking, following, or sharing an existing page.

- Create/join/leave group: To either create a new group or perform actions like joining or leaving an existing group

- Invite users to group: To invite other users to an existing group.

- Add/update/delete post: To add a new post, update the content of the post, or delete an existing post

- Like/comment/share post: To like a post, comment on a post, or share a post

- Add/update/delete/like comment: To add a new comment, update the content of the comment, like a particular comment, or delete a comment

- Accept/reject friend request: To accept or reject a friend request from another user

- Update privacy: To update the privacy settings of the profile

- Search users/groups/pages/posts: To search for other users, any existing groups or pages, or any posts made by users

- Accept/Reject friend request: To accept or reject a friend request from another Facebook user

- Accept/Reject group join invitation: To accept or reject a group joining invitation from another Facebook user

- Like/Comment/Share Post: To like, comment, or share any post visible to users on Facebook

### Page/Group Admin
- Block/unblock user: To block or unblock a user from a group or page

- Enable/disable page: To enable or disable a page

- Delete group: To delete an existing group

- Change a group's privacy: To change the privacy settings of a group (from public to private and vice versa)

### System
- Send new friend request notification: To send a notification of any friend request sent by another user

- Send message notification: To send a notification of any new messages

- Send new post notification: To send a notification of any new posts

- Send comment notification: To send a notification of any comments on your or others' posts

## Relationships
We describe the relationships between and among actors and their use cases in this section.


### Generalization
- The “Page/Group Admin” has a generalization relationship with the “User” as the admin can perform all those tasks that a normal user can perform.

- We can search for other users, groups, pages, or even posts. This shows that the “Search” use case has a generalization relationship with the “users,” “groups,” “pages,” and “posts” use cases.

### Associations
The table below shows the association relationship between actors and their use cases.
```
User                                      Page/Group Admin                          System

Add/update profile                        Add/update profile                        Send new friend request notification

Follow/unfollow user                      Follow/unfollow user                      Send message notification

Send message                              Send message                              Send new post notification

Send friend request                       Send friend request                       Send comment notification

Create/like/follow/share page             Create/like/follow/share page

Create/join/leave group                   Create/join/leave group

Invite user to group                      Invite user to group

Add/update/delete post                    Add/update/delete post

Add/update/delete/like comment            Add/update/delete/like comment

Accept/reject friend request              Accept/reject friend request

Update privacy                            Update privacy

Search users/groups/pages/posts           Search users/groups/pages/posts

Accept/Reject friend request              Block/unblock user

Accept/Reject group join invitation       Enable/disable page

Like/Comment/Share Post                   Delete group

                                          Change a group's privacy
```

### Include
- The “Send friend request” use case also has an include relationship with the “Send new friend request notification,” because whenever a user receives a friend request, the user is notified.

- The “Send message” use case has an include relationship with the “Send message notification” use case, because whenever a user receives a message, the user is notified.

- The “Add post” use case has an include relationship with the “Send new post notification” use case. Whenever a new post is created by a user being followed by the default user, the default user is notified.

- The “Add comment” use case has an include relationship with the “Send new comment notification” use case. Whenever a new comment is made by another user on a post either created by the default user or followed by the default user, the default user is notified.

## Use case diagram

[The use case diagram of Facebook](./ucd.png)
