# Code for the Parking Lot
We’ve gone over the different aspects of the parking lot system and observed the attributes attached to the problem using various UML diagrams. Let’s explore the more practical side of things, where we will work on implementing the parking lot system using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the parking lot system:

- Java

- C#

- Python

- C++

- JavaScript

## Parking lot classes
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we aren’t defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```

### Enumerations and custom data type
First of all, we will define all the enumerations required in the parking lot. According to the class diagram, there are two enumerations used in the system i.e., PaymentStatus and AccountStatus. The code to implement these enumerations and custom data types is as follows:
```
enumerations: A special data type which contains a set of predefined constants.
```

```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```
```java
// Enumeration
enum PaymentStatus {
  COMPLETED, 
  FAILED, 
  PENDING, 
  UNPAID, 
  REFUNDED
}

enum AccountStatus {
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  NONE
}

// Custom Person data type class
public class Person {
  private String name;
  private String address;
  private String phone;
  private String email;
}

// Custom Address data type class
public class Address {
  private int zipCode;
  private String address;
  private String city;
  private String state;
  private String country;
}
                    Definition for the constants
```

```c#
// Enumeration
enum PaymentStatus {
  COMPLETED, 
  FAILED, 
  PENDING, 
  UNPAID, 
  REFUNDED
}

enum AccountStatus {
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  NONE
}

// Custom Person data type class
class Person {
  private string name;
  private string address;
  private string phone;
  private string email;
}

// Custom Address data type class
class Address {
  private int zipCode;
  private string address;
  private string city;
  private string state;
  private string country;
}
                       Definitions for constants
```

```python
// Enumeration
enum PaymentStatus {
  COMPLETED, 
  FAILED, 
  PENDING, 
  UNPAID, 
  REFUNDED
}

enum AccountStatus {
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  NONE
}

// Custom Person data type class
class Person {
  private string name;
  private string address;
  private string phone;
  private string email;
}

// Custom Address data type class
class Address {
  private int zipCode;
  private string address;
  private string city;
  private string state;
  private string country;
}
                  Definitions for constants
```
```c++
// Enumeration
enum PaymentStatus {
  COMPLETED, 
  FAILED, 
  PENDING, 
  UNPAID, 
  REFUNDED
}

enum AccountStatus {
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  NONE
}

// Custom Person data type class
class Person {
  private string name;
  private string address;
  private string phone;
  private string email;
}

// Custom Address data type class
class Address {
  private int zipCode;
  private string address;
  private string city;
  private string state;
  private string country;
}
                    Definitions for constants
```

```javascript
// Enumeration
enum PaymentStatus {
  COMPLETED, 
  FAILED, 
  PENDING, 
  UNPAID, 
  REFUNDED
}

enum AccountStatus {
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  NONE
}

// Custom Person data type class
class Person {
  private string name;
  private string address;
  private string phone;
  private string email;
}

// Custom Address data type class
class Address {
  private int zipCode;
  private string address;
  private string city;
  private string state;
  private string country;
}
                      Definitions for constants
```
### Parking spots
The first section of the parking lot system that we will work on is the ParkingSpot class, which will act as a base class for four different types of parking spots: handicapped, compact, large, and motorcycle. This will have an instance of the Vehicle class. The definition of the ParkingSpot class and the classes being derived from it are given below:
```java
// ParkingSpot is an abstract class
public abstract class ParkingSpot {
  private int id;
  private boolean isFree;
  private Vehicle vehicle;

  public boolean getIsFree();
  public abstract boolean assignVehicle(Vehicle vehicle);
  public boolean removeVehicle();
}

public class Handicapped extends ParkingSpot {
  public boolean assignVehicle(Vehicle vehicle) {
    // definition
  }
}

public class Compact extends ParkingSpot {
  public boolean assignVehicle(Vehicle vehicle) {
    // definition
  }
}

public class Large extends ParkingSpot {
  public boolean assignVehicle(Vehicle vehicle) {
    // definition
  }
}

public class Motorcycle extends ParkingSpot {
  public boolean assignVehicle(Vehicle vehicle) {
    // definition
  }
}
                ParkingSpot and its derived classes
```

```c#
// ParkingSpot is an abstract class
public abstract class ParkingSpot {
    private int id;
    private bool isFree;
    private Vehicle vehicle; 

    public bool GetIsFree(); 
    public abstract bool AssignVehicle(Vehicle vehicle); 
    public bool RemoveVehicle(); 
}

class Handicapped : ParkingSpot {
    public override bool AssignVehicle(Vehicle vehicle) {
        // definition
    }
}

