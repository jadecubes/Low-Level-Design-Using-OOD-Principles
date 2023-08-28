# Code for Cricinfo
We've gone over the different aspects of Cricinfo and observed the attributes attached to the problem using various UML diagrams. Let's now explore the more practical side of things, where we will work on implementing the Cricinfo problem using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in Cricinfo:

- Java

- C#

- Python

- C++

- JavaScript

## Cricinfo classes
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```
### Constants
The following code defines the various enums and custom data types used in the Cricinfo design:
```
Note: JavaScript does not support enumerations. We’ll usethe Object.freeze() method as an alternative. It freezes an object and prevents further modifications.
```

```java
public class Address {
  private int zipCode;
  private String streetAddress;
  private String city;
  private String state;
  private String country;
}

enum MatchResult {
  LIVE,
  BAT_FIRST_WIN,
  FIELD_FIRST_WIN,
  DRAW,
  CANCELED
}

enum UmpireType {
  FIELD,
  RESERVED,
  THIRD_UMPIRE
}

enum WicketType {
  BOLD,
  CAUGHT,
  STUMPED,
  RUN_OUT,
  LBW,
  RETIRED_HURT,
  HIT_WICKET,
  OBSTRUCTING,
  HANDLING
}

enum BallType {
  NORMAL,
  WIDE,
  NO_BALL,
  WICKET
}

enum RunType {
  NORMAL,
  FOUR,
  SIX,
  LEG_BYE,
  BYE,
  NO_BALL,
  OVERTHROW
}

enum PlayingPosition {
  BATTING, 
  BOULING,
  ALL_ROUNDER
}
```
### Admin, player, coach, and umpire
### Run, ball, wicket, over, and innings
### Match
### Team, tournament squad, and playing11
### Tournament, points table, and stadium
### Commentator, commentary, and news
### Statistics
## Wrapping up
