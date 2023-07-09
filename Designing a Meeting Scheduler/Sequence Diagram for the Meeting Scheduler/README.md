# Sequence Diagram for the Meeting Scheduler
Sequence diagrams are a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for our meeting scheduler. In this lesson, we will create sequence diagrams for the following interactions:

- Schedule a meeting: The meeting organizer schedules a meeting time for some attendees.

- Sequence challenge: The meeting organizer cancels a scheduled meeting.

## Schedule a meeting
The sequence diagram to schedule a meeting should have the following actors and objects that will interact with each other:

- Actor: Organizer

- Objects: Scheduler, Calendar, MeetingRoom, and Meeting

The steps in the schedule meeting interaction are listed below:

1. The meeting organizer schedules a meeting for some attendees at a given interval.

2. The scheduler checks for the availability of a meeting room.

3. If a room is available:

I. The scheduler books the meeting room.

II. The scheduler creates a new meeting.

III. The scheduler updates the calendar with the new meeting.

IV. The scheduler informs the organizer that the meeting is scheduled.

V. The scheduler sends an invite to the attendee.

4. Else if no room is available:

I. The scheduler informs the organizer to select another meeting time.

Based on the order above, the sequence diagram for scheduling a meeting in the meeting scheduler system is given below:

[The sequence diagram for scheduling a meeting](./seq1.png)

## Sequence challenge: Cancel meeting
You'll help us to complete a sequence diagram for the cancel meeting interaction. A skeleton of the cancel meeting sequence diagram is provided below:

[The sequence diagram for canceling a meeting](./seq2.png)

Notice that the arrows in the diagram above are numbered from 1 to 7. The message boxes shown below are the messages to be exchanged between the actor(s) and object(s). Can you rearrange the messages below in the correct sequence of order they should appear in the skeleton of the sequence diagram given above?

[Sequence](./challenge.png)

[Answer](./answer.png)