class Compact : ParkingSpot {
    public override bool AssignVehicle(Vehicle vehicle) {
        // definition
    }
}

class Large : ParkingSpot {
    public override bool AssignVehicle(Vehicle vehicle) {
        // definition
    }
}

class Motorcycle : ParkingSpot {
    public override bool AssignVehicle(Vehicle vehicle) {
        // definition
    }
}
                    ParkingSpot and its derived classes
```

```python
# ParkingSpot is an abstract class
from abc import ABC, abstractmethod

class ParkingSpot(ABC):
  def __init__(self, id, isFree, vehicle):
    self.__id = id
    self.__isFree = isFree
    self.__vehicle = vehicle # Refers to an instance of the Vehicle class

  def get_is_free(self):
    pass

  # vehicle here refers to an instance of the Vehicle class
  @abstractmethod
  def assign_vehicle(self, vehicle):
    pass

  def remove_vehicle(self):
    pass

class Handicapped(ParkingSpot):
  # vehicle here refers to an instance of the Vehicle class
  def __init__(self, id, isFree, vehicle):
    super().__init__(id, isFree, vehicle)

  # vehicle here refers to an instance of the Vehicle class
  def assign_vehicle(self, vehicle):
    pass

class Compact(ParkingSpot):
  # vehicle here refers to an instance of the Vehicle class
  def __init__(self, id, isFree, vehicle):
    super().__init__(id, isFree, vehicle)

  # vehicle here refers to an instance of the Vehicle class
  def assign_vehicle(self, vehicle):
    pass

class Large(ParkingSpot):
  # vehicle here refers to an instance of the Vehicle class
  def __init__(self, id, isFree, vehicle):
    super().__init__(id, isFree, vehicle)

  # vehicle here refers to an instance of the Vehicle class
  def assign_vehicle(self, vehicle):
    pass

class Motorcycle(ParkingSpot):
  # vehicle here refers to an instance of the Vehicle class
  def __init__(self, id, isFree, vehicle):
    super().__init__(id, isFree, vehicle)

  # vehicle here refers to an instance of the Vehicle class
  def assign_vehicle(self, vehicle):
    pass
                    ParkingSpot and its derived classes
 ```
 
 ```c++
 // ParkingSpot is an abstract class
class ParkingSpot {
  private:
    int id;
    bool isFree;
    Vehicle vehicle; 

  public:
    bool isFree(); 
    virtual bool assignVehicle(Vehicle vehicle) = 0; 
    bool removeVehicle(); 
};

class Handicapped : public ParkingSpot {
  public:
    bool assignVehicle(Vehicle vehicle) {
        // definition
    }
};

class Compact : public ParkingSpot {
  public:
    bool assignVehicle(Vehicle vehicle) {
        // definition
    }
};

class Large : public ParkingSpot {
  public: 
    bool assignVehicle(Vehicle vehicle) {
        // definition
    }
};

class Motorcycle : public ParkingSpot {
  public: 
    bool assignVehicle(Vehicle vehicle) {
        // definition
    }
};
             ParkingSpot and its derived classes
```

```javascript
// ParkingSpot is an abstract class
class ParkingSpot {
    #id;
    #isFree;
    #vehicle;
    constructor(id, isFree, vehicle) {
        if (this.constructor == ParkingSpot) {
            throw new Error("Abstract classes can't be instantiated.");
        }
        else {
            this.#id = id;
            this.#isFree = isFree;
            this.#vehicle = vehicle; // Refers to an instance of the Vehicle class
        }
    }
    getIsFree() { }
    // vehicle here refers to an instance of the Vehicle class
    assignVehicle(vehicle) { }
    removeVehicle() { }
}

class Handicapped extends ParkingSpot {
    // vehicle here refers to an instance of the Vehicle class
    assignVehicle(vehicle) {
        // definition
    }
}

class CompactSpot extends ParkingSpot {
    // vehicle here refers to an instance of the Vehicle class
    assignVehicle(vehicle) {
        // definition
    }
}

class LargeSpot extends ParkingSpot {
    // vehicle here refers to an instance of the Vehicle class
    assignVehicle(vehicle) {
        // definition
    }
}

class Motorcycle extends ParkingSpot {
    // vehicle here refers to an instance of the Vehicle class
    assignVehicle(vehicle) {
        // definition
    }
}
                      ParkingSpot and its derived classes
```

### Vehicle
Vehicle will be another abstract class, which serves as a parent for four different types of vehicles: car, truck, van, and motor cycle. The definition of the Vehicle and its child classes are given below:

```java
// Vehicle is an abstract class
public abstract class Vehicle {
  private int licenseNo;
  public abstract void assignTicket(ParkingTicket ticket);
}

