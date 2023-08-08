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
RoomBooking is a class responsible for managing the bookings for a room. The implementation of this class is given below:

```java
public class RoomBooking {
    private String reservationNumber;
    private Date startDate;
    private int durationInDays;
    private BookingStatus status;
    private Date checkin;
    private Date checkout;

    private int guestId;
    private Room room;
    private Invoice invoice;
    private List<Notification> notifications;

    public static RoomBooking fectchDetails(String reservationNumber);
}
```

```c#
public class RoomBooking {
    private string reservationNumber;
    private DateTime startDate;
    private int durationInDays;
    private BookingStatus status;
    private DateTime checkin;
    private DateTime checkout;

    private int guestId;
    private Room room;
    private Invoice invoice;
    private List<Notification> notifications;

    public static RoomBooking FetchDetails(String reservationNumber);
}
```

```python
class RoomBooking:
  def __init__(self, reservation_number, start_date, duration_in_days, booking_status):
    self.__reservation_number = reservation_number
    self.__start_date = start_date
    self.__duration_in_days = duration_in_days
    self.__booking_status = booking_status
    self.__checkin = None
    self.__checkout = None
    self.__guest_id = 0
    self.__room = None
    self.__invoice = None
    self.__notifications = []

  def fetch_details(self, reservation_number):
    None
```

```c++
class RoomBooking {
    private: 
        string reservationNumber;
        time_t startDate;
        int durationInDays;
        BookingStatus status;
        time_t checkin;
        time_t checkout;
        int guestID;
        Room room;
        Invoice invoice;
        vector<Notification> notifications;

    public: 
        static RoomBooking fectchDetails(string reservationNumber);
};
```

```javascript
class RoomBooking {
    #reservationNumber;
    #startDate;
    #durationInDays;
    #status;
    #checkin;
    #checkout;
    #guestId;
    #room;
    #invoice;
    #notifications;
    constructor(reservationNumber, startDate, durationInDays, status, checkin,
    checkout, guestID, room, invoice) {
        this.#reservationNumber = reservationNumber;
        this.#startDate = startDate;
        this.#durationInDays = durationInDays;
        this.#status = status;
        this.#checkin = checkin;
        this.#checkout = checkout;
        this.#guestID = guestID;
        this.#room = room;
        this.#invoice = invoice;

        this.#notifications = new Array();
    }
    static fectchDetails(reservationNumber);
}
```
### Bill transaction
After generating an invoice, a customer needs to pay the bill to confirm the booking of the room. A BillTransaction class is required to store the information of bill payment. Three ways to pay the bill are check transactions, cash transactions, and credit card transactions.

```java
// BillTransaction is an abstract class
public abstract class BillTransaction {
    private Date creationDate;
    private double amount;      
    private PaymentStatus status;

    public abstract void initiateTransaction();
}

class CheckTransaction extends BillTransaction {
    private String bankName;
    private String checkNumber;

    public void initiateTransaction() {
        // functionality 
    }
}

class CreditCardTransaction extends BillTransaction {
    private String nameOnCard;
    private int zipcode;

    public void initiateTransaction() {
        // functionality 
    }
}

class CashTransaction extends BillTransaction {
    private double cashTendered;

    public void initiateTransaction() {
        // functionality 
    }
}
```

```c#
// BillTransaction is an abstract class
public abstract class BillTransaction {
    private DateTime creationDate;
    private double amount;      
    private PaymentStatus status;

    public abstract void InitiateTransaction();
}

class CheckTransaction : BillTransaction {
    private String bankName;
    private String checkNumber;

    public override void InitiateTransaction() {
        // functionality 
    }
}

class CreditCardTransaction : BillTransaction {
    private String nameOnCard;
    private int zipCode;

    public override void InitiateTransaction() {
        // functionality 
    }
}

class CashTransaction : BillTransaction {
    private double cashTendered;

    public override void InitiateTransaction() {
        // functionality 
    }
}
```

