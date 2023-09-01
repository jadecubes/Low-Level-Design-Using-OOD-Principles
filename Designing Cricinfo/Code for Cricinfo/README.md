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
class Admin {
  public: 
    bool addPlayer(Player player);
    bool addTeam(Team team);
    bool addMatch(Match match);
    bool addTournament(Tournament tournament);
    bool addStats(Stat stats);
    bool addNews(News news);
};

class Player {
  private: 
    string name;
    int age;
    int country;
    PlayerPosition position;
    vector<Team> teams;
    PlayerStat stat;
};

class Coach {
  private: 
    string name;
    int age;
    int country;
    vector<Team> teams;
};

class Umpire {
  private: 
    string name;
    int age;
    int country;

  public:
    bool assignMatch(Match match);
};
```

```javascript
class Admin {
  addPlayer(player);
  addTeam(team);
  addMatch(match);
  addTournament(tournament);
  addStats(stats);
  addNews(news);
}

class Player {
  #name;
  #age;
  #country;
  #position;
  #teams;
  #stat;
  constructor(name, age, country, position, teams, stat) {
    this.#name = name;
    this.#age = age;
    this.#country = country;
    this.#position = position;
    this.#teams = teams;
    this.#stat = stat;
  }
}

class Coach {
  #name;
  #age;
  #country;
  #teams;
  constructor(name, age, country, teams) {
    this.#name = name;
    this.#age = age;
    this.#country = country;
    this.#teams = teams;
  }
}

class Umpire {
  #name;
  #age;
  #country;
  constructor(name, age, country) {
    this.#name = name;
    this.#age = age;
    this.#country = country;
  }
  aiignMatch(match);
}

```

### Run, ball, wicket, over, and innings
In cricket, the mandatory concepts can be of five types: run, ball, wicket, over, and innings. To store information about these identities, we defined the Run, Ball, Wicket, Over, and Innings classes as shown below:

```java
public class Run {
  private int totalRuns;
  private RunType type;
  private Player scoredBy;
}

public class Ball {
  private Player balledBy;
  private Player playedBy;
  private BallType type;
  private List<Run> runs;
  private Wicket wicket;

  public boolean addCommentary(Commentary commentary);
}

public class Wicket {
  private WicketType type;
  private Player playerOut;
  private Player balledBy;
  private Player caughtBy;
  private Player runoutBy;
  private Player stumpedBy;
}

public class Over {
  private int number;
  private Player bowler;
  private int totalScore;
  private List<Ball> balls;

  public boolean addBall(Ball ball);
}

public class Innings {
  private Playing11 bowling;
  private Playing11 batting;
  private Date startTime;
   private Date endTime;
  private int totalScores;
  private int totalWickets;
  private List<Over> overs;

  public boolean addOver(Over over);
}
```

```c#
class Run {
  private int totalRuns;
  private RunType type;
  private Player scoredBy;
}

class Ball {
  private Player balledBy;
  private Player playedBy;
  private BallType type;
  private List<Run> runs;
  private Wicket wicket;

  public bool AddCommentary(Commentary commentary);
}

class Wicket {
  private WicketType type;
  private Player playerOut;
  private Player balledBy;
  private Player caughtBy;
  private Player runoutBy;
  private Player stumpedBy;
}

class Over {
  private int number;
  private Player bowler;
  private int totalScore;
  private List<Ball> balls;

  public bool AddBall(Ball ball);
}

class Innings {
  private Playing11 bowling;
  private Playing11 batting;
  private DateTime startTime;
  private DateTime endTime;
  private int totalScores;
  private int totalWickets;
  private List<Over> overs;

  public bool AddOver(Over over);
}
```

```python
class Run:
  def __init__(self, total_runs, _type, scored_by):
    self.__total_runs = total_runs
    self.___type = _type
    self.__scored_by = scored_by

class Ball:
  def __init__(self, balled_by, played_by, _type, runs, wicket):
    self.__balled_by = balled_by
    self.__played_by = played_by
    self.___type = _type
    self.__runs = runs
    self.__wicket = wicket
    
  def add_commentary(commentary):
    None

class Wicket:
  def __init__(self, _type, player_out, balled_by, caught_by, runout_by, stumped_by):
    self.___type = _type
    self.__player_out = player_out
    self.__balled_by = balled_by
    self.__caught_by = caught_by
    self.__runout_by = runout_by
    self.__stumped_by = stumped_by

class Over:
  def __init__(self, number, bowler, total_score, overs):
    self.__number = number
    self.__bowler = bowler
    self.__total_score = total_score
    self.__overs = overs
    
  def add_ball(ball):
    None

class Innings:
  def __init__(self, bowling, address, start_time, end_time, total_scores, total_wickets, overs):
    self.__bowling = bowling
    self.__address = address
    self.__start_time = start_time
    self.__end_time = end_time
    self.__total_scores = total_scores
    self.__total_wickets = total_wickets
    self.__overs = overs
    
  def add_over(over):
    None

