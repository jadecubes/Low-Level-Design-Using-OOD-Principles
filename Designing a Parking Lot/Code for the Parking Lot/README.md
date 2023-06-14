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
```
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
### Account
### Display board and parking rate
### Entrance and exit
### Parking ticket
### Payment
### Parking lot
## Wrapping up
