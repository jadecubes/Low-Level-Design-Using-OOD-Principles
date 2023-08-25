# Code for the Airline Management System
We’ve reviewed different aspects of the airline management system and observed the attributes attached to the problem using various UML diagrams. Let’s explore the more practical side of things, where we will work on implementing the airline management system using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the airline management system:

- Java

- C#

- Python

- C++

- JavaScript

## The airline management system classes
In this section, we’ll provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public methods function.
```

### Constants
The following code provides the definition of the various enums and custom data types being used in the airline management system:
```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```

```java
public class Address {
  private int zipCode;
  private String streetAddress;
  private String city;
  private String state;
  private String country;
}

enum AccountStatus {
  ACTIVE,
  DISABLED,
  CLOSED,
  BLOCKED
}

enum SeatStatus {
  AVAILABLE,
  BOOKED,
  CHANCE
}

enum SeatType {
  REGULAR,
  ACCESSIBLE,
  EMERGENCY_EXIT,
  EXTRA_LEG_ROOM
}

enum SeatClass {
  ECONOMY,
  ECONOMY_PLUS,
  BUSINESS,
  FIRST_CLASS
}

enum FlightStatus {
  ACTIVE,
  SCHEDULED,
  DELAYED,
  LANDED,
  DEPARTED,
  CANCELED,
  DIVERTED,
  UNKNOWN
}

enum ReservationStatus {
  REQUESTED,
  PENDING,
  CONFIRMED,
  CHECKED_IN,
  CANCELED
}

enum PaymentStatus {
  PENDING,
  COMPLETED,
  FAILED,
  DECLINED,
  CANCELED,
  REFUNDED
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

enum AccountStatus {
  ACTIVE,
  DISABLED,
  CLOSED,
  BLOCKED
}

enum SeatStatus {
  AVAILABLE,
  BOOKED,
  CHANCE
}

enum SeatType {
  REGULAR,
  ACCESSIBLE,
  EMERGENCY_EXIT,
  EXTRA_LEG_ROOM
}

enum SeatClass {
  ECONOMY,
  ECONOMY_PLUS,
  BUSINESS,
  FIRST_CLASS
}

enum FlightStatus {
  ACTIVE,
  SCHEDULED,
  DELAYED,
  LANDED,
  DEPARTED,
  CANCELED,
  DIVERTED,
  UNKNOWN
}

enum ReservationStatus {
  REQUESTED,
  PENDING,
  CONFIRMED,
  CHECKED_IN,
  CANCELED
}

enum PaymentStatus {
  PENDING,
  COMPLETED,
  FAILED,
  DECLINED,
  CANCELED,
  REFUNDED
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

class AccountStatus(enum.Enum):
  ACTIVE = 1 
  DISABLES = 2
  CLOSED = 3
  BLOCKED = 4

class SeatStatus(enum.Enum):
  AVAILABLE = 1 
  BOOKED = 2
  CHANCE = 3

class SeatType(enum.Enum):
  REGULAR = 1 
  ACCESSIBLE = 2
  EMERGENCY_EXIT = 3
  EXTRA_LEG_ROOM = 4

class SeatClass(enum.Enum):
  ECONOMY = 1 
  ECONOMY_PLUS = 2
  BUSINESS = 3
  FIRST_CLASS = 4

class FlightStatus(enum.Enum):
  ACTIVE = 1 
  SCHEDULED = 2
  DELAYED = 3
  LANDED = 4
  DEPARTED = 5
  CANCELED = 6
  DIVERTED = 7
  UNKNOWN = 8

class ReservationStatus(enum.Enum):
  REQUESTED = 1 
  PENDING = 2
  CONFIRMED = 3
  CHECKED_IN = 4
  CANCELED = 5

class PaymentStatus(enum.Enum):
  PENDING = 1 
  COMPLETED = 2
  FAILED = 3
  DECLINED = 4
  CANCELED = 5
  REFUNDED = 6

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

enum AccountStatus {
  ACTIVE,
  DISABLED,
  CLOSED,
  BLOCKED
};

enum SeatStatus {
  AVAILABLE,
  BOOKED,
  CHANCE
};

enum SeatType {
  REGULAR,
  ACCESSIBLE,
  EMERGENCY_EXIT,
  EXTRA_LEG_ROOM
}

enum SeatClass {
  ECONOMY,
  ECONOMY_PLUS,
  BUSINESS,
  FIRST_CLASS
};

enum FlightStatus {
  ACTIVE,
  SCHEDULED,
  DELAYED,
  LANDED,
  DEPARTED,
  CANCELED,
  DIVERTED,
  UNKNOWN
};

enum ReservationStatus {
  REQUESTED,
  PENDING,
  CONFIRMED,
  CHECKED_IN,
  CANCELED
};

enum PaymentStatus {
  PENDING,
  COMPLETED,
  FAILED,
  DECLINED,
  CANCELED,
  REFUNDED
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

const AccountStatus = Object.freeze({
  ACTIVE,
  DISABLED,
  CLOSED,
  BLOCKED
});

const SeatStatus = Object.freeze({
  AVAILABLE,
  BOOKED,
  CHANCE
});

const SeatType = Object.freeze({
  REGULAR,
  ACCESSIBLE,
  EMERGENCY_EXIT,
  EXTRA_LEG_ROOM
});

const SeatClass = Object.freeze({
  ECONOMY,
  ECONOMY_PLUS,
  BUSINESS,
  FIRST_CLASS
});

const FlightStatus = Object.freeze({
  ACTIVE,
  SCHEDULED,
  DELAYED,
  LANDED,
  DEPARTED,
  CANCELED,
  DIVERTED,
  UNKNOWN
});

const ReservationStatus = Object.freeze({
  REQUESTED,
  PENDING,
  CONFIRMED,
  CHECKED_IN,
  CANCELED
});

const PaymentStatus = Object.freeze({
  PENDING,
  COMPLETED,
  FAILED,
  DECLINED,
  CANCELED,
  REFUNDED
});
```
### Account and passenger
The Account class refers to an account for any user including admin, crew, front desk officer, and a customer. The Passenger class represents the passengers in the airline system. The definition of this class is given below:

```java
public class Account {
  private AccountStatus status;
  private int accountId;
  private String username;  
  private String password;

