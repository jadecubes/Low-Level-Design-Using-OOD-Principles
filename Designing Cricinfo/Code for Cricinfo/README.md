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

```c#
class Address {
  private int zipCode;
  private string streetAddress;
  private string city;
  private string state;
  private string country;
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

```python
class Address:
  def __init__(self, zip_code, street_address, city, state, country):
    self.__zip_code = zip_code
    self.__street_address = street_address
    self.__city = city
    self.__state = state
    self.__country = country

class MatchResult(enum.Enum):
  LIVE = 1 
  BAT_FIRST_WIN = 2
  FIELD_FIRST_WIN = 3
  DRAW = 4
  CANCELED = 5

class UmpireType(enum.Enum):
  FIELD = 1 
  RESERVED = 2
  THIRD_UMPIRE = 3

class WicketType(enum.Enum):
  BOLD = 1 
  CAUGHT = 2
  STUMPED = 3
  RUN_OUT = 4
  LBW = 5
  RETIRED_HURT = 6
  HIT_WICKET = 7
  OBSTRUCTING = 8
  HANDLING = 9

class BallType(enum.Enum):
  NORMAL = 1 
  WIDE = 2
  NO_BALL = 3
  WICKET = 4

class RunType(enum.Enum):
  NORMAL = 1 
  FOUR = 2
  SIX = 3
  LEG_BYE = 4
  BYE = 5
  NO_BALL = 6
  OVERTHROW = 7
  
class PlayingPosition(enum.Enum):
  BATTING = 1 
  BOULING = 2
  ALL_ROUNDER = 3
```

```c++
class Address {
  private:
    int zipCode;
    string streetAddress;
    string city;
    string state;
    string country;
};

enum MatchResult {
  LIVE,
  BAT_FIRST_WIN,
  FIELD_FIRST_WIN,
  DRAW,
  CANCELED
};

enum UmpireType {
  FIELD,
  RESERVED,
  THIRD_UMPIRE
};

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
};

enum BallType {
  NORMAL,
  WIDE,
  NO_BALL,
  WICKET
};

enum RunType {
  NORMAL,
  FOUR,
  SIX,
  LEG_BYE,
  BYE,
  NO_BALL,
  OVERTHROW
};

enum PlayingPosition {
  BATTING, 
  BOULING,
  ALL_ROUNDER
};
```

```javascript
class Address {
  #zipCode
  #streetAddress
  #city
  #state
  #country

  constructor(zipCode, streetAddress, city, state, country) {
    this.#zipCode = zipCode
    this.#streetAddress = streetAddress
    this.#city = city
    this.#state = state
    this.#country = country
  }
}

const MatchResult = Object.freeze({
  LIVE,
  BAT_FIRST_WIN,
  FIELD_FIRST_WIN,
  DRAW,
  CANCELED
});

const UmpireType = Object.freeze({
  FIELD,
  RESERVED,
  THIRD_UMPIRE
});

const WicketType = Object.freeze({
  BOLD,
  CAUGHT,
  STUMPED,
  RUN_OUT,
  LBW,
  RETIRED_HURT,
  HIT_WICKET,
  OBSTRUCTING,
  HANDLING
  DELETED
});

const BallType = Object.freeze({
  NORMAL,
  WIDE,
  NO_BALL,
  WICKET
});

const RunType = Object.freeze({
  NORMAL,
  FOUR,
  SIX,
  LEG_BYE,
  BYE,
  NO_BALL,
  OVERTHROW
});

const PlayingPosition = Object.freeze({
  BATTING, 
  BOULING,
  ALL_ROUNDER
});

```
### Admin, player, coach, and umpire
The definitions of the Admin, Player, Coach and Umpire classes are as follows:

```java
public class Admin {
  public boolean addPlayer(Player player);
  public boolean addTeam(Team team);
  public boolean addMatch(Match match);
  public boolean addTournament(Tournament tournament);
  public boolean addStats(Stat stats);
  public boolean addNews(News news);
}

public class Player {
  private String name;
  private int age;
  private int country;
  private PlayerPosition position;
  private List<Team> teams;
  private PlayerStat stat;
}

public class Coach {
  private String name;
  private int age;
  private int country;
  private List<Team> teams;
}

public class Umpire {
  private String name;
  private int age;
  private int country;

  public boolean assignMatch(Match match);
}
```

```c#
class Admin {
  public bool addPlayer(Player player);
  public bool AddTeam(Team team);
  public bool AddMatch(Match match);
  public bool AddTournament(Tournament tournament);
  public bool AddStats(Stat stats);
  public bool AddNews(News news);
}
class Player {
  private string name;
  private int age;
  private int country;
  private PlayerPosition position;
  private List<Team> teams;
  private PlayerStat stat;
}

class Coach {
  private string name;
  private int age;
  private int country;
  private List<Team> teams;
}

class Umpire {
  private string name;
  private int age;
  private int country;

  public bool AssignMatch(Match match);
}
```

```python
class Admin:
  def __init__(self):
    None
  def add_player(self, player):
    None  
  def add_team(self, team):
    None
  def add_match(self, match):
    None 
  def add_tournament(self, tournament):
    None
  def add_stats(self, stats):
    None 
  def add_news(self, news):
    None

class Player:
  def __init__(self, name, age, country, position, teams, stat):
    self.__namer = name
    self.__age = age
    self.__country = country
    self.__position = position
    self.__teams = teams
    self.__stat = stat

class Coach:
  def __init__(self, name, age, country, teams):
    self.__namer = name
    self.__age = age
    self.__country = country
    self.__teams = teams

class Umpire:
  def __init__(self, name, age, country):
    self.__namer = name
    self.__age = age
    self.__country = country

  def assign_match(match):
    None

```

```c++
```

```javascript
```

### Run, ball, wicket, over, and innings
### Match
### Team, tournament squad, and playing11
### Tournament, points table, and stadium
### Commentator, commentary, and news
### Statistics
## Wrapping up
