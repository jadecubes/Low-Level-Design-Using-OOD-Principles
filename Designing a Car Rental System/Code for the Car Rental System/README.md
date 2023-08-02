# Code for the Car Rental System
We’ve reviewed different aspects of the car rental system and observed the attributes attached to the problem using various UML diagrams. Let’s explore the more practical side of things, where we will work on implementing the car rental system using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the car rental system:

- Java

- C#

- Python

- C++

- JavaScript

## Car rental system classes
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public methods function.
```
### Enumerations
First, we will define all the enumerations required in the car rental system. According to the class diagram, there are seven enumerations used in the system, i.e., VehicleStatus, AccountStatus, ReservationStatus, PaymentStatus, VanType, CarType, and VehicleLogType. The code to implement these enumerations is as follows:
```
Note: JavaScript does not support enumerations, so we will use the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```

```java
// definition of enumerations used in the car rental system
enum VehicleStatus {
  AVAILABLE,
  RESERVED, 
  LOST, 
  BEING_SERVICED
}

enum AccountStatus {
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  BLOCKED
}

enum ReservationStatus {
  ACTIVE, 
  PENDING, 
  CONFIRMED, 
  COMPLETED, 
  CANCELED
}

enum PaymentStatus {
  UNPAID, 
  PENDING, 
  COMPLETED,  
  CANCELED,  
  REFUNDED
}

enum VanType {
  PASSENGER, 
  CARGO
}

enum CarType {
  ECONOMY, 
  COMPACT, 
  INTERMEDIATE, 
  STANDARD, 
  FULL_SIZE, 
  PREMIUM, 
  LUXURY
}

enum MotorcycleType {
  STANDARD,
  CRUISER,
  TOURING,
  SPORTS,
  OFF_ROAD,
  DUAL_PURPOSE
}

enum TruckType {
  LIGHT_DUTY,
  MEDIUM_DUTY,
  HEAVY_DUTY
}

enum VehicleLogType {
  ACCIDENT, 
  FUELING, 
  CLEANING_SERVICE, 
  OIL_CHANGE, 
  REPAIR, 
  OTHER
}
```

```c#
// definition of enumerations used in the car rental system
enum VehicleStatus {
  AVAILABLE,
  RESERVED, 
  LOST, 
  BEING_SERVICED
}

enum AccountStatus {
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  BLOCKED
}

enum ReservationStatus {
  ACTIVE, 
  PENDING, 
  CONFIRMED, 
  COMPLETED, 
  CANCELED
}

enum PaymentStatus {
  UNPAID, 
  PENDING, 
  COMPLETED,  
  CANCELED,  
  REFUNDED
}

enum VanType {
  PASSENGER, 
  CARGO
}

enum CarType {
  ECONOMY, 
  COMPACT, 
  INTERMEDIATE, 
  STANDARD, 
  FULL_SIZE, 
  PREMIUM, 
  LUXURY
}

enum MotorcycleType {
  STANDARD,
  CRUISER,
  TOURING,
  SPORTS,
  OFF_ROAD,
  DUAL_PURPOSE
}

enum TruckType {
  LIGHT_DUTY,
  MEDIUM_DUTY,
  HEAVY_DUTY
}

enum VehicleLogType {
  ACCIDENT, 
  FUELING, 
  CLEANING_SERVICE, 
  OIL_CHANGE, 
  REPAIR, 
  OTHER
}
```

```python
# definition of enumerations used in the car rental system
class VehicleStatus(enum.Enum):
  AVAILABLE = 1
  RESERVED = 2
  LOST = 3
  BEING_SERVICED = 4

class AccountStatus(enum.Enum):
  ACTIVE = 1
  CLOSED = 2
  CANCELED = 3
  BLACKLISTED = 4
  BLOCKED = 5

class ReservationStatus(enum.Enum):
  ACTIVE = 1
  PENDING = 2
  CONFIRMED = 3
  COMPLETED = 4
  CANCELED = 5

class PaymentStatus(enum.Enum):
  UNPAID = 1
  PENDING = 2
  COMPLETED = 3
  CANCELED = 4
  REFUNDED = 5

class VanType(enum.Enum):
  PASSENGER = 1
  CARGO = 2

class CarType(enum.Enum):
  ECONOMY = 1
  COMPACT = 2
  INTERMEDIATE = 3
  STANDARD = 4
  FULL_SIZE = 5
  PREMIUM = 6
  LUXURY = 7