  public boolean resetPassword();
}

public class Passenger {
  private int passengerId;
  private String name;
  private String gender;
  private Date dateOfBirth;  
  private String passportNumber;
}

```

```c#
class Account {
  private AccountStatus status;
  private int accountId;
  private string username;  
  private string password;

  public bool ResetPassword();
}

class Passenger {
  private int passengerId;
  private string name;
  private string gender;
  private DateTime dateOfBirth;  
  private string passportNumber;
}

```

```python
class Account:
  def __init__(self, status, account_id, username, password):
    self.__status = status # Refers to the AccountStatus enum
    self.__account_id = account_id
    self.__username = username
    self.__password = password

  def reset_password(self):
    pass 

class Passenger:
  def __init__(self, passenger_id, name, date_of_birth, gender, passport_number):
    self.__passenger_id = passenger_id 
    self.__name = name
    self.__date_of_birth = date_of_birth
    self.__gender = gender
    self.__passport_number = passport_number
```

```c++
class Account {
  private: 
    AccountStatus status;
    int accountId;
    string username;
    string password

  public:
    bool resetPassword();
};

class Passenger {
  private: 
    int passengerId;
    string name;
    time_t dateOfBirth;
    string gender;
    string passportNumber;
};

```

```javascript
class Account {
  #status;
  #accountId;
  #username;
  #password;

  constructor(status, accountId, username, password) {
    this.#status = status; // Refers to the AccountStatus enum
    this.#accountId = accountId;
    this.#username = username;
    this.#password = password;
  }

  resetPassword();
}

class Passenger {
  #passengerId;
  #name;
  #dateOfBirth;
  #gender;
  #passportNumber;

