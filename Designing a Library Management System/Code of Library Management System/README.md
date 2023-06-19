# Code of Library Management System
We’ve gone over the different aspects of the library management system and observed the attributes attached to the problem using various UML diagrams. Let us now explore the more practical side of things, where we will work on implementing the library management system using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the library management system:

- Java

- C#

- Python

- C++

- JavaScript

## Library management
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```

### Enumerations
First, we will define all the enumerations required in the library management system. According to the class diagram, there are four enumerations used in the system: BookFormat, BookStatus, ReservationStatus, and AccountStatus. The code to implement these enumerations is as follows:`
```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```
```java
// definition of enumerations used in library management system
enum BookFormat {
    HARDCOVER,
    PAPERBACK,
    AUDIOBOOK,
    EBOOK,
    NEWSPAPER,
    MAGAZINE,
    JOURNAL
}

enum BookStatus {
    AVAILABLE,
    RESERVED,
    LOANED,
    LOST
}

enum ReservationStatus {
    WAITING,
    PENDING,
    CANCELED,
    NONE
}

enum AccountStatus {
    ACTIVE,
    CLOSED,
    CANCELED,
    BLACKLISTED,
    NONE
}
            Enum definitions
```

```c#
// definition of enumerations used in library management system
enum BookFormat {
    HARDCOVER,
    PAPERBACK,
    AUDIOBOOK,
    EBOOK,
    NEWSPAPER,
    MAGAZINE,
    JOURNAL
}
  
enum BookStatus {
    AVAILABLE,
    RESERVED,
    LOANED,
    LOST
}

enum ReservationStatus {
    WAITING,
    PENDING,
    CANCELED,
    NONE
}

enum AccountStatus {
    ACTIVE,
    CLOSED,
    CANCELED,
    BLACKLISTED,
    NONE
}
            Enum definitions
```

```python

# definition of enumerations used in library management system
class BookFormat(Enum):
  HARDCOVER = 1
  PAPERBACK = 2
  AUDIOBOOK = 3
  EBOOK = 4
  NEWSPAPER = 5
  MAGAZINE = 6
  JOURNAL = 7


class BookStatus(Enum):
  AVAILABLE = 1
  RESERVED = 2
  LOANED = 3
  LOST = 4


class ReservationStatus(Enum):
  WAITING = 1
  PENDING = 2
  CANCELED = 3
  NONE = 4


class AccountStatus(Enum):
  ACTIVE = 1
  CLOSED = 2
  CANCELED = 3
  BLACKLISTED = 4
  NONE = 5
  
              Enum definitions
```

```c++
// definition of enumerations used in library management system
enum BookFormat {
    HARDCOVER,
    PAPERBACK,
    AUDIOBOOK,
    EBOOK,
    NEWSPAPER,
    MAGAZINE,
    JOURNAL
};
  
enum BookStatus {
    AVAILABLE,
    RESERVED,
    LOANED,
    LOST
};

enum ReservationStatus{
    WAITING,
    PENDING,
    CANCELED,
    NONE
};

enum AccountStatus{
    ACTIVE,
    CLOSED,
    CANCELED,
    BLACKLISTED,
    NONE
};
               Enum definitions
```

```javascript
const BookFormat = Object.freeze({
    HARDCOVER,
    PAPERBACK,
    AUDIOBOOK,
    EBOOK,
    NEWSPAPER,
    MAGAZINE,
    JOURNAL

});
  
const BookStatus  = Object.freeze({
    AVAILABLE,
    RESERVED,
    LOANED,
    LOST

});

const ReservationStatus = Object.freeze({
    WAITING,
    PENDING,
    CANCELED,
    NONE

});

const AccountStatus = Object.freeze({
    ACTIVE,
    CLOSED,
    CANCELED,
    BLACKLISTED,
    NONE
});
             Enum definitions
```

### Address and person
This section contains the code for Address and Person classes where the Person class is composed of an Address class. The implementation of these classes can be found below:
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
    private String phone;
}
          The Address and Person classes
```

```c#
class Address {
    private String streetAddress;
    private String city;
    private String state;
    private int zipCode;
    private String country;
}

class Person {
    private String name;
    private Address address;
    private String email;
    private String phone;
}
          The Address and Person classes
```

```python
class Address:
  def __init__(self, street, city, state, zip_code, country):
    self.__street_address = street
    self.__city = city
    self.__state = state
    self.__zip_code = zip_code
    self.__country = country


class Person(ABC):
  def __init__(self, name, address, email, phone):
    self.__name = name
    self.__address = address
    self.__email = email
    self.__phone = phone
               The Address and Person classes
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
        string phone;
};
     The Address and Person classes
```

```javascript
class Address {
    #streetAddress;
    #city;
    #state;
    #zipCode;
    #country;
}

class Person {
    #name;
    #address;
    #email;
    #phone;
}

         The Address and Person classes
```


### User
### Book reservation, book lending and fine
### Book and rack
### Notification
### Search and catalog
### Library
## Wrapping up