class MotorcycleType(enum.Enum):
  STANDARD = 1
  CRUISER = 2
  TOURING = 3
  SPORTS = 4
  OFF_ROAD = 5
  DUAL_PURPOSE = 6

class TruckType(enum.Enum)
  LIGHT_DUTY = 1
  MEDIUM_DUTY = 2
  HEAVY_DUTY = 3

class VehicleLogType(enum.Enum):
  ACCIDENT = 1
  FUELING = 2
  CLEANING_SERVICE = 3
  OIL_CHANGE = 4
  REPAIR = 5
  OTHER = 6
```

```c++
// definition of enumerations used in the car rental system
enum VehicleStatus {
  AVAILABLE,
  RESERVED, 
  LOST, 
  BEING_SERVICED
};

enum AccountStatus {
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  BLOCKED
};

enum ReservationStatus {
  ACTIVE, 
  PENDING, 
  CONFIRMED, 
  COMPLETED, 
  CANCELED
};

enum PaymentStatus {
  UNPAID, 
  PENDING, 
  COMPLETED,  
  CANCELED,  
  REFUNDED
};

enum VanType {
  PASSENGER, 
  CARGO
};

enum CarType {
  ECONOMY, 
  COMPACT, 
  INTERMEDIATE, 
  STANDARD, 
  FULL_SIZE, 
  PREMIUM, 
  LUXURY
};

enum MotorcycleType {
  STANDARD,
  CRUISER,
  TOURING,
  SPORTS,
  OFF_ROAD,
  DUAL_PURPOSE
};

enum TruckType {
  LIGHT_DUTY,
  MEDIUM_DUTY,
  HEAVY_DUTY
};

enum VehicleLogType {
  ACCIDENT, 
  FUELING, 
  CLEANING_SERVICE, 
  OIL_CHANGE, 
  REPAIR, 
  OTHER
};
```

```javascript
// definition of enumerations used in the car rental system
const VehicleStatus = Object.freeze({
  AVAILABLE,
  RESERVED, 
  LOST, 
  BEING_SERVICED
});

const AccountStatus = Object.freeze({
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  BLOCKED
});

const ReservationStatus = Object.freeze({
  ACTIVE, 
  PENDING, 
  CONFIRMED, 
  COMPLETED, 
  CANCELED
});

const PaymentStatus = Object.freeze({
  UNPAID, 
  PENDING, 
  COMPLETED,  
  CANCELED,  
  REFUNDED
});

const VanType = Object.freeze({
  PASSENGER, 
  CARGO
});

const CarType = Object.freeze({
  ECONOMY, 
  COMPACT, 
  INTERMEDIATE, 
  STANDARD, 
  FULL_SIZE, 
  PREMIUM, 
  LUXURY
});

const MotorcycleType = Object.freeze({
  STANDARD,
  CRUISER,
  TOURING,
  SPORTS,
  OFF_ROAD,
  DUAL_PURPOSE
});

const TruckType = Object.freeze({
  LIGHT_DUTY,
  MEDIUM_DUTY,
  HEAVY_DUTY
});

const VehicleLogType = Object.freeze({
  ACCIDENT, 
  FUELING, 
  CLEANING_SERVICE, 
  OIL_CHANGE, 
  REPAIR, 
  OTHER
});
```

### Address, person, and driver
This section contains the Address, Person, and Driver classes, where the first two classes are used as a custom data type. The implementation of these classes is shown below:se classes can be found below:

```java
public class Address {
  private String streetAddress;
  private String city;
  private String state;
  private int zipCode;
  private String country;
}

public class Person {
  private String name;
  private Address address;
  private String email;
  private String phoneNumber;
}

public class Driver extends Person {
    private int driverId;
}

```

```c#
class Address {
  private string streetAddress;
  private string city;
  private string state;
  private int zipCode;
  private string country;
}

class Person {
  private string name;
  private Address address;
  private string email;
  private string phoneNumber;
}

class Driver : Person {
    private int driverId;
}
```


```python
class Address:
  def __init__(self, street_address, city, state, zip_code, country):
    self.__street_address = street
    self.__city = city
    self.__state = state
    self.__zip_code = zip_code
    self.__country = country

class Person:
  def __init__(self, name, address, email, phone_number):
    self.__name = name
    self.__address = address
    self.__email = email
    self.__phone_number = phone_number

