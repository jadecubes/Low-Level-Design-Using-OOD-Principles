# Code for the Meeting Scheduler
We've reviewed the different aspects of the meeting scheduler and observed the attributes attached to the problem using various UML diagrams. Let's explore the more practical side of things, where we will work on implementing the meeting scheduler using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the meeting scheduler:

- Java

- C#

- Python

- C++

- JavaScript

## Meeting scheduler classes
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```
### User
The User class refers to a participant taking part in a meeting. A user can either accept or reject an invitation. The definition of this class is given below:
```java
public class User {
  private String name;
  private String email;
  public void respondInvitation(Notification invite);
}

The User class

```

```c#
class User {
  private string name;
  private string email;
  public void RespondInvitation(Notification invite);
}

The User class

```

```python
class User:
  def __init__(self, name, email):
    self.__name = name
    self.__email = email

  def respond_invitation(self, invite):
    pass

The User class

```

```c++
public class User {
  private:
    string name;
    string email;
  public void respondInvitation(Notification invite);
}

The User class

```

```javascript
class User {
  #name;
  #email;

  constructor(name, email) {
    this.#name = name;
    this.#email = email;
  }

  respondInvitation(invite) {}
}

The User class

```

### Interval
The Interval class denotes the meeting interval (the start and end time).

```java
public class Interval {
  private Date startTime;
  private Date endTime;
}

The Interval class

```

```c#
class Interval {
  private DateTime startTime;
  private DateTime endTime;
}

The Interval class

```

```python
class Interval:
  def __init__(self, start_time, end_time):
    self.__start_time = start_time
    self.__end_time = end_time

The Interval class

```

```c++
class Interval {
  private: 
    time_t startTime;
    time_t endTime;
}

The Interval class

```

```javascript
class Interval {
  #startTime;
  #endTime;

  constructor(startTime, endTime) {
    this.#startTime = startTime;
    this.#endTime = endTime;
  }
}

The Interval class

```


### Meeting room
The MeetingRoom class will represent the meeting rooms, each having a specific capacity, a boolean to check if a room is available, and a list of intervals for which the room is booked. The definition of the class is provided below:
```java
public class MeetingRoom {
  private int id;
  private int capacity;
  private boolean isAvailable;
  private List<Interval> bookedIntervals;
}

The MeetingRoom class

```

```c#
class MeetingRoom {
  private int id;
  private int capacity;
  private bool isAvailable;
  private List<Interval> bookedIntervals;
}

The MeetingRoom class
```

```python
class MeetingRoom:
  def __init__(self, id, capacity, is_available):
    self.__id = id
    self.__capacity = capacity
    self.__is_available = is_available
    self.__booked_intervals = []

The MeetingRoom class
```

```c++
class MeetingRoom {
  private:
    int id;
    int capacity;
    bool isAvailable;
    vector<Interval> bookedIntervals;
}

The MeetingRoom class
```

```javascript
class Interval {
  #startTime;
  #endTime;

  constructor(startTime, endTime) {
    this.#startTime = startTime;
    this.#endTime = endTime;
  }
}

The MeetingRoom class
```
### Calendar
The Calendar class contains a list of meetings to keep track of all the scheduled meetings. The definition of this class is provided below:

```java
public class Calendar {
  private List<Meeting> meetings;
}

The Calendar classes

```

```c#
class Calendar {
  private List<Meeting> meetings;
}

The Calendar classes

```

```python
class Calendar:
  def __init__(self):
    self.__meetings = []

The Calendar classes

```

```c++
class Calendar {
  private vector<Meeting> meetings;
}

The Calendar classes

```

```javascript
class Calendar {
  #meetings;

  constructor() {
    this.#meetings = new Array;
  }
}

The Calendar classes

```
### Meeting
### Meeting scheduler
### Notification
## Wrapping up
