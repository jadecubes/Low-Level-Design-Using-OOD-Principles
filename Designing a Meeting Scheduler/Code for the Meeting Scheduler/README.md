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
The Meeting class outlines the meeting details such as the number and list of participants, meeting time interval, and meeting room. It also has the option to add more participants. The definition of this class is shown below:

```java
public class Meeting {
  private int id;
  private int participantsCount;
  private List<User> participants;
  private Interval interval;
  private MeetingRoom room;
  private String subject
  
  public void addParticipants(List<User> participants);
}

The Meeting class

```

```c#
class Meeting {
  private int id;
  private int participantsCount;
  private List<User> participants;
  private Interval interval;
  private MeetingRoom room;
  private string subject
  
  public void AddParticipants(List<User> participants);
}

The Meeting class

```

```python
class Meeting:
    def __init__(self, id, participants_count, interval, room, subject):
        self.__id = id
        self.__participants_count = participants_count
        self.__participants = []
        self.__interval = interval
        self.__room = room
        self.__subject = subject
  
  def add_participants(self, participants):
      pass

The Meeting class

```

```c++
class Meeting {
  private: 
    int id;
    int participantsCount;
    vector<User> participants;
    Interval interval;
    MeetingRoom room;
    string subject

  public:
    void addParticipants(vector<User> participants);
}

The Meeting class

```

```javascript
class Meeting {
    #id;
    #participantsCount;
    #participants;
    #interval;
    #room;
    #subject;

    constructor(id, participantsCount, interval, room, subject) {
        this.#id = id;
        this.#participantsCount = participantsCount;
        this.#participants = new Array();
        this.#interval = interval;
        this.#room = room;
        this.#subject = subject;
    }
  
  addParticipants(participants) {}
}

The Meeting class


```

### Meeting scheduler
The MeetingScheduler class is the main class of the meeting scheduler and contains the organizer, which is responsible for scheduling and canceling a meeting as well as booking or releasing a room. It also checks if any meeting rooms are available for a meeting. In addition, there will be only one instance of the scheduler in the meeting scheduler. Therefore, the MeetingScheduler class will be a Singleton class to ensure that only one instance for the scheduler is created in the entire system.

The definition of this class is shown below:

```java
public class MeetingScheduler {
  private User organizer;
  private Calendar calendar;
  private List<MeetingRoom> rooms;

  // Scheduler is a singleton class that ensures it will have only one active instance at a time
  private static MeetingScheduler scheduler = null;
    
  // Created a static method to access the singleton instance of Scheduler class
  public static MeetingScheduler getInstance() {
    if (scheduler == null) {
      scheduler = new MeetingScheduler();
    }
    return scheduler;
  }  

  public boolean scheduleMeeting(List<User> users, Interval interval);
  public boolean cancelMeeting(List<User> users, Interval interval);
  public boolean bookRoom(MeetingRoom room, int numberOfPersons, Interval interval);
  public boolean releaseRoom(MeetingRoom room, Interval interval);
  public MeetingRoom checkRoomsAvailability(int numberOfPersons, Interval interval);
}

The Meeting class

```

```c#
class MeetingScheduler {
  private User organizer;
  private Calendar calendar;
  private List<MeetingRoom> rooms;

  // Scheduler is a singleton class that ensures it will have only one active instance at a time
  private static MeetingScheduler scheduler = null;
    
  // Created a static method to access the singleton instance of Scheduler class
  public static MeetingScheduler GetInstance() {
    if (scheduler == null) {
      scheduler = new MeetingScheduler();
    }
    return scheduler;
  }

  public bool ScheduleMeeting(List<User> users, Interval interval);
  public bool CancelMeeting(List<User> users, Interval interval);
  public bool BookRoom(MeetingRoom room, int numberOfPersons, Interval interval);
  public bool ReleaseRoom(MeetingRoom room, Interval interval);
  public MeetingRoom CheckRoomsAvailability(int numberOfPersons, Interval interval);
}

The Meeting class

```