class Driver(Person):
  def __init__(self, name, address, email, phone_number, driver_id):
    super().__init__(name, address, email, phone_number)
    self.__driver_id = driver_id
```

```c++
class Address {
    private: 
        string streetAddress;
        string city;
        string state;
        int zipCode;
        string country;
};

class Person {
    private: 
        string name;
        Address address;
        string email;
        string phoneNumber;
};

class Driver : public Person {
    private:
        int driverId;
};
```

```javascript
class Address {
    #streetAddress;
    #city;
    #state;
    #zipCode;
    #country;
    constructor(streetAddress, city, state, zipCode, country) {
        this.#streetAddress = streetAddress;
        this.#city = city;
        this.#state = state;
        this.#zipCode = zipCode;
        this.#country = country;
    }
}

class Person {
    #name;
    #address;
    #email;
    #phoneNumber;
    constructor(name, address, email, phoneNumber) {
        this.#name = name;
        this.#address = address;
        this.#email = email;
        this.phoneNumber = phoneNumber;
    }
}

class Driver extends Person {
    #driverId;
    constructor(name, address, phone, email, driverID) {
        this.#driverId = driverId;
        super(name, address, phone, email);
    }
}
```

### Account
Account is an abstract class that represents the various people or actors that can interact with the system. There are two types of accounts: receptionist and customer. The implementation of Account and its subclasses is shown below:

```java
public abstract class Account extends Person {
    private String accountId;
    private String password;
    private AccountStatus status;

    public abstract boolean resetPassword();
}

public class Receptionist extends Account {
    private Date dateJoined;

    public List<Customer> searchCustomer(String name);
    public boolean addReservation();
    public boolean cancelReservation();
    public boolean resetPassword() {
        // definition
    }
}

public class Customer extends Account {
    private String licenseNumber;
    private Date licenseExpiry;

    public boolean addReservation();
    public boolean cancelReservation();
    public List<VehicleReservation> getReservations();
    public boolean resetPassword() {
        // definition
    }
}
```

```c#
public abstract class Account : Person {
    private string accountId;
    private string password;
    private AccountStatus status;

    public abstract bool ResetPassword();
}

class Receptionist : Account {
    private DateTime dateJoined;

    public List<Customer> SearchCustomer(String name);
    public bool AddReservation();
    public bool CancelReservation();
    public override bool ResetPassword() {
        // definition
    }
}

class Customer : Account {
    private string licenseNumber;
    private DateTime licenseExpiry;

    public bool AddReservation();
    public bool CancelReservation();
    public List<VehicleReservation> GetReservations();
    public override bool ResetPassword() {
        // definition
    }
}
```

```python
from abc import ABC, abstractmethod

class Account(ABC):
  def __init__(self, name, address, email, phone_number, account_id, password, person):
    super().__init__(name, address, email, phone_number)
    self.__id = account_id
    self.__password = password
    self.__status = AccountStatus.NONE

  @abstractmethod
  def reset_password(self):
    None

class Receptionist(Account):
  def __init__(self, name, address, email, phone_number, account_id, password, person, date_joined):
    super().__init__(name, address, email, phoneNumber, accountId, password, person, status)
    self.__date_joined = date_joined


  def search_customer(self, name):
    None

  def add_reservation(self):
    None

  def cancel_reservation(self):
    None

  def reset_password(self):
    # functionality
  

class Customer(Account):
  def __init__(self, name, address, email, phone_number, account_id, password, person, license_number, lisense_expiry):
    super().__init__(name, address, email, phone_number, account_id, password, person, status)
    self.__license_number = license_number
    self.__lisense_expiry = lisense_expiry

  def add_reservation(self):
    None
    
  def cancel_reservation(self):
    None
    
  def get_reservations(self):
    None

  def reset_password(self):
    # functionality
```

```c++
class Account : public Person {
    private: 
        string accountId;
        string password;
        AccountStatus status;
    public:
        virtual bool resetPassword() =0;
};

class Receptionist : public Account {
    private:
        time_t dateJoined;
    public: 
        vector<Customer> searchCustomer(String name);
        bool addReservation();
        bool cancelReservation();
        bool resetPassword() {
            // definition
        }
};