public class Car extends Vehicle {
  public void assignTicket(ParkingTicket ticket) {
    // definition
  }
}

public class Van extends Vehicle {
  public void assignTicket(ParkingTicket ticket) {
    // definition
  }
}

public class Truck extends Vehicle {
  public void assignTicket(ParkingTicket ticket) {
    // definition
  }
}

public class MotorCycle extends Vehicle {
  public void assignTicket(ParkingTicket ticket) {
    // definition
  }
}
            Vehicle and its child classes
```

```c#
// Vehicle is an abstract class
public abstract class Vehicle {
    private string licenseNo;
    public abstract void AssignTicket(ParkingTicket ticket); 
}

class Car : Vehicle {
    public override void AssignTicket(ParkingTicket ticket) {
        // definition
    }
}

class Van : Vehicle {
    public override void AssignTicket(ParkingTicket ticket) {
        // definition
    }
}

class Truck : Vehicle {
    public override void AssignTicket(ParkingTicket ticket) {
        // definition
    }
}

class MotorCycle : Vehicle {
    public override void AssignTicket(ParkingTicket ticket) {
        // definition
    }
}
       Vehicle and its child classes
```

```python
# Vehicle is an abstract class
from abc import ABC, abstractmethod

class Vehicle(ABC):
  def __init__(self, license_no):
    self.__license_no = license_no

  # ticket here refers to an instance of the ParkingTicket class
  @abstractmethod
  def assign_ticket(self, ticket):
    pass

class Car(Vehicle):
  # ticket here refers to an instance of the ParkingTicket class
  def __init__(self, license_no):
    super().__init__(license_no)
  
  # ticket here refers to an instance of the ParkingTicket class
  def assign_ticket(self, ticket):
    pass

class Van(Vehicle):
  # ticket here refers to an instance of the ParkingTicket class
  def __init__(self, license_no):
    super().__init__(license_no)

  # ticket here refers to an instance of the ParkingTicket class
  def assign_ticket(self, ticket):
    pass

class Truck(Vehicle):
  # ticket here refers to an instance of the ParkingTicket class
  def __init__(self, license_no, ticket):
    super().__init__(license_no, ticket)

  # ticket here refers to an instance of the ParkingTicket class
  def assign_ticket(self, ticket):
    pass

class MotorCycle(Vehicle):
  # ticket here refers to an instance of the ParkingTicket class
  def __init__(self, license_no, ticket):
    super().__init__(license_no, ticket)

  # ticket here refers to an instance of the ParkingTicket class
  def assign_ticket(self, ticket):
    pass
    
                  Vehicle and its child classes
```

```c++
// Vehicle is an abstract class
class Vehicle {
  private:
    string licenseNo;

  public:
    void virtual assignTicket(ParkingTicket ticket) = 0; 
};

class Car : public Vehicle {
  public:
    void assignTicket(ParkingTicket ticket) {
        // definition
    } 
};

class Van : public Vehicle {
  public:
    void assignTicket(ParkingTicket ticket) {
        // definition
    } 
};

class Truck : public Vehicle {
  public:
    void assignTicket(ParkingTicket ticket) {
        // definition
    } 
};

class MotorCycle : public Vehicle {
  public:
    void assignTicket(ParkingTicket ticket) {
        // definition
    } 
};
             Vehicle and its child classes
```

```javascript
// Vehicle is an abstract class
class Vehicle {
  #licenseNo;

  constructor(licenseNo) {
    if (this.constructor == Vehicle) {
      throw new Error("Abstract classes can't be instantiated.");
    }
    else {
      this.#licenseNo = licenseNo;
    }
  }

  // ticket here refers to an instance of the ParkingTicket class
  assignTicket(ticket) { }
}

class Car extends Vehicle {
  // ticket here refers to an instance of the ParkingTicket class
  assignTicket(ticket) {
        // definition
    }
}

class Van extends Vehicle {
  // ticket here refers to an instance of the ParkingTicket class
  assignTicket(ticket) {
        // definition
    }
}

class Truck extends Vehicle {
  // ticket here refers to an instance of the ParkingTicket class
  assignTicket(ticket) {
        // definition
    }
}

class MotorCycle extends Vehicle {
  // ticket here refers to an instance of the ParkingTicket class
  assignTicket(ticket) {
        // definition
    }
}
              Vehicle and its child classes
