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

```c$
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
### Parking ticket
### Payment
### Parking lot
## Wrapping up
