# Code for the Hotel Management System
We’ve reviewed different aspects of the hotel management system and observed the attributes attached to the problem using various UML diagrams. Let’s explore the more practical side of things, where we will work on implementing the hotel management system using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the hotel management system:

- Java

- C#

- Python

- C++

- JavaScript

## Hotel management system classes
In this section, we’ll provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public methods function.
```
### Enumerations
First, we will define all the enumerations required in the hotel management system. According to the class diagram, there are six enumerations used in the system, i.e., RoomStyle, RoomStatus, BookingStatus, AccountStatus, AccountType, and PaymentStatus. The code to implement these enumerations is as follows:
```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```

```java
// definition of enumerations used in hotel management system
enum RoomStyle {
    STANDARD, 
    DELUXE, 
    FAMILY_SUITE, 
    BUSINESS_SUITE
}

enum RoomStatus {
    AVAILABLE, 
    RESERVED, 
    OCCUPIED, 
    NOT_AVAILABLE, 
    BEING_SERVICED, 
    OTHER
}

enum BookingStatus {
    REQUESTED, 
    PENDING, 
    CONFIRMED,
    CANCELLED, 
    ABANDONED
}

enum AccountStatus {
    ACTIVE, 
    CLOSED, 
    CANCELED, 
    BLACKLISTED, 
    BLOCKED
}

enum AccountType {
    MEMBER, 
    GUEST, 
    MANAGER, 
    RECEPTIONIST
}

enum PaymentStatus {
    UNPAID, 
    PENDING, 
    COMPLETED, 
    FILLED, 
    DECLINED, 
    CANCELLED, 
    ABANDONED, 
    SETTLING, 
    SETTLED, 
    REFUNDED
}
```

```c#
// definition of enumerations used in elevator system
enum RoomStyle {
    STANDARD, 
    DELUXE, 
    FAMILY_SUITE, 
    BUSINESS_SUITE
}

enum RoomStatus {
    AVAILABLE, 
    RESERVED, 
    OCCUPIED, 
    NOT_AVAILABLE, 
    BEING_SERVICED, 
    OTHER
}

enum BookingStatus {
    REQUESTED, 
    PENDING, 
    CONFIRMED, 
    CANCELLED, 
    ABANDONED
}

enum AccountStatus {
    ACTIVE, 
    CLOSED, 
    CANCELED, 
    BLACKLISTED, 
    BLOCKED
}

enum AccountType {
    MEMBER, 
    GUEST, 
    MANAGER, 
    RECEPTIONIST
}

enum PaymentStatus {
    UNPAID, 
    PENDING, 
    COMPLETED, 
    FILLED, 
    DECLINED, 
    CANCELLED, 
    ABANDONED, 
    SETTLING, 
    SETTLED, 
    REFUNDED
}
```

```python
# definition of enumerations used in elevator system
class RoomStatus(enum.Enum):
  AVAILABLE = 1
  RESERVED = 2
  OCCUPIED = 3
  NOT_AVAILABLE = 4
  BEING_SERVICED = 5
  OTHER = 6


class BookingStatus(enum.Enum):
  REQUESTED = 1
  PENDING = 2
  CONFIRMED = 3
  CANCELED = 4
  ABANDONED = 5


class AccountStatus(enum.Enum):
  ACTIVE = 1
  CLOSED = 2
  CANCELED = 3
  BLACKLISTED = 4
  BLOCKED = 5


class AccountType(enum.Enum):
  MEMBER = 1
  GUEST = 2
  MANAGER = 3
  RECEPTIONIST = 4


class PaymentStatus(enum.Enum):
  UNPAID = 1
  PENDING = 2
  COMPLETED = 3
  FILLED = 4
  DECLINED = 5
  CANCELLED = 6
  ABANDONED = 7
  SETTLING = 8
  SETTLED = 9
  REFUNDED = 10
```

```c++
// definition of enumerations used in elevator system
enum RoomStyle {
    STANDARD, 
    DELUXE, 
    FAMILY_SUITE, 
    BUSINESS_SUITE
};

enum RoomStatus {
    AVAILABLE, 
    RESERVED, 
    OCCUPIED, 
    NOT_AVAILABLE, 
    BEING_SERVICED, 
    OTHER
};