```


### Account
The Account class will be an abstract class, which will have the actors, Admin and ParkingAttendant, as child classes. The definition of these classes is given below:

```java
public abstract class Account {
  // Data members
  private String userName;
  private String password;
  private Person person; // Refers to an instance of the Person class
  private AccountStatus status; // Refers to the AccountStatus enum

  public abstract boolean resetPassword();
}

public class Admin extends Account {
  // spot here refers to an instance of the ParkingSpot class
  public boolean addParkingSpot(ParkingSpot spot);
  // displayBoard here refers to an instance of the DisplayBoard class
  public boolean addDisplayBoard(DisplayBoard displayBoard);
  // entrance here refers to an instance of the Entrance class
  public boolean addEntrance(Entrance entrance);
  // exit here refers to an instance of the Exit class
  public boolean addExit(Exit exit;

  // Will implement the functionality in this class
  public boolean resetPassword() {
    // definition
  }
}

public class ParkingAttendant extends Account {
  public boolean processTicket(String ticketNumber);

  // Will implement the functionality in this class
  public boolean resetPassword() {
    // definition
  }
}
            Account and its child classes
```

```c#
public abstract class Account {
  // Data members
  private string userName;
  private string password;
  private Person person; // Refers to an instance of the Person class
  private AccountStatus status; // Refers to the AccountStatus enum

  public abstract bool ResetPassword();
}

class Admin : Account {
  // spot here refers to an instance of the ParkingSpot class
  public bool AddParkingSpot(ParkingSpot spot);
  // displayBoard here refers to an instance of the DisplayBoard class
  public bool AddDisplayBoard(DisplayBoard displayBoard);
  // entrance here refers to an instance of the Entrance class
  public bool AddEntrance(Entrance entrance);
  // exit here refers to an instance of the Exit class
  public bool AddExit(Exit exit;

  // Will implement the functionality in this class
  public override bool ResetPassword() {
    // definition
  }
}

class ParkingAttendant : Account {
  public bool ProcessTicket(string ticketNumber);

  // Will implement the functionality in this class
  public override bool ResetPassword() {
    // definition
  }
}
      Account and its child classes
```

```python
from abc import ABC, abstractmethod

class Account(ABC):
  # Data members
  def __init__(self, user_name, password, person, status):
    self.__user_name = user_name
    self.__password = password
    self.__person = person # Refers to an instance of the Person class
    self.__status = status # Refers to the AccountStatus enum

  @abstractmethod
  def reset_password(self):
    pass

class Admin(Account):
  def __init__(self, user_name, password, person, status):
    super().__init__(user_name, password, person, status)

  # spot here refers to an instance of the ParkingSpot class
  def add_parking_spot(self, spot):
    pass

  # display_board here refers to an instance of the DisplayBoard class
  def add_display_board(self, display_board):
    pass

  # entrance here refers to an instance of the Entrance class
  def add_entrance(self, entrance):
    pass

  # exit here refers to an instance of the Exit class
  def add_exit(self, exit):
    pass

  def reset_password(self):
    # Will implement the functionality in this class
    pass

class ParkingAttendant(Account):
  def __init__(self, user_name, password, person, status):
    super().__init__(user_name, password, person, status)

  def process_ticket(self, ticket_number):
    pass

  def reset_password(self):
    # Will implement the functionality in this class
    pass
              Account and its child classes
```

```c++
class Account {
  // Data members
  private: 
    string userName;
    string password;
    Person person; // Refers to an instance of the Person class
    AccountStatus status; // Refers to the AccountStatus enum

  public:
    virtual bool resetPassword() = 0;
}

class Admin : public Account {
  public: 
    // spot here refers to an instance of the ParkingSpot class
    bool addParkingSpot(ParkingSpot spot);
    // displayBoard here refers to an instance of the DisplayBoard class
    bool addDisplayBoard(DisplayBoard displayBoard);
    // entrance here refers to an instance of the Entrance class
    bool addEntrance(Entrance entrance);
    // exit here refers to an instance of the Exit class
    bool addExit(Exit exit;
  
    // Will implement the functionality in this class
    bool resetPassword() {
      // definition
    }
}

class ParkingAttendant : public Account {
  public: 
    bool processTicket(string ticketNumber);

    // Will implement the functionality in this class
    bool resetPassword() {
      // definition
    }
}
           Account and its child classes
```

```javascript
class Account {
  #userName;
  #password;
  #person;
  #status;

  // Data members
  constructor(userName, password, person, status) {
    if (this.constructor == Account) {
      throw new Error("Abstract classes can't be instantiated.");
    }
    else {
      this.#userName = userName
      this.#password = password
      this.#person = person // Refers to an instance of the Person class
      this.#status = status // Refers to the AccountStatus enum
    }
  }