```python
# BillTransaction is an abstract class
from abc import ABC, abstractmethod
class BillTransaction(ABC):
    def __init__(self, creation_date, amount, status):
        self.__creation_date = creation_date
        self.__amount = amount
        self.status = status

    @abstractmethod
    def initiate_transaction():
        pass

class CheckTransaction(BillTransaction):
    def __init__(self, creation_date, amount, status, bank_name, check_number):
        super().__init__(creation_date, amount, status)
        self.__bank_name = bank_name
        self.__check_number = check_number

    def initiate_transaction():
        pass

class CreditCardTransaction(BillTransaction):
    def __init__(self, creation_date, amount, status, name_on_card, zip_code):
        super().__init__(creation_date, amount, status)
        self.__name_on_card = name_on_card
        self.__zip_code = zip_code

    def initiate_transaction():
        pass

class CashTransaction(BillTransaction):
    def __init__(self, creation_date, amount, status, cash_tendered):
        super().__init__(creation_date, amount, status)
        self.__cash_tendered = cash_tendered

    def initiate_transaction():
        pass
```

```c++
// BillTransaction is an abstract class
class Billtransaction {
    private: 
        time_t creationDate;
        double amount;      
        PaymentStatus status;

    public: 
        void initiateTransaction() = 0;
};

class CheckTransaction : public Billtransaction {
    private: 
        string bankName;
        string checkNumber;

    public: 
        void initiateTransaction() {
            // functionality 
        }
};

class CreditCardTransaction : public Billtransaction {
    private: 
        string nameOnCard;
        int zipcode;

    public: 
        void initiateTransaction() {
            // functionality 
        }
};

class CashTransaction : public Billtransaction {
    private: 
        double cashTendered;

    public: 
        void initiateTransaction() {
            // functionality 
        }
};
```

```javascript
// BillTransaction is an abstract class
class BillTransaction {
    #creationDate;
    #amount;      
    #status;

    constructor(creationDate, amount, status) {
        if (this.constructor == Notification) {
          throw new Error("Abstract classes can't be instantiated.");
        }
        else {
            this.#creationDate = creationDate;
            this.#amount = amount;
            this.#status = status;
        }
    }

    initiateTransaction();
}

class CheckTransaction extends BillTransaction {
    #bankName;
    #checkNumber;

    constructor(bankName, checkNumber, creationDate, amount, status) {
        this.#bankName = bankName;
        this.#checkNumber = checkNumber;
        super(creationDate,amount,status);
    }

    initiateTransaction() {
        // functionality 
    }
}

class CreditCardTransaction extends BillTransaction {
    #nameOnCard;
    #zipCode;

    constructor(nameOnCard, zipCode, creationDate, amount, status) {
        this.#nameOnCard = nameOnCard;
        this.#zipCode = zipCode;
        super(creationDate,amount,status);
    }

    initiateTransaction() {
        // functionality 
    }
}

class CashTransaction extends BillTransaction {
    #cashTendered;

    constructor(cashTendered, creationDate, amount, status) {
        this.#cashTendered = cashTendered;
        super(creationDate,amount,status);
    }

    initiateTransaction() {
        // functionality 
    }

}
```
### Notification
The Notification class is another abstract class responsible for sending notifications, with the SMSNotification and EmailNotification classes as its child. The implementation of this class is given below:

```java
// Notification is an abstract class
public abstract class Notification {
    private int notificationId;
    // The Date data type represents and deals with both date and time.
    private Date createdOn;      
    private String content;

    public abstract void sendNotification(Person person);
}

class SMSNotification extends Notification {

    public void sendNotification(Person person) {
        // functionality 
    }
}

class EmailNotification extends Notification {

    public void sendNotification(Person person) {
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

    public abstract void SendNotification(Person person);
}

class SMSNotification : Notification {

    public override void SendNotification(Person person) {
        // functionality 
    }
}

class EmailNotification : Notification {

    public override void SendNotification(Person person) {
        // functionality 
    }
}
```