  constructor(passengerId, name, dateOfBirth, gender, passportNumber) {
    this.#passengerId = passengerId;  
    this.#name = name;
    this.#dateOfBirth = dateOfBirth;
    this.#gender = gender;
    this.#passportNumber = passportNumber;
  }
}

```
### Person
Person is an abstract class that represents the various people or actors that can interact with the system. There are four types of persons: Admin, Crew, FrontDeskOfficer, and Customer. The implementation of the mentioned classes is shown below:

```java
public abstract class Person {
  private String name;
  private Address address;
  private String email;
  private String phone;
  private Account account;
}

public class Admin extends Person {
  public boolean addAircraft(Aircraft aircraft);
  public boolean addFlight(Flight flight);
  public boolean cancelFlight(Flight flight);
  public boolean assignCrew(Flight flight);
  public boolean blockUser(User user);
  public boolean unblockUser(User user);
}

public class Crew extends Person {
  public List<FlightInstance> viewSchedule();
}

public class FrontDeskOfficer extends Person {
  public List<Itinerary> viewItinerary();
  public boolean createItinerary();
  public boolean createReservation();
  public boolean assignSeat();
  public boolean makePayment();
}

public class Customer extends Person {
  private int customerId;

  public List<Itinerary> viewItinerary();
  public boolean createItinerary();
  public boolean createReservation();
  public boolean assignSeat();
  public boolean makePayment();
}
```

```c#
public abstract class Person {
    private string name;
    private Address address;
    private string email;
    private string phone;
    private Account account;
}

class Admin : Person {
  public bool AddAircraft(Aircraft aircraft);
  public bool AddFlight(Flight flight);
  public bool CancelFlight(Flight flight);
  public bool AssignCrew(Flight flight);
  public bool BlockUser(User user);
  public bool UnblockUser(User user);
}

class Crew : Person {
  public List<FlightInstance> ViewSchedule();
}

class FrontDeskOfficer : Person {
  public List<Itinerary> ViewItinerary();
  public bool CreateItinerary();
  public bool CreateReservation();
  public bool AssignSeat();
  public bool MakePayment();
}

class Customer : Person {
  private int customerId;

  public List<Itinerary> ViewItinerary();
  public bool CreateItinerary();
  public bool CreateReservation();
  public bool AssignSeat();
  public bool MakePayment();
}
```

```python
from abc import ABC, abstractmethod
class Person(ABC):
  def __init__(self, name, address, email, phone, account):
    self.__name = name
    self.__address = address
    self.__email = email
    self.__phone = phone
    self.__account = account


class Admin(Person):
  def __init__(self, name, address, email, phone, account):
    super().__init__(name, address, email, phone, account)

  def add_aircraft(self, aircraft):
    None
  
  def add_flight(self, flight):
    None
  
  def cancel_flight(self, flight):
    None

  def assign_crew(self, flight):
    None

  def block_user(self, user):
    None

  def unblock_user(self, user):
    None

class Crew(Person):
  def __init__(self, name, address, email, phone, account):
    super().__init__(name, address, email, phone, account)
  
  def view_schedule(self):
    None

class FrontDeskOfficer(Person):
  def __init__(self, name, address, email, phone, account):
    super().__init__(name, address, email, phone, account)
  
  def view_itinerary():
    None

  def create_itinerary():
    None

  def create_reservation():
    None

  def assign_seat():
    None
  
  def make_payment():
    None

class Customer(Person):
  def __init__(self, name, address, email, phone, account, customer_id):
    self.__customer_id = customer_id
  
    super().__init__(name, address, email, phone, account)
  
  def view_itinerary():
    None

  def create_itinerary():
    None

  def create_reservation():
    None

  def assign_seat():
    None
  