class Customer : public Account {
    private: 
        String licenseNumber;
        time_t licenseExpiry;
    public: 
        bool addReservation();
        bool cancelReservation();
        vector<VehicleReservation> getReservations();
        bool resetPassword() {
            // definition
        }
};
```

```javascript
class Account extends Person {
    #accountId;
    #password;
    #status;
    constructor(name, address, phone, email, accountId, password, status) {
        if (this.constructor == Account) {
          throw new Error("Abstract classes can't be instantiated.");
        }
        else{
            this.#accountId = accountId;
            this.#password = password;
            this.#status = status;
            super(name, address, phone, email);
        }
    }
    resetPassword();
}

class Receptionist extends Account {
    #dateJoined;
    constructor(name, address, phone, email, accountId, password, status, dateJoined) {
        this.#dateJoined = dateJoined;
        super(name, address, phone, email, accountId, password, status);
    }
    searchCustomer(name);
    addReservation();
    cancelReservation();
    resetPassword() {
        // definition
    }
}

class Customer extends Account {
    #licenseNumber;
    #licenseExpiry;
    constructor(name, address, phone, email, accountId, password, status, licenseNumber,licenseExpiry) {
        this.#licenseNumber = licenseNumber;
        this.#licenseExpiry = licenseExpiry;
        super(name, address, phone, email, accountId, password, status);
    }
    addReservation();
    cancelReservation();
    getReservations();
    resetPassword() {
        // definition
    }
}
```

### Vehicle
Vehicle will be another abstract class, which serves as a parent for four different types of vehicles: Car, Van, Truck, and MotorCycle. The definition of the Vehicle and its child classes is given below:

```java
// Vehicle is an abstract class
public abstract class Vehicle {
  private String vehicleId;
  private String licenseNumber;
  private int passengerCapacity;
  private boolean hasSunroof;
  private VehicleStatus status;
  private String model;
  private int manufacturingYear;
  private int mileage;
  private List<VehicleLog> log;
  
  public boolean reserveVehicle();
  public boolean returnVehicle();
}

public class Car extends Vehicle {
  private CarType carType;
}

public class Van extends Vehicle {
  private VanType vanType;
}

public class Truck extends Vehicle {
  private TruckType truckType;
}

public class Motorcycle extends Vehicle {
  private MotorcycleType motorcycleType;
}
```

```c#
// Vehicle is an abstract class
public abstract class Vehicle {
    private string vehicleId;
    private string licenseNumber;
    private int passengerCapacity;
    private bool hasSunroof;
    private VehicleStatus status;
    private string model;
    private int manufacturingYear;
    private int mileage;
    private List<VehicleLog> log;
    
    public bool ReserveVehicle();
    public bool ReturnVehicle();
}

class Car : Vehicle {
    private CarType carType;
}

class Van : Vehicle {
    private VanType vanType;
}

class Truck : Vehicle {
    private TruckType truckType;
}

class MotorCycle : Vehicle {
    private MotorcycleType motorcycleType;
}
```

```python
# Vehicle is an abstract class
from abc import ABC, abstractmethod

class Vehicle(ABC):
  def __init__(self, vehicle_id, license_number, passenger_capacity, has_sunroof, status, model, manufacturing_year, mileage):
    self.__vehicle_id = vehicle_id
    self.__license_number = license_number
    self.__passenger_capacity = passenger_capacity
    self.__has_sunroof = has_sunroof
    self.__status = status
    self.__model = model
    self.__manufacturing_year = manufacturing_year
    self.__mileage = mileage
    self.__log = []

  def reserve_vehicle(self):
    None

  def return_vehicle(self):
    None


class Car(Vehicle):
  def __init__(self, vehicle_id, license_number, passenger_capacity, has_sunroof, status, model, manufacturing_year, mileage, car_type):
    super().__init__(vehicle_id, license_number, passenger_capacity, has_sunroof, status, model, manufacturing_year, mileage)
    self.__type = type


class Van(Vehicle):
  def __init__(self, vehicle_id, license_number, passenger_capacity, has_sunroof, status, model, manufacturing_year, mileage, van_type):
    super().__init__(vehicle_id, license_number, passenger_capacity, has_sunroof, status, model, manufacturing_year, mileage)
    self.__type = type


class Truck(Vehicle):
  def __init__(self, vehicle_id, license_number, passenger_capacity, has_sunroof, status, model, manufacturing_year, mileage, truck_type):
    super().__init__(vehicle_id, license_number, passenger_capacity, has_sunroof, status, model, manufacturing_year, mileage)
    self.__type = type