```python
class __MeetingScheduler(object):
  __instances = None

  # Scheduler is a singleton class that ensures it will have only one active instance at a time
  def __new__(cls):
    if cls.__instances is None:
        cls.__instances = super(__MeetingScheduler, cls).__new__(cls)
    return cls.__instances

class MeetingScheduler(metaclass=__MeetingScheduler):
  def __init__(self, organizer, calendar):
    self.__organizer = organizer
    self.__calendar = calendar
    self.__rooms = []

  def schedule_meeting(self, users, interval):
    pass
  def cancel_meeting(self, users, interval):
    pass
  def book_room(self, room, number_of_persons, interval):
    pass
  def release_room(self, room, interval):
    pass
  def check_rooms_availability(self, number_of_persons, interval):
    pass

The Meeting class

```

```c++
class MeetingScheduler {
  private:
    // Scheduler is a singleton class that ensures it will have only one active instance at a time
    static MeetingScheduler *scheduler = nullptr;
    User organizer;
    Calendar calendar;
    vector<MeetingRooms> rooms;

    
  public:
    // Created a static method to access the singleton instance of Scheduler class
    static MeetingScheduler *getInstance() {
      if (scheduler == nullptr) {
        scheduler = new MeetingScheduler();
      }
      return scheduler;
    }

    bool scheduleMeeting(vector<User> users, Interval interval);
    bool cancelMeeting(vector<User> users, Interval interval);
    bool bookRoom(MeetingRoom room, int numberOfPersons, Interval interval);
    bool releaseRoom(MeetingRoom room, Interval interval);
    MeetingRoom checkRoomsAvailability(int numberOfPersons, Interval interval);
}

The Meeting class

```

```javascript
class Meeting {
    #id;
    #participantsCount;
    #participants;
    #interval;
    #room;
    #subject;

    constructor(id, participantsCount, interval, room, subject) {
        this.#id = id;
        this.#participantsCount = participantsCount;
        this.#participants = new Array();
        this.#interval = interval;
        this.#room = room;
        this.#subject = subject;
    }
  
  addParticipants(participants) {}
}

The Meeting class

```


### Notification
The Notification class is responsible for sending notifications to users about any new meetings or cancelations. The definition of this class is provided below:

```java
public class Notification {
  private int notificationId;
  private string content;
  private Date creationDate;

  public boolean sendNotification(User user);
  public boolean cancelNotification(User user);
}

The Notification class

```

```c#
class Notification {
  private int notificationId;
  private string content;
  private DateTime creationDate;

  public bool SendNotification(User user);
  public bool CancelNotification(User user);
}

The Notification class

```

```python
class Notification:
  def __init__(self, notification_id, content, creation_date):
    self.__notification_id = notification_id
    self.__content = content
    self.__creation_date = creation_date
  def send_notification(self, user):
    pass
  def cancel_notification(self, user):
    pass

The Notification class

```

```c++
class Notification {
  private:
    int notificationId;
    string content;
    time_t creationDate;

  public:
    bool sendNotification(User user);
    bool cancelNotification(User user);
}

The Notification class

```

```javascript
class MeetingScheduler {
  #organizer;
  #calendar;
  #rooms;

  // Scheduler is a singleton class that ensures it will have only one active instance at a time
  constructor(organizer, calendar) {
    if (MeetingScheduler._instance) {
      throw new Error("Singleton classes can't be instantiated more than once.")
    }

    MeetingScheduler._instance = this;
    this.#organizer = organizer;
    this.#calendar = calendar;
    this.#rooms = new Array();
  }

  // Created a static method to access the singleton instance of Scheduler class
  static getInstance() {
    if(!MeetingScheduler._instance) {
      return new MeetingScheduler();
    }

    return MeetingScheduler._instance;
  }

  scheduleMeeting(users, interval) {}
  cancelMeeting(users, interval) {}
  bookRoom(room, numberOfPersons, interval) {}
  releaseRoom(room, interval) {}
  checkRoomsAvailability(numberOfPersons, interval) {}
}

The Notification class

```
## Wrapping up
We've explored the complete design of the meeting scheduler in this chapter. We've looked at how the meeting scheduler can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
