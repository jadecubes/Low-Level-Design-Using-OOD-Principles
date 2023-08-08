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
### Person
### Service
### Invoice
### Room booking
### Bill transaction
### Notification
### Room, room key and room housekeeping
### Search and catalog
### Hotel and hotel branch
## Wrapping up