  def make_payment():
    None

```

```c++
class Person {
  private: 
    string name;
    Address address;
    string email;
    string phone;
    Account account;
};

class Admin : public Person {
  public: 
    bool addAircraft(Aircraft aircraft);
    bool addFlight(Flight flight);
    bool cancelFlight(Flight flight);
    bool assignCrew(Flight flight);
    bool blockUser(User user);
    bool unblockUser(User user);
};

class Crew : public Person {
  public: 
    vector<FlightInstance> viewSchedule();
};

class FrontDeskOfficer : public Person {
  public: 
    vector<Itinerary> viewItinerary();
    bool createItinerary();
    bool createReservation();
    bool assignSeat();
    bool makePayment();
};

class FrontDeskOfficer : public Person {
  private:
    int customerId;
  public: 
    vector<Itinerary> viewItinerary();
    bool createItinerary();
    bool createReservation();
    bool assignSeat();
    bool makePayment();
};

```

```javascript
class Person {
    #name;
    #address;
    #email;
    #phone;
    #account;
    constructor(name, address, email, phone, account) {
        if (this.constructor == Person) {
          throw new Error("Abstract classes can't be instantiated.");
        }
        else{
            this.#name = name;
            this.#address = address;
            this.#email = email;
            this.#phone = phone;
            this.#account = account;
        }
    }
}

class Admin extends Person {
  constructor(name, address, email, phone, account){
    super(name, address, email, phone, account);
  }
  addAircraft(aircraft);
  addFlight(flight);
  cancelFlight(flight);
  assignCrew(flight);
  blockUser(user);
  unblockUser(user);
}

class Crew extends Person {
  constructor(name, address, email, phone, account){
    super(name, address, email, phone, account);
  }
  viewSchedule();
}

class FrontDeskOfficer extends Person {
  constructor(name, address, email, phone, account){
    super(name, address, email, phone, account);
  }
  viewItinerary();
  createItinerary();
  createReservation();
  assignSeat();
  makePayment();
}

class Customer extends Person {
  #customerId;
  
  constructor(customerId, name, address, email, phone, account){
    this.#customerId = customerId;
    super(name, address, email, phone, account);
  }
  viewItinerary();
  createItinerary();
  createReservation();
  assignSeat();
  makePayment();
}
```

### Seat and flight seat
The Seat and FlightSeat are used to keep track of the customer’s seat. Here, Seat is the physical seat in the aircraft and FlightSeat is the seat assigned to a specific flight instance. The definition of these two classes is given below:
```java
public class Seat {
  private String seatNumber;
  private SeatType type;
  private SeatClass _class;
}

public class FlightSeat extends Seat {
  private double fare;
  private SeatStatus status;
  private String reservationNumber;
}
```

```c#
class Seat {
  private string seatNumber;
  private SeatType type;
  private SeatClass _class;
}

class FlightSeat : Seat {
  private double fare;
  private SeatStatus status;
  private string reservationNumber;
}
```

```python
class Seat:
  def __init__(self, seat_number, type, _class):
    self.__seat_number = seat_number 
    self.__type = type
    self.___class = _class


class FlightSeat(Seat):
  def __init__(self, fare, status, email, seat_number, type, _class):
    self.__fare = fare
    self.__status = status
    self.__reservationNumber = reservationNumber
  
    super().__init__(seat_number, type, _class)

```

```c++
class Seat {
  private: 
    string seatNumber;
    SeatType type;
    SeatClass _class;
};

class FlightSeat : public Seat {
  private: 
    double fare;
    SeatStatus status;
    string reservationNumber;
};
```

```javascript
class Seat {
  #seatNumber;
  #type;
  #_class;
  constructor(seatNumber, type, _class) {
    this.#seatNumber = seatNumber; 
    this.#type = type;
    this.#_class = _class;
  }
}

class FlightSeat extends Seat {
  #fare;
  #status;
  #reservationNumber;
  constructor(fare, status, reservationNumber, seatNumber, type, _class){
    this.#fare = fare;
    this.#status = status;
    this.#reservationNumber = reservationNumber;
    super(seatNumber, type, _class);
  }
}
```


### Flight and flight instance
The Flight and FlightInstance classes provide the details of the flight and its instances to the customer. The definition of these classes is given below:

```java
public class Flight {
  private String flightNo;
  private int durationMin;
  private Airport departure;
  private Airport arrival;
  private List<FlightInstance> instances;
}

public class FlightInstance {
  private Flight flight;
  private Date departureTime;
  private String gate;
  private FlightStatus status;
  private Aircraft aircraft;
  private List<FlightSeat> seats;
}
```

```c#
class Flight {
  private string flightNo;
  private int durationMin;
  private Airport departure;
  private Airport arrival;
  private List<FlightInstance> instances;
}

class FlightInstance {
  private Flight flight;
  private DateTime departureTime;
  private string gate;
  private FlightStatus status;
  private Aircraft aircraft;
  private List<FlightSeat> seats;
}
```

```python
class Flight:
  def __init__(self, flight_no, duration_min, departure, arrival):
    self.__flight_no = flight_no 
    self.__duration_min = duration_min
    self.__departure = departure
    self.__password = arrival
    self.__instances = []


class FlightInstance:
  def __init__(self, flight, departureTime, gate, status, aircraft, seats):
    self.__flight = flight 
    self.__departureTime = departureTime
    self.__gate = gate
    self.__status = status
    self.__aircraft = aircraft
    self.__seats = seats

```

```c++
class Flight {
  private:
    string flightNo;
    int durationMin;
    Airport departure;
    Airport arrival;
    vector<FlightInstance> instances;
};

class FlightInstance {
  private: 
    Flight flight;
    time_t departureTime;
    string gate;
    FlightStatus status;
    Aircraft aircraft;
    vector<FlightSeat> seats;
};
```

```javascript
class Flight {
  #flightNo;
  #durationMin;
  #departure;
  #arrival;
  #instances;