```

```c++
class Run {
  private: 
    int totalRuns;
    RunType type;
    Player scoredBy;
};

class Ball {
  private:
    Player balledBy;
    Player playedBy;
    BallType type;
    vector<Run> runs;
    Wicket wicket;
  public: 
    boolean addCommentary(Commentary commentary);
};

class Wicket {
  private: 
    WicketType type;
    Player playerOut;
    Player balledBy;
    Player caughtBy;
    Player runoutBy;
    Player stumpedBy;
};

class Over {
  private:
    int number;
    Player bowler;
    int totalScore;
    vector<Ball> balls;
  public: 
    bool addBall(Ball ball);
};

class Innings {
  private: 
    Playing11 bowling;
    Playing11 batting;
    time_t startTime;
    time_t endTime;
    int totalScores;
    int totalWickets;
    List<Over> overs;
  public: 
    bool addOver(Over over);
};

```

```javascript
class Run {
  #totalRuns;
  #type;
  #scoredBy;
  constructor(totalRuns, address, scoredBy) {
    this.#totalRuns = totalRuns;
    this.#type = type;
    this.#scoredBy = scoredBy;
  }
}

class Ball {
  #balledBy;
  #playedBy;
  #type;
  #runs;
  #wicket;
  constructor(balledBy, playedBy, type, runs, wicket) {
    this.#balledBy = balledBy;
    this.#playedBy = playedBy;
    this.#type = type;
    this.#runs = runs;
    this.#wicket = wicket;
  }
  addCommentary(commentary);
}

class Wicket {
  #type;
  #playerOut;
  #balledBy;
  #caughtBy;
  #runoutBy;
  #stumpedBy;
  constructor(type, playerOut, balledBy, caughtBy, runoutBy, stumpedBy) {
    this.#type = type;
    this.#playerOut = playerOut;
    this.#balledBy = balledBy;
    this.#caughtBy = caughtBy;
    this.#runoutBy = runoutBy;
    this.#stumpedBy = stumpedBy;
  }
}

class Over {
  #number;
  #bowler;
  #totalScore;
  #balls;
  constructor(number, bowler, totalScore, balls) {
    this.#number = number;
    this.#bowler = bowler;
    this.#totalScore = totalScore;
    this.#balls = balls;
  }
  addBall(ball);
}

class Innings {
  #bowling;
  #batting;
  #startTime;
  #endTime;
  #totalScores;
  #totalWickets;
  #overs;
  constructor(bowling, batting, startTime, endTime, totalScores, totalWickets, overs) {
    this.#bowling = bowling;
    this.#batting = batting;
    this.#startTime = startTime;
    this.#endTime = endTime;
    this.#totalScores = totalScores;
    this.#totalWickets = totalWickets;
    this.#overs = overs;
  }
  addOver(over);
}

```

### Match
```java
public abstract class Match {
  private Date startTime;
  private MatchResult result;
  private int totalOvers;
  private List<Playing11> teams;
  private List<Innings> innings;
  private Playing11 tossWin;
  private Map<Umpire, UmpireType> umpires;
  private Stadium stadium;
  private List<Commentator> commentators;
  private List<MatchStat> stats;

  public abstract boolean assignStadium(Stadium stadium);
  public abstract boolean assignUmpire(Umpire umpire);
}

public class T20 extends Match {
  public boolean assignStadium(Stadium stadium);
  public boolean assignUmpire(Umpire umpire);
}

public class Test extends Match {
  public boolean assignStadium(Stadium stadium);
  public boolean assignUmpire(Umpire umpire);
}

public class ODI extends Match {
  public boolean assignStadium(Stadium stadium);
  public boolean assignUmpire(Umpire umpire);
}
```

```c#
public abstract class Match {
  private DateTime startTime;
  private MatchResult result;
  private int totalOvers;
  private List<Playing11> teams;
  private List<Innings> innings;
  private Playing11 tossWin;
  private Dictionary<Umpire, UmpireType> umpires;
  private Stadium stadium;
  private List<Commentator> commentators;
  private List<MatchStat> stats;

  public abstract bool AssignStadium(Stadium stadium);
  public abstract bool AssignUmpire(Umpire umpire);
}

public class T20 : Match {
  public override bool AssignStadium(Stadium stadium);
  public override bool AssignUmpire(Umpire umpire);
}

public class Test : Match {
  public override bool AssignStadium(Stadium stadium);
  public override bool AssignUmpire(Umpire umpire);
}