```python
# Notification is an abstract class
from abc import ABC, abstractmethod
class Notification(ABC):
    def __init__(self, notification_id, created_on, content):
        self.__notificationId = notificationId
        self.__created_on = created_on
        self.__content = content

    # account here refers to an instance of the Account class 
    @abstractmethod
    def send_notification(person):
        pass

class SMSNotification(Notification):
    def __init__(self, notification_id, created_on, content):
        super().__init__(notification_id, created_on, content)

    # account here refers to an instance of the Account class 
    def send_notification(person):
        # functionality 
        pass

class EmailNotification(Notification):
    def __init__(self, notification_id, created_on, content):
        super().__init__(notification_id, created_on, content)

    # account here refers to an instance of the Account class 
    def send_notification(person):
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
        void sendNotification(Person person) = 0;
};

class SMSNotification : public Notification {
    public: 
        void sendNotification(Person person) {
            // functionality 
        }
};

class EmailNotification : public Notification {
    public: 
        void sendNotification(Person person) {
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
    sendNotification(person){};
}

class SMSNotification extends Notification {
    constructor(){
        super(notificationId, createdOn, content);
    }

    // account here refers to an instance of the Account class 
    sendNotification(person){
        // functionality 
    }
}

class EmailNotification extends Notification {
    constructor(){
        super(notificationId, createdOn, content);
    }

    // account here refers to an instance of the Account class 
    sendNotification(person){
        // functionality 
    }
}
```
### Room, room key and room housekeeping
The Room class represents a room in the hotel. RoomKey is a class used to express the electronic key card and the RoomHousekeeping is a class used to keep track of all the housekeeping records for the rooms. The implementation of these classes is given below:

```java
public class Room {
    private String roomNumber;
    private RoomStyle style;
    private RoomStatus status;
    private double bookingPrice;
    private boolean isSmoking;
    private List<RoomKey> keys;
    private List<RoomHousekeeping> housekeepingLog;

    public boolean isRoomAvailable();
    public boolean checkin();
    public boolean checkout();
}

public class RoomKey {
    private String keyId;
    private String barcode;
    private Date issuedAt;
    private boolean isActive;
    private boolean isMaster;

    public boolean assignRoom(Room room);
}

public class RoomHousekeeping
{
    private String description;
    private Date startDatetime;
    private int duration;
    private Housekeeper housekeeper;

    public boolean addHousekeeping(Room room);
}
```

```c#
public class Room {
    private string roomNumber;
    private RoomStyle style;
    private RoomStatus status;
    private double bookingPrice;
    private bool isSmoking;
    private List<RoomKey> keys;
    private List<RoomHousekeeping> housekeepingLog;

    public bool IsRoomAvailable();
    public bool Checkin();
    public bool Checkout();
}

public class RoomKey {
    private string keyId;
    private string barcode;
    private DateTime issuedAt;
    private bool isActive;
    private bool isMaster;

    public bool AssignRoom(Room room);
}

public class RoomHousekeeping
{
    private string description;
    private DateTime startDatetime;
    private int duration;
    private Housekeeper housekeeper;

    public bool AddHousekeeping(Room room);
}
```

```python
class Room:
    def __init__(self, room_number, style, status, booking_price, is_smoking):
        self.__room_number = room_number
        self.__style = style
        self.__status = status
        self.__booking_price = booking_price
        self.__is_smoking = is_smoking
        self.__keys = []
        self.__room_housekeeping_log = []

    def is_room_available():
        None

    def checkin():
        None

    def checkout():
        None

class RoomKey:
  def __init__(self, key_id, barcode, is_active, is_master):
    self.__key_id = key_id
    self.__barcode = barcode
    self.__issued_at = datetime.date.today()
    self.__is_active = is_active
    self.__is_master = is_master

  def assign_room(self, room):
    None


class RoomHousekeeping:
  def __init__(self, description, duration, housekeeper):
    self.__description = description
    self.__start_datetime = datetime.date.today()
    self.__duration = duration
    self.__housekeeper = housekeeper

  def add_housekeeping(self, room):
    None
```

```c++
class Room {
    private: 
        string roomNumber;
        RoomStyle style;
        RoomStatus status;
        double bookingPrice;
        bool isSmoking;
        vector<RoomKey> keys;
        vector<RoomHousekeeping> housekeepingLog;

    public: 
        bool isRoomAvailable();
        bool checkin();
        bool checkout();
};

class RoomKey {
    private: 
        string keyId;
        string barcode;
        time_t issuedAt;
        bool isActive;
        bool isMaster;

    public: 
        bool assignRoom(Room room);
};

class RoomHousekeeping {
    private: 
        string description;
        time_t startDatetime;
        int duration;
        Housekeeper housekeeper;

    public: 
        bool addHousekeeping(Room room);
};
```