  constructor(flightNo, durationMin, departure, arrival) {
    this.#flightNo = flightNo; 
    this.#durationMin = durationMin;
    this.#departure = departure;
    this.#arrival = arrival;
    this.#instances = new Array();
  }
}

class FlightInstance {
  #flight;
  #departureTime;
  #gate;
  #status;
  #aircraft;
  #seats;
  
  constructor(flight, departureTime, gate, status, aircraft, seats) {
    this.#flight = flight;  
    this.#departureTime = departureTime;
    this.#gate = gate;
    this.#status = status;
    this.#aircraft = aircraft;
    this.#seats = seats;
  }
}

```
### Itinerary and flight reservation
The Itinerary and FlightReservation classes are used to keep track of itineraries and flights reserved by the customers. Both classes are defined below:

```java
public class Itinerary {
  private Airport startingAirport;
  private Airport finalAirport;
  private Date creationDate;
  private List<FlightReservation> reservations;
  private List<Passenger> passengers;

  public boolean makeReservation();
  public boolean makePayment();
}

public class FlightReservation {
  private String reservationNumber;
  private FlightInstance flight;
  private HashMap<Passenger, FlightSeat> seatMap;
  private ReservationStatus status;
  private Date creationDate;

  public static FlightReservation fetchReservationDetails(String reservationNumber);
  public List<Passenger> getPassengers();
}

```

```c#
class Itinerary {
  private Airport startingAirport;
  private Airport finalAirport;
  private DateTime creationDate;
  private List<FlightReservation> reservations;
  private List<Passenger> passengers;

  public bool MakeReservation();
  public bool MakePayment();
}

class FlightReservation {
  private string reservationNumber;
  private FlightInstance flight;
  private Dictionary<Passenger, FlightSeat> seatMap;
  private ReservationStatus status;
  private DateTime creationDate;

  public static FlightReservation FetchReservationDetails(String reservationNumber);
  public List<Passenger> GetPassengers();
}
```

```python
class Itinerary:
  def __init__(self, starting_airport, final_airport, creation_date, reservations, passengers):
    self.__starting_airport = starting_airport
    self.__final_airport = final_airport
    self.__creation_date = creation_date
    self.__reservations = reservations
    self.__passengers = passengers

  def make_reservation(self):
    pass 

  def make_payment(self):
    pass 

public class FlightReservation {
  private String reservationNumber;
  private FlightInstance flight;
  private HashMap<Passenger, FlightSeat> seatMap;
  private ReservationStatus status;
  private Date creationDate;

