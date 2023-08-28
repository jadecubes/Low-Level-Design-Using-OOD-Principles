# Use Case Diagram for Cricinfo
Let's build the use case diagram of Cricinfo and understand the relationship between its different components.

First, we will define the different elements of our Cricinfo system, followed by the complete use case diagram of the system.

## System
Our system is "Cricinfo."

## Actors
Now, we’ll define the main actors of Cricinfo.

### Primary actors
- Admin: The admin is in charge of performing numerous operations—adding or modifying tournaments, innings, updating stats, etc.

- Commentator: This actor can add commentary to the match or modify it.

### Secondary actors
There is no secondary actor in the system.

## Use cases
In this section, we’ll define the use cases for Cricinfo. We have listed the use cases according to their respective interactions with a particular actor.
```
Note: You’ll see some use cases occurring multiple times because they are shared among different actors in the system.
```
### Admin
- Add/modify team: To add a team in the system or modify it

- Add/modify player: To add a player to the team or modify it

- Add/modify tournament: To add a tournament in the system or modify it

- Add/modify team squad: To add a team squad or modify it

- Add/modify innings: To add innings in the match or modify it

- Add/modify over: To add an over in the match or modify it

- Add/modify ball: To add a ball in the match or modify it

- Add match: To add a match in the system

- Add/update news: To add the match news in the system or update it

- Add/modify stadium: To add a stadium in the system or modify it

- Add/modify umpire: To add an umpire in the system or modify it

- Add/update stats: To add stats of a player, match, or tournament to the system

### Commentator
- Add/modify commentary: To add a commentary to the match or modify it

## Relationships
We describe the relationships between and among actors and their use cases in this section.

### Generalization
- The admin can add/update stats by adding/updating player, match, or tournament stats. This shows “Add/update stats” use case has a generalization relationship with the “Add/update player stats,” “Add/update match stats,” and “Add/update tournament stats” use cases.

- The admin can add the match type—T20, test, or ODI. Hence, the “Add match” use case has a generalization relationship with the “Add T20,” “Add test,” and “Add ODI” use cases.

### Associations
The table below shows the association relationship between actors and their use cases.

```
Admin                         Commentator

Add/modify team               Add/modify commentary

Add/modify player



Add/modify tournament

Add/modify team squad

Add/modify innings

Add/modify over

Add/modify ball

Add match

Add/update news

Add/modify stadium

Add/modify umpire

Add/update stats
```
### Extend
While adding/modifying the ball, either a run, wicket, or both are added/modified. Therefore, the “Add/modify ball” use case has an extend relationship with the “Add/modify run” and “Add/modify wicket” use cases.

## Use case diagram
[The use case diagram of Cricinfo]