  resetPassword() {}
}

class Admin extends Account {
  // spot here refers to an instance of the ParkingSpot class
  addParkingSpot(spot) {}
  // displayBoard here refers to an instance of the DisplayBoard class
  addDisplayBoard(displayBoard) {}
  // entrance here refers to an instance of the Entrance class
  addEntrance(entrance) {}
  // exit here refers to an instance of the Exit class
  addExit(exit) {}
  
  // Will implement the functionality in this class
  resetPassword() {
    // definition
  }
}

class ParkingAttendant extends Account {
  processTicket(ticketNumber) {}
  
  // Will implement the functionality in this class
  resetPassword() {
    // definition
  }
}
          Account and its child classes
```

### Display board and parking rate
This section contains the DisplayBoard and ParkingRate classes that only have the composition class with the ParkingLot class. This relationship is highlighted in the ParkingLot class. The definition of these classes is given below:
```java
public class DisplayBoard {
  // Data members
  private int id;
  private <List>Handicapped handicappedSpot;
  private <List>Compact compactSpot;
  private <List>Large largeSpot;
  private <List>MotorCycle motorCycleSpot;
  
  // Member function
  public void showFreeSlot();
}

public class ParkingRate {
  // Data members
  private double hours;
  private double rate;

  // Member function
  public void calculate();
}
   The DisplayBoard and ParkingRate classes
```

```c$
class DisplayBoard {
  // Data members
  private int id;
  private <List>Handicapped handicappedSpot;
  private <List>Compact compactSpot;
  private <List>Large largeSpot;
  private <List>MotorCycle motorCycleSpot;

  // Member functions
  public void ShowFreeSlot();
}

class ParkingRate {
  // Data members
  private double hours;
  private double rate;

  // Member function
  public void Calculate();
}
         The DisplayBoard and ParkingRate classes
```

```python
class DisplayBoard:
  def __init__(self, id, handicapped_spot, compact_spot, large_spot, motor_cycle_spot):
    self.__id = id
    self.__handicapped_spot = handicapped_spot # Refers to an instance of the Handicapped class 
    self.__compact_spot = compact_spot # Refers to an instance of the Compact class
    self.__large_spot = large_spot # Refers to an instance of the Large class
    self.__motor_cycle_spot = motor_cycle_spot # Refers to an instance of the Motorcycle class 

  # Member functions
  def show_free_slot(self):
    pass

class ParkinRate:
  def __init__(self, hours, rate):
    self.__hours = hours
    self.__rate = rate

  # Member function
  def calculate(self):
    pass
```

```c++
class DisplayBoard {
// Data members
  private:
    int id;
    vector<Handicapped> handicappedSpot;
    vector<Compact> compactSpot;
    vector<Large> largeSpot;
    vector<MotorCycle> motorCycleSpot;

  // Member functions
  public:
    void showFreeSlot();
};

class ParkingRate {
  // Data members
  private:
    double hours;
    double rate;

// Member function
  public: 
    void calculate();
};
              The DisplayBoard and ParkingRate classes
```

```javascript
class DisplayBoard {
    // Data members
    #id;
    #handicapped;
    #compact;
    #large;
    #motorCycle;

    constructor(id, handicappedSpot, compactSpot, largeSpot, motorCycleSpot) {
        this.#id = id;
        this.#handicapped = new Array(); 
        this.#compact = new Array(); 
        this.#large = new Array();  
        this.#motorCycle = new Array();  
    }

    // Member functions
    showFreeSlot() {}
}

class ParkinRate {
    // Data members
    #id;
    #hours;
    #rate;
    constructor(id, hours, rate) {
        this.#id = id;
        this.#hours = hours;
        this.#rate = rate;
    }

    // Member function
    calculate() {}
}
           The DisplayBoard and ParkingRate classes
```


### Entrance and exit
This section contains the Entrance and Exit classes, both of which are associated with the ParkingTicket class. The definition of the Entrance and Exit classes is given below:
```java
public class Entrance {
  // Data members 
  private int id;
  private ParkingTicket ticket;

  // Member function
  public ParkingTicket getTicket(ParkingTicket ticket);
}

public class Exit {
  // Data members 
  private int id;
  private ParkingTicket ticket;

  // Member function
  public void validateTicket(ParkingTicket ticket);
}
       The Entrance and Exit classes
```

```c#
class Entrance {
    // Data members 
    private int id;
    private ParkingTicket ticket; 

    // Member function
    public ParkingTicket GetTicket(ParkingTicket ticket); 
}

class Exit {
    // Data members 
    private int id;
    private ParkingTicket ticket; 