class Motorcycle(Vehicle):
  def __init__(self, vehicle_id, license_number, passenger_capacity, has_sunroof, status, model, manufacturing_year, mileage, motorcycle_type):
    super().__init__(vehicle_id, license_number, passenger_capacity, has_sunroof, status, model, manufacturing_year, mileage)
    self.__type = type
```

```c++
// Vehicle is an abstract class
class Vehicle {
    private:
        string vehicleId;
        string licenseNumber;
        int passengerCapacity;
        bool hasSunroof;
        VehicleStatus status;
        string model;
        int manufacturingYear;
        int mileage;
        vector<VehicleLog> log;

    public:
        bool reserveVehicle();
        bool returnVehicle();
};

class Car : public Vehicle {
    private:
        CarType carType;
};

class Van : public Vehicle {
   private:
        VanType vanType;
}

class Truck : public Vehicle {
    private:
        TruckType truckType;
};

class MotorCycle : public Vehicle {
    private:
        MotorcycleType motorcycleType;
};
```

```javascript
// Vehicle is an abstract class
class Vehicle {
  #vehicleId;
  #licenseNumber;
  #passengerCapacity;
  #hasSunroof;
  #status;
  #model;
  #manufacturingYear;
  #mileage;
  #log;

  constructor(vehicleId, licenseNumber, passengerCapacity, hasSunroof, status, model, manufacturingYear, mileage) {
    if (this.constructor == Vehicle) {
      throw new Error("Abstract classes can't be instantiated.");
    }
    else {
      this.#vehicleId = vehicleId;
      this.#licenseNumber = licenseNumber;
      this.#passengerCapacity = passengerCapacity;
      this.#hasSunroof = hasSunroof;
      this.#status = status;
      this.#model = model;
      this.#manufacturingYear = manufacturingYear;
      this.#mileage = mileage;
      this.#log = new Array();
    }
  }
  reserveVehicle();
  returnVehicle();
}

class Car extends Vehicle {
  #carType;
  constructor(carType) {
      this.#carType = type;
  }
}

class Van extends Vehicle {
  #vanType;
  constructor(vanType) {
      this.#vanType = vanType;
  }
}

class Truck extends Vehicle {
  #truckType;
  constructor(truckType) {
      this.#truckType = truckType;
  }
}

class MotorCycle extends Vehicle {
  #motorcycleType;
  constructor(motorcycleType) {
      this.#motorcycleType = motorcycleType;
  }
}
```

### Equipment
Equipment is an abstract class, and this section represents different equipment: Navigation, ChildSeat, and SkiRack added in the reservation. The code to implement these classes is shown below:

```java
// Equipment is an abstract class
public abstract class Equipment {
    private int equipmentId;
    private int price;
}

public class Navigation extends Equipment {
}

public class ChildSeat extends Equipment {
}

public class SkiRack extends Equipment {
}
```

```c#
// Equipment is an abstract class
public abstract class Equipment {
    private int equipmentId;
    private int price;
}

class Navigation : Equipment {
}

class ChildSeat : Equipment {
}

class SkiRack : Equipment {
}
```

```python
# Equipment is an abstract class
from abc import ABC, abstractmethod

class Equipment(ABC):
  def __init__(self, equipment_id, price):
    self.__equipment_id = equipment_id
    self.__price = price

class Navigation(Equipment):
  def __init__(self, equipment_id, price):
    super().__init__(equipment_d, price)

class ChildSeat(Equipment):
  def __init__(self, equipment_id, price):
    super().__init__(equipmentId, price)

class SkiRack(Equipment):
  def __init__(self, equipment_id, price):
    super().__init__(equipment_id, price)
```

```c++
// Equipment is an abstract class
class Equipment {
    private:
        int equipmentId;
        int price;
};

class Navigation : public Equipment {
    
};

class ChildSeat : public Equipment {
   
};

class SkiRack : public Equipment {
    
};
```

```javascript
// Equipment is an abstract class
class Equipment {
  #equipmentId;
  #price;

  constructor(equipmentId, price) {
    if (this.constructor == Equipment) {
      throw new Error("Abstract classes can't be instantiated.");
    }
    else {
      this.#equipmentId = equipmentId;
      this.#price = price;
    }
  }
}

class Navigation extends Equipment {
  constructor(equipmentId, price) {
    super(equipmentId, price);
  }
}