```javascript
class Room {
    #roomNumber;
    #style;
    #status;
    #bookingPrice;
    #isSmoking;
    #keys;
    #housekeepingLog;
    constructor(roomNumber, style, status, bookingPrice, isSmoking) {
        this.#roomNumber = roomNumber;
        this.#style = style;
        this.#status = status;
        this.#bookingPrice = bookingPrice;
        this.#isSmoking = isSmoking;

        this.#keys = new Array();
        this.#housekeepingLog = new Array();
    }

    isRoomAvailable();
    checkin();
    checkout();
}

class RoomKey {
    #keyId;
    #barcode;
    #issuedAt;
    #isActive;
    #isMaster;
    constructor(keyId, barcode, issuedAt, isActive, isMaster){
        this.#keyId = keyId;
        this.#barcode = barcode;
        this.#issuedAt = issuedAt;
        this.#isActive = isActive;
        this.#isMaster = isMaster;
    }
    assignRoom(room);
}

class RoomHousekeeping
{
    #description;
    #startDatetime;
    #duration;
    #housekeeper;
    constructor(description, startDatetime, duration, housekeeper){
        this.#description = description;
        this.#startDatetime = startDatetime;
        this.#duration = duration;
        this.#housekeeper = housekeeper;
    }
    addHousekeeping(room);
}
```
### Search and catalog
Search is an interface, and the Catalog class implements the search interface to help in the room search. The code to perform this functionality is presented below:

```java
public interface Search {
    public static List<Room> search(RoomStyle style, Date date, int duration);
}

public class Catalog implements Search {
    private List<Room> rooms;

    public List<Room> search(RoomStyle style, Date date, int duration);
}
```

```c#
public interface Search {
    public static List<Room> Search(RoomStyle style, DateTime date, int duration);
}

public class Catalog : Search {
    private List<Room> rooms;

    public List<Room> Search(RoomStyle style, DateTime date, int duration);
}
```

```python
from abc import ABC, abstractmethod
class Search(ABC):
    def search(style, start_date, duration):
        None


class Catalog(Search):
    def __init__(self):
        self.__rooms = []

    def search(style, date, duration):
        None
```

```c++
class Search {
    public:  
        static vector<Room> search(RoomStyle style, time_t date, int duration);
};

class Catalog : public Search {
    private: 
        vector<Room> rooms;

    public: 
        vector<Room> search(RoomStyle style, time_t date, int duration);
};
```

```javascript
class Search {
    static search(style, date, duration);
}

class Catalog extends Search {
    #rooms;

    constructor() {
        this.#rooms = new Array();
    }

    search(style, date, duration);
}
```
### Hotel and hotel branch
The Hotel class is the base class of the system that represents the hotel. The implementation of these classes is given below:

```java
public class HotelBranch {
  private String name;
  private Address location;

  public List<Room> getRooms();
}

public class Hotel {
  private String name;
  private List<HotelBranch> locations;

  public boolean addLocation(HotelBranch location);
}
```

```c#
class HotelBranch {
  private string name;
  private Address location;

  public List<Room> GetRooms();
}

class Hotel {
  private string name;
  private List<HotelBranch> locations;

  public bool AddLocation(HotelBranch location);
}
```

```python
class HotelBranch:
    def __init__(self, name, address):
        self.__name = name
        self.__address = address
  
    def get_rooms():
        None

class Hotel:
    def __init__(self, name, hotel_branch):
        self.__name = name
        self.__hotel_branch = hotel_branch

    def add_location(self, location):
        None
```

```c++
class HotelBranch {
  private: 
    string name;
    Address location;

  public: 
    vector<Room> getRooms();
};

class Hotel {
  private: 
    string name;
    vector<HotelBranch> locations;

  public: 
    bool addLocation(HotelBranch location);
};
```

```javascript
class HotelBranch {
  #name;
  #location;
    constructor(name,location){
        this.#name = name;
        this.#location = location;
    }
  getRooms();
}

class Hotel {
  #name;
  #locations;
  constructor(name){
        this.#name = name;
        this.#locations = new Array();
    }
    addLocation(location);
}
```
## Wrapping up
We've explored the complete design of a hotel management system in this chapter. We've looked at how a basic hotel management system can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
