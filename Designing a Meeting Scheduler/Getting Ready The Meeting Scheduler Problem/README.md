# Getting Ready: The Meeting Scheduler Problem
## Problem definition
A meeting scheduler software allows organizations to schedule and book meetings for a group of participants. The scheduler determines a meeting time and location depending on the availability of the participants. It ensures that most of the intended participants can effectively meet on the specified date and interval. The system allows users to book and cancel meetings. The invited participants promptly receive these notifications. The organizer can also add new participants to a meeting after the meeting is scheduled.

[Schedule a meeting using a meeting scheduler]

## Expectations from the interviewee
It is important to narrow down the components you will include in your design of a meeting scheduler. The following section provides an overview of some of the main expectations that the interviewer will want to hear you discuss in more detail during the interview.

### Room assignment
A meeting scheduler is responsible for assigning a meeting room to a scheduled meeting. Make sure to ask the following questions from the interviewer to figure out how this assignment works:

- How does the system determine available rooms?

- How important is the capacity of a room when assigning a room for a meeting?

### Availability of attendees
There are multiple attendees in a meeting, and all attendees have different schedules. You may ask the following questions to understand how the scheduler works:

- How does the system check the availability of the attendees?

- How does the system access the meeting information of all attendees?

## Design approach
We'll design a meeting scheduler using the bottom-up design approach. For this purpose, we will follow the steps below:

- Identify and design the smallest components first, like an interval and meeting room.

- Use these small components to design additional components, for example, a meeting and a calendar.

- Repeat the steps above until we design the scheduler, which is the main component of the system.

## Design pattern
It is always a good practice to discuss the design patterns that the meeting scheduler falls under, during the interview. Stating the design patterns will give the interviewer a positive impression and shows that the interviewee is well-versed in the advanced concepts of object-oriented design.

The following design pattern is used to design the meeting scheduler:

- Singleton design pattern

Let's explore the requirements of the meeting scheduler in the next lesson.