class ChildSeat extends Equipment {
  constructor(equipmentId, price) {
    super(equipmentId, price);
  }
}

class SkiRack extends Equipment {
  constructor(equipmentId, price) {
    super(equipmentId, price);
  }
}
```

### Service
Service is an abstract class, and this section represents different services: DriverService, RoadsideAssistance, and Wi-Fi added to the reservation. The code to implement these classes is shown below:

```java
// Service is an abstract class
public abstract class Service {
    private int serviceId;
    private int price;
}

public class DriverService extends Service {
    private int driverId;
}

public class RoadsideAssistance extends Service {
}

public class WiFi extends Service {
}
```

```c#
// Service is an abstract class
public abstract class Service {
    private int serviceId;
    private int price;
}

class DriverService : Service {
    private int driverId;
}

class RoadsideAssistance : Service {
}

class WiFi : Service {
}
```

```python
# Service is an abstract class
from abc import ABC, abstractmethod

class Service(ABC):
  def __init__(self, service_id, price):
    self.__service_id = service_id
    self.__price = price

class DriverService(Service):
    def __init__(self, service_id, price, driver_id):
        super().__init__(service_id, price)
        self.__driver_id = driver_id

class RoadsideAssistance(Service):
    def __init__(self, service_id, price):
        super().__init__(service_id, price)

class WiFi(Service):
    def __init__(self, service_id, price):
        super().__init__(service_id, price)
```

```c++
// Service is an abstract class
class Service {
    private:
        int serviceId;
        int price;
};

class DriverService : public Service {
    private:
        int driverId;
};

class RoadsideAssistance : public Service {
};

class WiFi : public Service {
};
```

```javascript
// Service is an abstract class
class Service {
  #serviceId;
  #price;

  constructor(serviceId, price) {
    if (this.constructor == Service) {
      throw new Error("Abstract classes can't be instantiated.");
    }
    else {
      this.#serviceId = serviceId;
      this.#price = price;
    }
  }
}

class DriverService extends Service {
  #driverId;
  constructor(serviceId, price, driverId) {
    this.#driverId = driverId;
    super(serviceId, price);
  }
}

class RoadsideAssistance extends Service {
  constructor(serviceId, price) {
    super(serviceId, price);
  }
}

class WiFi extends Service {
  constructor(serviceId, price) {
    super(serviceId, price);
  }
}
```

### Payment
The Payment class is another abstract class, with the Cash and CreditCard classes as its child. This takes in the PaymentStatus enum to keep track of the payment status. The definition of this class is provided below:

```java
// Payment is an abstract class
public abstract class Payment {
  // Data members
  private double amount;

  // The Date datatype represents and deals with both date and time.
  private Date timestamp;
  private PaymentStatus status;

  public abstract boolean makePayment();
}

public class Cash extends Payment {
    public boolean makePayment() {
        // functionality
    }
}

public class CreditCard extends Payment {
    // Data members
    private String nameOnCard;
    private String cardNumber;
    private String billingAddress;
    private int code;

    public boolean makePayment() {
        // functionality
    }
}
```

```c#
// Payment is an abstract class
public abstract class Payment {
  // Data members
  private double amount;
  
  // The DateTime datatype represents and deals with both date and time.
  private DateTime timestamp;
  private PaymentStatus status;
  
  public abstract bool MakePayment();
}

class Cash : Payment {
    public override bool MakePayment() {
        // functionality
    }
}

class CreditCard : Payment {
    // Data members
    private string nameOnCard;
    private string cardNumber;
    private string billingAddress;
    private int code;
    
    public override bool MakePayment() {
        // functionality
    }
}
```

```python
# Payment is an abstract class
from abc import ABC, abstractmethod

class Payment(ABC):
  # Data members
  def __init__(self, amount, timestamp, status):
    self.__amount = amount
    self.__timestamp = timestamp
    self.__status = status # Refers to the PaymentStatus enum

  @abstractmethod
  def make_payment(self):
    pass

class Cash(Payment):
  def __init__(self, amount, timestamp, status):
    super().__init__(amount, timestamp, status)

  def make_payment(self):
    # functionality
    pass

class CreditCard(Payment):
  # Data members
  def __init__(self, amount, timestamp, status, name_on_card, card_number, billing_address, code):
    self.__name_on_card = name_on_card
    self.__card_number = card_number
    self.__billing_address = billing_address
    self.__code = code
    super().__init__(amount, timestamp, status)

  def make_payment(self):
    # functionality
    pass