  public static FlightReservation fetchReservationDetails(String reservationNumber);
  public List<Passenger> getPassengers();
}

class FlightReservation:
  def __init__(self, reservation_number, flight, seat_map, status, creation_date):
    self.__reservation_number = reservation_number 
    self.__flight = flight
    self.__seat_map = seat_map
    self.__status = status
    self.__creation_date = creation_date
```

```c++
class Itinerary {
  private: 
    Airport startingAirport;
    Airport finalAirport;
    time_t creationDate;
    vector<FlightReservation> reservations;
    vector<Passenger> passengers;

  public:
    bool makeReservation();
    bool makePayment();
};

class FlightReservation {
  private:
    string reservationNumber;
    FlightInstance flight;
    map<Passenger, FlightSeat> seatMap;
    ReservationStatus status;
    time_t creationDate;

  public: 
    static FlightReservation fetchReservationDetails(String reservationNumber);
    vector<Passenger> getPassengers();
};

```

```javascript
class Itinerary {
  #startingAirport;
  #finalAirport;
  #creationDate;
  #reservations;
  #passengers;
  constructor(startingAirport, finalAirport, creationDate, reservations, passengers) {
    this.#startingAirport = startingAirport; 
    this.#finalAirport = finalAirport;
    this.#creationDate = creationDate;
    this.#reservations = reservations;
    this.#passengers = passengers;
  }
  makeReservation();
  makePayment();
}

class FlightReservation {
  #reservationNumber;
  #flight;
  #seatMap;
  #status;
  #creationDate;
  constructor(reservationNumber, flight, seatMap, status, creationDate) {
    this.#reservationNumber = reservationNumber;  
    this.#flight = flight;
    this.#seatMap = seatMap;
    this.#status = status;
    this.#creationDate = creationDate;
  }
  fetchReservationDetails(reservationNumber);
  getPassengers();
}

```
### Payment
The Payment class is another abstract class with two child classes: Cash and CreditCard. This takes the PaymentStatus enum to keep track of the payment status. The definition of this class is provided below:

```java
public abstract class Payment {
  private int paymentId;
  private double amount;
  private PaymentStatus status;
  private Date timestamp;

  public abstract boolean makePayment();
}

public class Cash extends Payment {
    public boolean makePayment() {
        // functionality
    }
}

public class CreditCard extends Payment {
    private String nameOnCard;
    private String cardNumber;

    public boolean makePayment() {
        // functionality
    }
}
```

```c#
public abstract class Payment {
  private int paymentId;
  private double amount;
  private PaymentStatus status;
  private DateTime timestamp;
  
  public abstract bool MakePayment();
}

class Cash : Payment {
    public override bool MakePayment() {
        // functionality
    }
}

class CreditCard : Payment {
    private string nameOnCard;
    private string cardNumber;
    
    public override bool MakePayment() {
        // functionality
    }
}
```

```python
# Payment is an abstract class
from abc import ABC, abstractmethod

class Payment(ABC):
  def __init__(self, payment_id, amount, status, timestamp):
    self.__payment_id = payment_id
    self.__amount = amount
    self.__status = status # Refers to the PaymentStatus enum
    self.__timestamp = timestamp

  @abstractmethod
  def make_payment(self):
    pass

class Cash(Payment):
  def __init__(self, payment_id, amount, status, timestamp):
    super().__init__(payment_id, amount, status, timestamp)

  def make_payment(self):
    # functionality
    pass

class CreditCard(Payment):
  def __init__(self, payment_id, amount, status, timestamp, name_on_card, card_number):
    self.__name_on_card = name_on_card
    self.__card_number = card_number
    super().__init__(payment_id, amount, status, timestamp)

  def make_payment(self):
    # functionality
    pass
```

```c++
class Payment {
  private:
    int paymentId;
    double amount;
    PaymentStatus status;
    time_t timestamp;
    
  public:
    virtual bool makePayment() = 0;
};

class Cash : public Payment {
  public bool makePayment() {
      // functionality
  }
};

class CreditCard : public Payment {
  private:  
    string nameOnCard;
    string cardNumber;