    // Member function
    public void ValidateTicket(ParkingTicket ticket); 
}
           The Entrance and Exit classes
```

```python
class Entrance:
  def __init__(self, id, ticket):
    self.__id = id
    self.__ticket = ticket # Refers to an instance of the ParkingTicket class

  # ticket here refers to an instance of the ParkingTicket class
  def get_ticket(self, ticket):
    pass

class Exit:
  def __init__(self, id, ticket):
    self.__id = id
    self.__ticket = ticket # Refers to an instance of the ParkingTicket class

  # ticket here refers to an instance of the ParkingTicket class
  def validate_ticket(self, ticket):
    pass
                 The Entrance and Exit classes
```

```c++
class Entrance {
  // Data members 
  private:
    int id;
    ParkingTicket ticket; 

  // Member function
  public:
    ParkingTicket getTicket(ParkingTicket ticket); 
};

class Exit {
  // Data members 
  private:
    int id;
    ParkingTicket ticket; 

  // Member function
  public:
    void validateTicket(ParkingTicket ticket); 
};
             The Entrance and Exit classes
```

```javascript
class Entrance {
    // Data members 
    #id;
    #ticket;
    constructor(id, ticket) {
        this.#id = id;
        this.#ticket = ticket; // Refers to an instance of the ParktingTicket class
    }

    // ticket here refers to an instance of the ParktingTicket class
    getTicket(ticket) { }
}

class Exit {
    // Data members 
    #id;
    #ticket;
    constructor(id, ticket) {
        this.#id = id;
        this.#ticket = ticket; // Refers to an instance of the ParktingTicket class
    }

    // ticket here refers to an instance of the ParktingTicket class
    validateTicket(ticket){ }
}
               The Entrance and Exit classes
```

### Parking ticket
The definition of the ParkingTicket class can be found below. This contains instancesof the Vehicle, Payment, Entrance and Exit classes:
```java
public class ParkingTicket {
    private int ticketNo;
    private Date timestamp;
    private Date exit;
    private double amount;
    private boolean status;

    // Following are the instances of their respective classes
    private Vehicle vehicle;
    private Payment payment;
    private Entrance entrance;
    private Exit exitIns;    
}
        The ParkingTicket class
```

```c#
public class ParkingTicket {
    private int ticketNo;
    private DateTime timestamp;
    private DateTime exit;
    private double amount;
    private bool status;
    
    // Following are the instances of their respective classes
    private Vehicle vehicle;
    private Payment payment;
    private Entrance entrance;
    private Exit exitIns;    
}
          The ParkingTicket class
```

```python
class ParkingTicket:
  def __init__(self, ticket_no, timestamp, exit, amount, status, vehicle, payment, entrance, exit_ins):
    self.__ticket_no = ticket_no
    self.__timestamp = timestamp
    self.__exit = exit
    self.__amount = amount
    self.__status = status
    
    # Following are the instances of their respective classes
    self__vehicle = vehicle
    self__payment = payment
    self__entrance = entrance
    self__exit_ins = exit_ins
     
     The ParkingTicket class
```

```c++
class ParkingTicket {
  private: 
    int ticketNo;
    time_t timestamp;
    time_t exit;
    double amount;
    bool status;
  
    // Following are the instances of their respective classes
    Vehicle vehicle;
    Payment payment;
    Entrance entrance;
    Exit exitIns;    
};

              The ParkingTicket class
```

```javascript
class ParkingTicket{
    #ticketNo;
    #timestamp;
    #exit;
    #amount;
    #status;
    #vehicle;
    #payment;
    #entrance;
    #exitIns;

    constructor(ticketNo, timestamp, exit,amount, status, vehicle, payment, entrance, exitIns) {
        this.#ticketNo = ticketNo;
        this.#timestamp = timestamp;
        this.#exit = exit;
        this.#amount = amount;
        this.#status = status;

        // Following are the instances of their respective classes
        this.#vehicle = vehicle;
        this.#payment = payment;
        this.#entrance = entrance;
        this.#exitIns = exitIns;
    }
}
                 The ParkingTicket class
```

### Payment
The Payment class is another abstract class, with the Cash and CreditCard classes as its child. This takes the PaymentStatus enumeration and the dateTime data type to keep track of the payment status and time. The definition of this class is given below

```java
// Payment is an abstract class
public abstract class Payment {
    private double amount;
    private PaymentStatus status;
    private Date timestamp;