```

```c++
// Payment is an abstract class
class Payment {
  // Data members
  private:
    double amount;
    // The time_t datatype represents and deals with both date and time.
    time_t timestamp;
    PaymentStatus status;

  public virtual bool makePayment() = 0;
}

class Cash : public Payment {
  public bool makePayment() {
      // functionality
  }
}

class CreditCard : public Payment {
  // Data members
  private:  
    string nameOnCard;
    string cardNumber;
    string billingAddress;
    int code;

  public bool makePayment() {
      // functionality
  }
}
```

```javascript
// Payment is an abstract class
class Payment {
    #amount;
    #timestamp;
    #status;

    // Data members
    constructor(amount, timestamp, status) {
        if (this.constructor === Payment) {
            throw new Error("Abstract classes can't be instantiated.");
        }
        else {
            this.#amount = amount;
            this.#timestamp = timestamp;
            this.#status = status; // Refers to the PaymentStatus enum
        }
    }

    makePayment() { }
}
class Cash extends Payment{
    makePayment(){
        // functionality
    }
}
class CreditCard extends Payment{
    #nameOnCard;
    #cardNumber;
    #billingAddress;
    #code;

    // Data members
    constructor(amount, timestamp, status, nameOnCard, cardNumber, billingAddress, code) {
        this.#nameOnCard = nameOnCard;
        this.#cardNumber = cardNumber;
        this.#billingAddress = billingAddress;
        this.#code = code;
        super(amount, timestamp, status)
    }

    makePayment(){
        // functionality
    }
}
```

### Vehicle log and Vehicle reservation
VehicleLog is a class responsible for keeping track of all the events related to a vehicle. VehicleReservation is a class responsible for managing the reservation of vehicles. The implementation of this class is given below:

```java
public class VehicleLog {
  private int logId;
  private VehicleLogType logType;
  private String description;
  private Date creationDate;
}

public class VehicleReservation {
  private int reservationId;
  private String customerId;
  private String vehicleId;
  private Date creationDate;
  private ReservationStatus status;
  private Date dueDate;
  private Date returnDate;
  private String pickupLocation;
  private String returnLocation;
  
  private List<Equipment> equipments;
  private List<Service> services;

  public static VehicleReservation getReservationDetails();
  public boolean addEquipment();
  public boolean addService();
}
```

```c#
class VehicleLog {
  private int logId;
  private VehicleLogType logType;
  private string description;
  private DateTime creationDate;
}

class VehicleReservation {
  private int reservationId;
  private string customerId;
  private string vehicleId;
  private DateTime creationDate;
  private ReservationStatus status;
  private DateTime dueDate;
  private DateTime returnDate;
  private string pickupLocation;
  private string returnLocation;

  private List<Equipment> equipments;
  private List<Service> services;

  public static VehicleReservation GetReservationDetails();
  public bool AddEquipment();
  public bool AddService();
}
```

```python
class VehicleLog:
  def __init__(self, log_id, log_type, description, creation_date):
    self.__log_id = log_id
    self.__log_type = log_type
    self.__description = description
    self.__creation_date = creation_date


class VehicleReservation:
  def __init__(self, reservation_id, customer_id, vehicle_id, due_date, return_date, pickup_location, return_location):
    self.__reservation_id = reservation_id
    self.__customer_id = customer_id
    self.__vehicle_id = vehicle_id
    self.__creation_date = datetime.date.today()
    self.__status = ReservationStatus.ACTIVE
    self.__due_date = due_date
    self.__return_date = return_date
    self.__pickup_location = pickup_location
    self.__return_location = return_location

    self.__equipments = []
    self.__services = []

  def add_equipment(self):
    None

  def add_service(self):
    None
```

```c++
class VehicleLog {
    private:
        int logId;
        VehicleLogType type;
        string description;
        time_t creationDate;
};

class VehicleReservation {
    private:
        int reservationId;
        string customerId;
        string vehicleId;
        time_t creationDate;
        ReservationStatus status;
        time_t dueDate;
        time_t returnDate;
        string pickupLocation;
        string returnLocation;

        vector<Equipment> equipments;
        vector<Service> services;

