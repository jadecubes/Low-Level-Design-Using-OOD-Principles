# Class Diagram for the Meeting Scheduler
In this lesson, we'll identify and design the classes, abstract classes, and interfaces based on the requirements that we have previously gathered from the interviewer in a meeting scheduler.

## Components of a meeting scheduler
As mentioned earlier, we'll design the meeting scheduler using a bottom-up approach.

### User
The User class is responsible for representing the personal information of a user such as their name, email, and can also accept or reject an invitation to a meeting.

The class definition is shown below:

[The class diagram of the User class](./user.png)

```
R5: Users will receive an invite regardless of whether or not they are available at the interval. Users can respond to the invitation by either accepting or rejecting the invite.
```

### Interval
The Interval class contains the start time and end time of a meeting. The visual representation of the Interval class is as follows:

[The class diagram of the Interval class](./interval.png)

```
R3: If not reserved already, each meeting room should have the ability to be booked, along with setting an interval, a start time, and an end time for the meeting.
```
### Meeting room
The MeetingRoom class contains the details of any particular room, such as its capacity and a status, to identify whether it is currently available. It also contains a list of intervals to keep track of when the room is booked for a meeting.

The class diagram of the MeetingRoom class is provided below:

[The class diagram of the MeetingRoom class](./meetingroom.png)

```
R2: Each meeting room should have a specific capacity to accommodate the desired number of people.

R3: If not reserved already, each meeting room should have the ability to be booked, along with setting an interval, a start time, and an end time for the meeting.
```
### Meeting
The Meeting class displays the meeting details, such as the participants, the meeting time, and the meeting room.

The class diagram of the Meeting class is provided below:

[The class diagram of the Meeting class](./meeting.png)

```
R3: If not reserved already, each meeting room should have the ability to be booked, along with setting an interval, a start time, and an end time for the meeting.
```
### Calendar
The Calendar class keeps track of all the meetings that are scheduled or being held.

The class definition is provided below:

[The class diagram of the Calendar class](./calenar.png)

```
R6: Each user should have access to a calendar that can be used to track the date and time, as well as to schedule or cancel meetings.
```

### Meeting scheduler
The MeetingScheduler class contains an organizer that is responsible for scheduling a meeting using the calendar. It can also cancel a meeting, check the availability of meeting rooms, and book or release a meeting room.

The visual representation of the MeetingScheduler class is provided below:

[Class diagram of the MeetingScheduler class](./meetingscheduler.png)

```
R6: Each user should have access to a calendar that can be used to track the date and time, as well as to schedule or cancel meetings.
```

### Notification
The Notification class will send a notification for an invitation to a user regarding any new meeting. It will also send a cancelation notification to a user as well, in case any meeting gets canceled or is postponed.

The UML representation of the class is shown below:

[The class diagram of the Notification class](./notification.png)

```
R4: A notification should be sent to all the people invited to the meeting.
```

## Relationship between the classes
Now, we'll discuss the relationships between the classes we have defined above in the meeting scheduler.

### Association
The class diagram has the following association relationships:

- The User class has a one-way association with the Notification class and a two-way association with the Meeting class.

- The MeetingScheduler class has a one-way association with the Notification and Meeting classes.

[The association relationship between classes](./relationship.png)

### Composition
The class diagram has the following composition relationships:

- The MeetingScheduler class is composed of the Calendar class.

- The Calendar class is composed of the Meeting class.

[The composition relationship between classes](./composition.png)


### Aggregation
The class diagram has the following aggregation relationships:

- The MeetingScheduler class is aggregated from the User and MeetingRoom class.

- The MeetingRoom class is aggregated from the Interval class.

## Class diagram of the meeting scheduler
Here's the complete class diagram for the meeting scheduler:

[The class diagram of the meeting scheduler](./classdiagram.png)

## Design pattern
In the meeting scheduler design, the entire system revolves around the scheduler which is responsible for scheduling meetings. To create a robust design, it is not possible that there can be more than one instance for the scheduler. Therefore, we use the Singleton design pattern to ensure that only one instance of the scheduler is created and that this instance has a global point of access.

We have completed the class diagram of the meeting scheduler according to the requirements. Now let's design the sequence diagram of the meeting scheduler in the next lesson.