  public:
    bool makePayment() {
      // functionality
  }
};
```

```javascript
// Payment is an abstract class
class Payment {
  #paymentId
  #amount;
  #status;
  #timestamp;
  constructor(paymentId, amount, timestamp, status) {
    if (this.constructor == Payment) {
      throw new Error("Abstract classes can't be instantiated.");
    }
    else {
      this.#paymentId = paymentId;
      this.#amount = amount;
      this.#timestamp = timestamp;
      this.#status = status; // Refers to the PaymentStatus enum
    }
  }
  makePayment() { }
}
class Cash extends Payment{
  constructor(paymentId, amount, timestamp, status) {
    super(paymentId, amount, timestamp, status);
  }
  makePayment(){
    // functionality
  }
}
class CreditCard extends Payment{
  #nameOnCard;
  #cardNumber;
  constructor(paymentId, amount, timestamp, status, nameOnCard, cardNumber) {
    this.#nameOnCard = nameOnCard;
    this.#cardNumber = cardNumber;
    super(paymentId, amount, timestamp, status);
  }
  makePayment(){
    // functionality
  }
}
```

### Notification
The Notification class is another abstract class responsible for sending notifications with two child classes: SMSNotification and EmailNotification . The implementation of this class is shown below:

```java
public abstract class Notification {
    private int notificationId;
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

    def send_notification(account):
        # functionality 
        pass

class EmailNotification(Notification):
    def __init__(self, notification_id, created_on, content):
        super().__init__(notification_id, created_on, content)

    def send_notification(account):
        # functionality 
        pass
```

```c++
// Notification is an abstract class
class Notification {
    private: 
        int notificationId;
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
  sendNotification(account) {
    // functionality 
  }
}

class EmailNotification extends Notification {
  constructor() {
    super(notificationId, createdOn, content);
  }
  sendNotification(account) {
    // functionality 
  }
}
```
### Search and catalog
The SearchCatalog class contains the flight instance information and implements the Search interface class to enable the search functionality based on the criteria. Both classes are defined below:

```java
public interface Search {
  // Interface method (does not have a body)
  public List<FlightInstance> searchFlight(Airport source, Airport dest, Date arrival, Date departure);
}

public class SearchCatalog implements Search {
  private HashMap<Quartet<Airport, Airport, Date, Date>, List<FlightInstance>> flights;

  public List<FlightInstance> searchFlight(Airport source, Airport dest, Date arrival, Date departure) {
    // functionality
  }
}
```

```c#
interface Search {
  public List<FlightInstance> SearchFlight(Airport source, Airport dest, DateTime arrival, DateTime departure);
}

class SearchCatalog : Search {
  private Dictionary<(Airport, Airport, DateTime, DateTime), List<FlightInstance>> flights;

  public List<FlightInstance> SearchFlight(Airport source, Airport dest, DateTime arrival, DateTime departure) {
    // functionality
  }
}

```

```python
from abc import ABC, abstractmethod

class Search(ABC):
  def search_flight(self, source, dest, arrival, departure):
    pass

class SearchCatalog(Search):
  def __init__(self):
    self.__flights = {}

  def search_flight(self, source, dest, arrival, departure):
    # functionality
    pass
```

```c++
class Search {
  public:
    virtual vector<FlightInstance> searchFlight(Airport source, Airport dest, time_t arrival, time_t departure) = 0;
};

class SearchCatalog : public Search {
  private:
    map<tuple<Airport, Airport, time_t, time_t>, vector<FlightInstance>> flights;
    
  public:
    vector<FlightInstance> searchFlight(Airport source, Airport dest, time_t arrival, time_t departure) {
      // functionality
    }
};

```

```javascript
class Search {
  constructor() {
    if (this.constructor === Search) {
      throw new Error("Abstract classes can't be instantiated.");
    }
  }
  searchFlight(source, dest, arrival, departure) {}
}

class SearchCatalog extends Search {
  #flights;
  constructor() {
    this.#flights = new Map();
  }
  searchFlight(source, dest, arrival, departure) {
    // functionality
  }
}
```


### Airport, aircraft, and airline
This section contains classes like Airport, Aircraft, and Airline that make up the infrastructure of our airline management system. Here, Airline is a Singleton class. The definition of these classes is given below:

```java
public class Airport {
  private String name;
  private String code;
  private Address address;
  private List<Flight> flights;
}

public class Aircraft {
  private String name;
  private String code;
  private String model;
  private int seatCapacity;
  private List<Seat> seats;
}

public class Airline {
  private String name;
  private String code;
  private List<Flight> flights;
  private List<Aircraft> aircrafts;
  private List<Crew> crew;
  
