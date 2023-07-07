# Use Case Diagram for the Meeting Scheduler
Let's build the use case diagram of the meeting scheduler and understand the relationship between its different components.

First, we'll define the different elements of the meeting scheduler system, followed by the complete use case diagram of the system.

## System
Our system is a "meeting scheduler."

## Actors
Now, we'll define the main actors of the meeting scheduler.

### Primary actors
- Scheduler: This actor can schedule and cancel meetings and book and release meeting rooms.

- User: This actor can accept and reject invitations and will decide their presence for the meetings.

### Secondary actors
- System: This is responsible for sending out notifications regarding any new meetings or cancellations.

## Use cases
In this section, we'll define the use cases for the meeting scheduler. We have listed the use cases according to their respective interactions with a particular actor.

### Scheduler
- Schedule/Cancel meeting: To schedule a new meeting or cancel an existing one

- Book/Release room: To book a room for a meeting or release it

### User
- Attend meeting: To attend a meeting

- Accept/Reject meeting: To accept or reject a meeting invitation

### System
- Send invite notification: To send a notification of any new meeting invitations

- Send cancelation notification: To send a notification of any meeting cancellations

## Relationships
We describe the relationships between and among actors and their use cases in this section.

### Associations
The table below shows the association relationship between actors and their use cases.

```

Scheduler                      User                        System

Schedule/Cancel meeting      Attend meeting	             Send invite notification

Book/Release room            Accept/Reject meeting       Send cancelation notification
```

### Include
- The "Schedule meeting" use case has an include relationship with "Book room," since a room also needs to be booked when a meeting is scheduled.

- The "Schedule meeting" use case also has an include relationship with "Send invite notification," since, whenever a new meeting is scheduled, an invite is sent to all participant's users.

- The "Cancel meeting" use case has an include relationship with the "Release room" use case, since the scheduled room needs to be set free whenever any meeting is canceled.

- The "Cancel meeting" use case has an include relationship with the "Send cancelation notification" use case, since, whenever a meeting is canceled, a cancelation notice is sent to all participant's users.

- The "Cancel meeting" use case also has an include relationship with the "Remove meeting from calendar" use case, since, once a meeting has been canceled, the interval time of all participant's users needs to be set free.

## Use case diagram
Here's the use case diagram of the meeting scheduler:

[The use case diagram of the meeting scheduler]

In the next lesson, we'll discuss the class diagram with a detailed explanation of all classes and their relationship with each other.