    public abstract boolean initiateTransaction();
}

public class Cash extends Payment {
    public boolean initiateTransaction() {
        // definition
    }
}

public class CreditCard extends Payment {
    public boolean initiateTransaction() {
        // definition
    }
}
        Payment and its derived classes
```

```c#
// Payment is an abstract class
public abstract class Payment {
    private double amount;
    private PaymentStatus status;
    private DateTime timestamp;
    public abstract bool InitiateTransaction();
}

class Cash : Payment {
    public override bool InitiateTransaction() {
        // definition
    }
}

class CreditCard : Payment {
    public override bool InitiateTransaction() {
        // definition
    }
}
            Payment and its derived classes
```

```python
# Payment is an abstract class
from abc import ABC, abstractmethod

class Payment(ABC):
  def __init__(self, amount, status, timestamp):
    self.__amount = amount
    self.__status = status # Refers to the PaymentStatus enum
    self.__timestamp = timestamp

  @abstractmethod
  def initiate_transaction(self):
    pass

class Cash(Payment):
  def __init__(self, amount, status, timestamp):
    super().__init__(amount, status, timestamp)

  def initiate_transaction(self):
    pass

class CreditCard(Payment):
  def __init__(self, amount, status, timestamp):
    super().__init__(amount, status, timestamp)

  def initiate_transaction(self):
    pass
          Payment and its derived classes
```

```c++
// Payment is an abstract class
class Payment {
    private:
        double amount;
        PaymentStatus status;
        time_t timestamp;

    public virtual bool initiateTransaction() = 0;
};

class Cash : public Payment {
    public bool initiateTransaction() {
        // definition
    }
};

class CreditCard : public Payment {
    public bool initiateTransaction() {
        // definition
    }
};
      Payment and its derived classes
```

```javascript
// Payment is an abstract class
class Payment {
    #amount;
    #status;
    #timestamp;

    constructor(amount, status, timestamp) {
        if (this.constructor == Payment) {
            throw new Error("Abstract classes can't be instantiated.");
        }
        else {
            this.#amount = amount;
            this.#status = status; // Refers to the PaymentStatus enum
            this.#timestamp = timestamp;
        }
    }
    initiateTransaction() { }
}
class Cash extends Payment{
    initiateTransaction(){
        // definition
    }
}
class CreditCard extends Payment{
    initiateTransaction(){
        // definition
    }
}

           Payment and its derived classes
```
### Parking lot
The final class of the parking lot system is the ParkingLot class which will be a Singleton class, meaning the entire system will only have one instance of this class. The definition of this class is given below:

```java
public class ParkingLot {
    private int id;
    private String name;
    private String address;
    private ParkingRate parkingRate;

    private HashMap<String, Entrance> entrance;
    private HashMap<String, Exit> exit;

    // Create a hashmap that identifies all currently generated tickets using their ticket number
    private HashMap<String, ParkingTicket> tickets;

    // The ParkingLot is a singleton class that ensures it will have only one active instance at a time
    // Both the Entrance and Exit classes use this class to create and close parking tickets
    private static ParkingLot parkingLot = null;

    // Created a private constructor to add a restriction (due to Singleton)
    private ParkingLot() {
        // Call the name, address, parking_rate elements of the customer in the parking lot from the database
        // Create initial entrance and exit hashmaps respectively
    }

    // Created a static method to access the singleton instance of ParkingLot
    public static ParkingLot getInstance() {
        if (parkingLot == null) {
            parkingLot = new ParkingLot();
        }
        return parkingLot;
    }

    public boolean addEntrance(Entrance entrance){}
    public boolean addExit(Exit exit){}

    // This function allows parking tickets to be available at multiple entrances
    public ParkingTicket getParkingTicket(Vehicle vehicle) {}

    public boolean isFull(ParkingSpot type){}
}
          The ParkingLot class
```

```c#
class ParkingLot {
    private int id;
    private string name;
    private string address;
    private ParkingRate parkingRate;

    private Dictionary<string, Entrance> entrance;
    private Dictionary<string, Exit> exit;

    // Create a hashmap that identifies all currently generated tickets using their ticket number
    private Dictionary<string, ParkingTicket> tickets;

    // The ParkingLot is a singleton class that ensures it will have only one active instance at a time
    // Both the Entrance and Exit classes use this class to create and close parking tickets
    private static ParkingLot parkingLot = null;

    // Created a private constructor to add a restriction (due to Singleton)
    ParkingLot() {
        // Call the name, address, parking_rate elements of the customer in the parking lot from the database
        // Create initial entrance and exit hashmaps respectively
    }