enum BookingStatus {
    REQUESTED, 
    PENDING, 
    CONFIRMED, 
    CANCELLED, 
    ABANDONED
};

enum AccountStatus {
    ACTIVE, 
    CLOSED, 
    CANCELED, 
    BLACKLISTED, 
    BLOCKED
};

enum AccountType {
    MEMBER, 
    GUEST, 
    MANAGER, 
    RECEPTIONIST
};

enum PaymentStatus {
    UNPAID, 
    PENDING, 
    COMPLETED, 
    FILLED, 
    DECLINED, 
    CANCELLED, 
    ABANDONED, 
    SETTLING, 
    SETTLED, 
    REFUNDED
};
```

```javascript
// definition of enumerations used in elevator system
const RoomStyle = Object.freeze({
    STANDARD, 
    DELUXE, 
    FAMILY_SUITE, 
    BUSINESS_SUITE
});

const RoomStatus = Object.freeze({
    AVAILABLE, 
    RESERVED, 
    OCCUPIED, 
    NOT_AVAILABLE, 
    BEING_SERVICED, 
    OTHER
});

const BookingStatus = Object.freeze({
    REQUESTED, 
    PENDING, 
    CONFIRMED, 
    CANCELLED, 
    ABANDONED
});

const AccountStatus = Object.freeze({
    ACTIVE, 
    CLOSED, 
    CANCELED, 
    BLACKLISTED, 
    BLOCKED
});

const AccountType = Object.freeze({
    MEMBER, 
    GUEST, 
    MANAGER, 
    RECEPTIONIST
});

const PaymentStatus = Object.freeze({
    UNPAID, 
    PENDING, 
    COMPLETED, 
    FILLED, 
    DECLINED, 
    CANCELLED, 
    ABANDONED, 
    SETTLING, 
    SETTLED, 
    REFUNDED
});
```
### Address and account
This section contains the Address and Account classes. Here, the Address class is used as a custom data type. The implementation of these classes is shown below:

```java
public class Address {
    private String streetAddress;
    private String city;
    private String state;
    private int zipCode;
    private String country;
}

public class Account {
    private String id;
    private String password;
    private AccountStatus status;
  
    public boolean resetPassword();
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

class Account {
    private string id;
    private string password;
    private AccountStatus status;
  
    public bool ResetPassword();
}
```

```python
class Address:
  def __init__(self, street, city, state, zip_code, country):
    self.__street_address = street
    self.__city = city
    self.__state = state
    self.__zip_code = zip_code
    self.__country = country

class Account:
  def __init__(self, id, password, status=AccountStatus.ACTIVE):
    self.__id = id
    self.__password = password
    self.__status = status

  def reset_password(self):
    None
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

class Account {
    private: 
        string id;
        string password;
        AccountStatus status;
  
    public: 
        bool resetPassword();
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

class Account {
    #id;
    #password;
    #status;
    constructor(id, password, status){
        this.#id = id;
        this.#password = password;
        this.#status = status;
    }
  
    resetPassword();
}
```
### Person
Person is an abstract class that represents the various people or actors that can interact with the system. There are four types of persons: Guest, Receptionist, Server, and Housekeeper. The implementation of the mentioned classes is shown below:

```java
public abstract class Person {
    private String name;
    private Address address;
    private String email;
    private String phone;
    private Account account;
}


public class Guest extends Person {
    private int totalRoomsCheckedIn;

    public List<RoomBooking> getBookings();
}

public class Receptionist extends Person {
    public List<Member> searchMember(String name);
    public boolean createBooking();
}

public class Housekeeper extends Person {
    public boolean assignToRoom();
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


public class Guest : Person {
    private int totalRoomsCheckedIn;

    public List<RoomBooking> GetBookings();
}

public class Receptionist : Person {
    public List<Member> SearchMember(string name);
    public bool CreateBooking();
}

public class Housekeeper : Person {
    public bool AssignToRoom();
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


class Guest(Person):
  def __init__(self):
    self.__total_rooms_checked_in = 0

  def get_bookings(self):
    None


class Receptionist(Person):
  def search_member(self, name):
    None