  // The Airline is a singleton class that ensures it will have only one active instance at a time
  private static Airline airline = null;
  
  // Created a static method to access the singleton instance of Airline class
  public static Airline getInstance() {
    if (airline == null) {
      airline = new Airline();
    }
    return airline;
  }
}
```
```c#
class Airport {
  private string name;
  private string code;
  private Address address;
  private List<Flight> flights;
}

class Aircraft {
  private string name;
  private string code;
  private string model;
  private int seatCapacity;
  private List<Seat> seats;
}

class Airline {
  private string name;
  private string code;
  private List<Flight> flights;
  private List<Aircraft> aircrafts;
  private List<Crew> crew;
  
  // The Airline is a singleton class that ensures it will have only one active instance at a time
  private static Airline airline = null;

  // Created a static method to access the singleton instance of Airline
  public static Airline GetInstance {
    get {
      if (airline == null) {
        airline = new Airline();
      }
      return airline;
    }
  }
  
}

```

```python
class Airport:
  def __init__(self, name, code, address):
    self.__name = name
    self.__code = code
    self.__address = address
    self.__flights = [] # List of flights

class Aircraft:
  def __init__(self, name, code, model, seatCapacity, seats):
    self.__name = name
    self.__code = code
    self.__models = model
    self.__seatCapacity = seatCapacity
    self.__seats = [] # List of seats

# The Airline is a singleton class that ensures it will have only one active instance at a time
class __Airline(object):
  __instances = None
  
  def __new__(cls):
    if cls.__instances is None:
        cls.__instances = super(__Airline, cls).__new__(cls)
    return cls.__instances

class Airline(metaclass = __Airline):
  def __init__(self, name, code):
    self.__name = name
    self.__code = code
    self.__flights = [] # List of flights
    self.__aircrafts = [] # List of aircrafts
    self.__crew = [] # List of crew
```

```c++
class Airport {
  private: 
    string name;
    string code;
    Address address;
    vector<Flight> flights;
};

class Aircraft {
  private:
    string name;
    string code;
    string model;
    int seatCapacity;
    vector<Seat> seats;
};

class Airline {
  private:
    string name;
    string code;
    vector<Flight> flights;
    vector<Aircraft> aircrafts;
    vector<Crew> crew;
    // The Airline is a singleton class that ensures it will have only one active instance at a time
    static Airline airline = NULL;

  public:
    // Created a static method to access the singleton instance of Airline
    static Airline getInstance() {
      if (airline == NULL) {
        airline = new Airline();
      }
      return airline;
    }
};

```

```javascript
class Airport {
  #name; 
  #code;
  #address;
  #flights;
  constructor(name, code, address) {
    this.#name = name;
    this.#code = code;
    this.#address = zipaddressCode; 
    this.#flights = new Array(); // List of flights
  }
}

class Aircraft {
  #name; 
  #code;
  #model;
  #seatCapacity;
  #seats;
  constructor(name, code, model, seatCapacity, seats) {
    this.#name = name;
    this.#code = code;
    this.#model = model; 
    this.#seatCapacity = seatCapacity; 
    this.#seats = seats; // List of seats
  }
}

class Airline {
  #name; 
  #code;
  #flights;
  #aircrafts;
  #crew;
  constructor(name, code) {
    this.#name = name;
    this.#code = code;
    this.#flights = new Array(); // List of flights
    this.#crew = new Array();
    this.#aircrafts = new Array(); // List of aircrafts
    // The Airline is a singleton class that ensures it will have only one active instance at a time
    var airline = null;
  }
  // Created a static method to access the singleton instance of Airline
    getInstance() {
        if (airline == null) {
            airline = new Airline;
        }
        return airline;
    }
}
```
## Wrapping up
We've explored the complete design of the airline management system in this chapter. We've looked at how a basic airline management system can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