public class ODI : Match {
  public override bool AssignStadium(Stadium stadium);
  public override bool AssignUmpire(Umpire umpire);
}
```

```python
from abc import ABC, abstractmethod
class Match(ABC):
  def __init__(self, start_time, result, total_overs, teams, innings, toss_win, umpires, stadium, commentators, stats):
    self.__start_time = start_time
    self.__result = result
    self.__total_overs = total_overs
    self.__teams = teams
    self.__innings = innings
    self.__toss_win = toss_win
    self.__umpires = umpires
    self.__stadium = stadium
    self.__commentators = commentators
    self.__stats = stats

  @abstractmethod
  def assign_stadium(self, stadium):
    None
  def assign_umpire(self, umpire):
    None

class T20(Match):
  def __init__(self, start_time, result, total_overs, teams, innings, toss_win, umpires, stadium, commentators, stats):
    super().__init__(start_time, result, total_overs, teams, innings, toss_win, umpires, stadium, commentators, stats)

  def assign_stadium(self, stadium):
    None
  def assign_umpire(self, umpire):
    None

class Test(Match):
  def __init__(self, start_time, result, total_overs, teams, innings, toss_win, umpires, stadium, commentators, stats):
    super().__init__(start_time, result, total_overs, teams, innings, toss_win, umpires, stadium, commentators, stats)
  
  def assign_stadium(self, stadium):
    None
  def assign_umpire(self, umpire):
    None

class ODI(Match):
  def __init__(self, start_time, result, total_overs, teams, innings, toss_win, umpires, stadium, commentators, stats):
    super().__init__(start_time, result, total_overs, teams, innings, toss_win, umpires, stadium, commentators, stats)
 
  def assign_stadium(self, stadium):
    None
  def assign_umpire(self, umpire):
    None

```

```c++
public class Match {
  private: 
    time_t startTime;
    MatchResult result;
    int totalOvers;
    List<Playing11> teams;
    List<Innings> innings;
    Playing11 tossWin;
    map<Umpire, UmpireType> umpires;
    Stadium stadium;
    List<Commentator> commentators;
    List<MatchStat> stats;

  public: 
    virtual bool assignStadium(Stadium stadium) = 0;
    virtual bool assignUmpire(Umpire umpire) = 0;
};

class T20 : public Match {
  public: 
    bool assignStadium(Stadium stadium);
    bool assignUmpire(Umpire umpire);
};

class Test : public Match {
  public: 
    bool assignStadium(Stadium stadium);
    bool assignUmpire(Umpire umpire);
};

class ODI : public Match {
  public: 
    bool assignStadium(Stadium stadium);
    bool assignUmpire(Umpire umpire);
};
```

```javascript
class Match {
    #startTime;
    #result;
    #totalOvers;
    #teams;
    #innings;
    #tossWin;
    #umpires;
    #stadium;
    #commentators;
    #stats;
    constructor(startTime, result, totalOvers, teams, innings, tossWin, umpires, stadium, commentators, stats) {
      if (this.constructor == Match) {
        throw new Error("Abstract classes can't be instantiated.");
      }
      else{
        this.#startTime = startTime;
        this.#result = result;
        this.#totalOvers = totalOvers;
        this.#teams = teams;
        this.#innings = innings;
        this.#tossWin = tossWin;
        this.#umpires = umpires;
        this.#stadium = stadium;
        this.#commentators = commentators;
        this.#stats = stats;
      }
    }
    assignStadium(stadium);
    assignUmpire(umpire);
}

class T20 extends Match {
  constructor(startTime, result, totalOvers, teams, innings, tossWin, umpires, stadium, commentators, stats){
    super(startTime, result, totalOvers, teams, innings, tossWin, umpires, stadium, commentators, stats);
  }
  assignStadium(stadium);
  assignUmpire(umpire);
}

class Test extends Match {
  constructor(startTime, result, totalOvers, teams, innings, tossWin, umpires, stadium, commentators, stats){
    super(startTime, result, totalOvers, teams, innings, tossWin, umpires, stadium, commentators, stats);
  }
  assignStadium(stadium);
  assignUmpire(umpire);
}

class ODI extends Match {
  constructor(startTime, result, totalOvers, teams, innings, tossWin, umpires, stadium, commentators, stats){
    super(startTime, result, totalOvers, teams, innings, tossWin, umpires, stadium, commentators, stats);
  }
  assignStadium(stadium);
  assignUmpire(umpire);
}

```
### Team, tournament squad, and playing11
The definitions of the AdminTeam, TournamentSquad, and Playing11 classes are as follows:

```java
```

```c#
```

```python
```

```c++
```

```javascript
```
### Tournament, points table, and stadium
```java
```

```c#
```

```python
```

```c++
```

```javascript
```
### Commentator, commentary, and news
```java
```

```c#
```

```python
```

```c++
```

```javascript
```
### Statistics
```java
```

```c#
```

```python
```

```c++
```

```javascript
```
## Wrapping up
We've explored the complete design of Cricinfo in this chapter. We've looked at how Cricinfo can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