    public: 
        static VehicleReservation getReservationDetails();
        bool addEquipment();
        bool addService();
};
```

```javascript
class VehicleLog {
    #logId; 
    #type;
    #description;
    #creationDate;
    constructor(logId, type, description, creationDate){
        this.#logId = logId;
        this.#type = type;
        this.#description = description;
        this.#creationDate = creationDate;
    }
}

class VehicleReservation {
    #reservationId;
    #customerId;
    #vehicleId;
    #creationDate;
    #status;
    #dueDate;
    #returnDate;
    #pickupLocation;
    #returnLocation;
    #equipments;
    #services;
    constructor(reservationId, customerId, vehicleId, creationDate, dueDate, returnDate, pickupLocation, returnLocation){
        this.#reservationId = reservationId;
        this.#customerId = customerId;
        this.#vehicleId = vehicleId;
        this.#creationDate = creationDate;
        this.#status = ReservationStatus.ACTIVE;
        this.#dueDate = dueDate;
        this.#returnDate = returnDate;
        this.#pickupLocationName = pickupLocation;
        this.#returnLocationName = returnLocation;
        
        this.#equipments = [];
        this.#services = [];
    }
    getReservationDetails();
    addEquipment();
    addService();
}
```

### Notification
The Notification class is another abstract class responsible for sending notifications, with the SMSNotification and EmailNotification classes as its child. The implementation of this class is shown below:

```java
// Notification is an abstract class
public abstract class Notification {
    private int notificationId;
    // The Date data type represents and deals with both date and time.
    private Date createdOn;      
    private String content;

    public abstract void sendNotification(Account account);
}

class SmsNotification extends Notification {

    public void sendNotification(Account account) {
        // functionality 
    }
}

class EmailNotification extends Notification {

    public void sendNotification(Account account) {
        // functionality 
    }
}
```

```c#
// Notification is an abstract class
public abstract class Notification {
    private int notificationId;
    private DateTime createdOn;
    private string content;

    public abstract void SendNotification(Account account);
}

class SmsNotification : Notification {

    public override void SendNotification(Account account) {
        // functionality 
    }
}

class EmailNotification : Notification {

    public override void SendNotification(Account account) {
        // functionality 
    }
}
```

```python
# Notification is an abstract class
from abc import ABC, abstractmethod
class Notification(ABC):
    def __init__(self, notification_id, created_on, content):
        self.__notification_id = notification_id
        self.__created_on = created_on
        self.__content = content

    # account here refers to an instance of the Account class 
    @abstractmethod
    def send_notification(account):
        pass

class SmsNotification(Notification):
    def __init__(self, notification_id, created_on, content):
        super().__init__(notification_id, created_on, content)

    # account here refers to an instance of the Account class 
    def send_notification(account):
        # functionality 
        pass

class EmailNotification(Notification):
    def __init__(self, notification_id, created_on, content):
        super().__init__(notification_id, created_on, content)

    # account here refers to an instance of the Account class 
    def send_notification(account):
        # functionality 
        pass
```

```c++
// Notification is an abstract class
class Notification {
    private: 
        int notificationId;
        // The time_t datatype represents and deals with both date and time.
        time_t createdOn;
        string content;

    public: 
        void sendNotification(Account account) = 0;
};

class SmsNotification : public Notification {
    public: 
        void sendNotification(Account account) {
            // functionality 
        }
};

class EmailNotification : public Notification {
    public: 
        void sendNotification(Account account) {
            // functionality 
        }
};
```

```javascript
// Notification is an abstract class
class Notification {
    #notificationId;
    #createdOn;
    #content;
    constructor(notificationId, createdOn, content) {
        if (this.constructor == Notification) {
          throw new Error("Abstract classes can't be instantiated.");
        }
        else {
            this.#notificationId = notificationId;
            this.#createdOn = createdOn;
            this.#content = content;
        }
    }
    // account here refers to an instance of the Account class 
    sendNotification(account) {};
}

class SmsNotification extends Notification {
    constructor(){
        super(notificationId, createdOn, content);
    }

    // account here refers to an instance of the Account class 
    sendNotification(account) {
        // functionality 
    }
}

class EmailNotification extends Notification {
    constructor() {
        super(notificationId, createdOn, content);
    }

    // account here refers to an instance of the Account class 
    sendNotification(account) {
        // functionality 
    }
}
```



### Parking stall and fine
### Search interface and vehicle catalog
### Car rental system and car rental branch
## Wrapping up