  def create_booking(self):
    None

class Housekeeper(Person):
  def assignToRoom():
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


class Guest : public Person {
    private: 
        int totalRoomsCheckedIn;

    public: 
        vector<RoomBooking> getBookings();
};

class Receptionist : public Person {
    public: 
        vector<Member> searchMember(string name);
        bool createBooking();
};

public class HouseKeeper : public Person {
    public: 
        bool assignToRoom();
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

class Guest extends Person {
    #totalRoomsCheckedIn;
    constructor(totalRoomsCheckedIn, name, address, email, phone, account){
        this.#totalRoomsCheckedIn = totalRoomsCheckedIn;
        super(name, address, email, phone, account);
    }
    getBookings();
}

class Receptionist extends Person {
    searchMember(name);
    createBooking();
}

class HouseKeeper extends Person {
    assignToRoom();
}
```

### Service
Service is an abstract class, and this section represents different charges, Amenity, RoomService, and KitchenService), against a booking. The code to implement these classes is shown below:

```java
public abstract class Service {
    private Date issueAt;

    public boolean addInvoiceItem(Invoice invoice);
}

public class Amenity extends Service {
    private String name;
    private String description;
}

public class RoomService extends Service {
    private boolean isChargeable;
    private Date requestTime;
}

public class KitchenService extends Service {
    private String description;
}
```

```c#
public abstract class Service {
    private DateTime issueAt;
    
    public bool AddInvoiceItem(Invoice invoice);
}

public class Amenity : Service {
    private string name;
    private string description;
}

public class RoomService : Service {
    private bool isChargeable;
    private DateTime requestTime;
}

public class KitchenService : Service {
    private string description;
}
```

```python
from abc import ABC, abstractmethod
class RoomCharge(ABC):
  def __init__(self):
    self.__issue_at = datetime.date.today()

  def add_invoice_item(self, invoice):
    None

class Amenity(Service):
  def __init__(self, name, description):
    self.__name = name
    self.__description = description

class RoomService(Service):
  def __init__(self, is_chargeable, request_time):
    self.__is_chargeable = is_chargeable
    self.__request_time = request_time

class KitchenService(Service):
  def __init__(self, description):
    self.__description = description
```

```c++
class Service {
    private: 
        time_t issueAt;

    public: 
        bool addInvoiceItem(Invoice invoice);
};

class Amenity : public Service {
    private: 
        string name;
        string description;
};

class RoomService : public Service {
    private: 
        bool isChargeable;

    private: 
        time_t requestTime;
};

class KitchenService : public Service {
    private: 
        string description;
};
```

```javascript
class Service {
    #issueAt;
    addInvoiceItem(invoice);
    constructor(issueAt) {
        if (this.constructor == Service) {
          throw new Error("Abstract classes can't be instantiated.");
        }
        else{
            this.#issueAt = issueAt;
        }
    }
}

class Amenity extends Service {
    #name;
    #description;
    constructor(name, description, issueAt) {
        this.#name = name;
        this.#description = description;
        super(issueAt);
    }
}

class RoomService extends Service {
    #isChargeable;
    #requestTime;
    constructor(isChargeable, requestTime, issueAt) {
        this.#isChargeable = isChargeable;
        this.#requestTime = requestTime;
        super(issueAt);
    }
}

class KitchenService extends Service {
    #description;
    constructor(description, issueAt) {
        this.#description = description;
        super(issueAt);
    }
}
```

### Invoice
This section contains information on the Invoice class to create a bill. The implementation of this class is represented below:

```java
public class Invoice {
    private double amount;
    
    public boolean createBill();
}
```

```c#
class Invoice {
    private double amount;
    
    public bool CreateBill();
}
```

```python
class Invoice:
    def __init__(self, amount):
        self.__amount = amount
    
    def create_bill():
        None
```

```c++
class Invoice {
    private: 
        double amount;
    
    public: 
        bool createBill();
};
```

```javascript
class Invoice {
    #amount; 
    constructor(amount) {
        this.#amount = amount;
    }
    createBill();
}
```



### Room booking
### Bill transaction
### Notification
### Room, room key and room housekeeping
### Search and catalog
### Hotel and hotel branch
## Wrapping up