    // Created a static method to access the singleton instance of ParkingLot
    public static ParkingLot GetInstance() {
        get {
            if (parkingLot == null) {
                parkingLot = new ParkingLot();
            }
            return parkingLot;
        }
    }

    public bool AddEntrance(Entrance entrance) {}
    public bool AddExit(Exit exit) {}

    // This function allows parking tickets to be available at multiple entrances
    public ParkingTicket GetParkingTicket(Vehicle vehicle) {}

    public bool IsFull(ParkingSpot type) {}
}
                 The ParkingLot class
```

```python
# The __ParkingLot is a singleton class that ensures it will have only one active instance at a time
# Both the Entrance and Exit classes use this class to create and close parking tickets
class __ParkingLot(object):
  __instances = None
  
  def __new__(cls):
    if cls.__instances is None:
        cls.__instances = super(__ParkingLot, cls).__new__(cls)
    return cls.__instances

class ParkingLot(metaclass=__ParkingLot):
  def __init__(self, id, name, address, parking_rate):
    # Call the name, address, parking_rate elements of the customer in the parking lot from the database
    self.__id = id
    self.__name = name
    self.__address = address
    self.__parking_rate = parking_rate

    # Create initial entrance and exit hashmaps respectively
    self.__entrance = {}
    self.__exit = {}

    # Create a hashmap that identifies all currently generated tickets using their ticket number
    self.__tickets = {}

  # entrance here refers to an instance of the Entrance class
  def add_entrance(self, entrance):
    pass

  # exit here refers to an instance of the Exit class
  def add_exit(self, exit):
    pass

  # This function allows parking tickets to be available at multiple entrances
  # vehicle here refers to an Vehicle of the Exit class
  # Returns a ParkingTicket instance
  def get_parking_ticket(self, vehicle):
    pass

   # type here refers to an instance of the ParkingSpot class
  def is_full(self, type):
    pass
                 The ParkingLot class
```

```c++
class ParkingLot {
    private:
        int id;
        string name;
        string address;
        ParkingRate parkingRate;

        map<string, Entrance> entrance;
        map<string, Exit> exit;

        // Create a hashmap that identifies all currently generated tickets using their ticket number
        map<string, ParkingTicket> tickets;

        // The ParkingLot is a singleton class that ensures it will have only one active instance at a time
        // Both the Entrance and Exit classes use this class to create and close parking tickets
        static ParkingLot parkingLot = NULL;

        // Created a private constructor to add a restriction (due to Singleton)
        ParkingLot() {
            // Call the name, address, parking_rate elements of the customer in the parking lot from the database
            // Create initial entrance and exit hashmaps respectively
        }

    // Created a static method to access the singleton instance of ParkingLot
    public:
        static ParkingLot getInstance() {
            if (parkingLot == NULL) {
                parkingLot = new ParkingLot();
            }
            return parkingLot;
        }

        bool addEntrance(Entrance entrance) {}
        bool addExit(Exit exit) {}

        // This function allows parking tickets to be available at multiple entrances
        ParkingTicket getParkingTicket(Vehicle vehicle) {}

        bool isFull(ParkingSpot type) {}
};
                    The ParkingLot class
```

```javascript
class ParkingLot {
    #id;
    #name;
    #address;
    #parkingRate;

    constructor(id, name, address, parkingRate) {
        if (ParkingLot._instance){
            throw new Error("Singleton classes can't be instantiated more than once.")
        }
        // The ParkingLot is a singleton class that ensures it will have only one active instance at a time
        // Both the Entrance and Exit classes use this class to create and close parking tickets
        ParkingLot._instance = this;

        // Call the name, address, parking_rate elements of the customer in the parking lot from the database
        this.#id = id;
        this.#name = name;
        this.#address = address;
        this.#parkingRate = parkingRate;

        // Create initial entrance and exit hashmaps respectively
        this.entrance = new Map();
        this.exit = new Map();

        // Create a hashmap that identifies all currently generated tickets using their ticket number
        this.tickets = new Map();
    }
    // Created a static method to access the singleton instance of ParkingLot
    static getInstance() {
        if(!ParkingLot._instance){
            return new ParkingLot();
        }
        return ParkingLot._instance;
    }
    
    // entrance here refers to an instance of the Entrance class
    addEntrance(entrance) {}
    // exit here refers to an instance of the Exit class
    addExit(exit) {}

    // This function allows parking tickets to be available at multiple entrances
    // vehicle here refers to an instance of the Vehicle class
    // Returns a ParkingTicket instance
    getParkingTicket(vehicle) {}

    // type here refers to an instance of the ParkingSpot class
    isFull(type) {}
}
                    The ParkingLot class
```

## Wrapping up
