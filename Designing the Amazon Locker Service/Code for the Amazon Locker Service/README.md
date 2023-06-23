# Code for the Amazon Locker Service
We've gone over the different aspects of the Amazon Locker service and observed the attributes attached to the problem using various UML diagrams. Let’s explore the more practical side of things, where we will work on implementing the Amazon Locker service using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the Amazon Locker service:

- Java

- C#

- Python

- C++

- JavaScript

## Amazon Locker service classes
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```
### Enumerations
First, we will define all the enumerations used in the Amazon Locker service. According to the class diagram, there are two enumerations in the system, i.e., LockerSize and LockerState The code to implement these enumerations is as follows:
```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze()  method as an alternative that freezes an object and prevents further modifications.
```
```
enumerations: A special data type which contains a set of predefined constants.
```

```java
// definition of enumerations used in the Amazon Locker service
public enum LockerSize {
    EXTRA_SMALL,
    SMALL,
    MEDIUM,
    LARGE,
    EXTRA_LARGE,
    DOUBLE_EXTRA_LARGE
}
public enum LockerState {
    CLOSED,
    BOOKED,
    AVAILABLE
}
```

```c#
// definition of enumerations used in the Amazon Locker service
enum LockerSize {
    EXTRA_SMALL,
    SMALL,
    MEDIUM,
    LARGE,
    EXTRA_LARGE,
    DOUBLE_EXTRA_LARGE
}
enum LockerState {
    CLOSED,
    BOOKED,
    AVAILABLE
}
            Constant definitions

```

```python
# definition of enumerations used in the Amazon Locker service
class LockerSize(enum.Enum):
    EXTRA_SMALL = 1
    SMALL = 2
    MEDIUM = 3
    LARGE = 4
    EXTRA_LARGE = 5
    DOUBLE_EXTRA_LARGE = 6
}
class LockerState(enum.Enum):
    CLOSED = 1
    BOOKED = 2
    AVAILABLE = 3
}
        Constant definitions

```

```c++
// definition of enumerations used in the Amazon Locker service
enum LockerSize {
    EXTRA_SMALL,
    SMALL,
    MEDIUM,
    LARGE,
    EXTRA_LARGE,
    DOUBLE_EXTRA_LARGE
}
enum LockerState {
    CLOSED,
    BOOKED,
    AVAILABLE
}

              Constant definitions
```

```javascript
// definition of enumerations used in the Amazon Locker service
const LockerSize = Object.freeze({
    EXTRA_SMALL,
    SMALL,
    MEDIUM,
    LARGE,
    EXTRA_LARGE,
    DOUBLE_EXTRA_LARGE
});
const LockerState = Object.freeze({
    CLOSED,
    BOOKED,
    AVAILABLE
});

Constant definitions

```

### Item and Order
The Item class represents the single item while the Order represents the order placed by the customer and can contain the list of items. The definition of these two classes is given below:

```java
public class Item {
  private String itemId;
  private int quantity;
}

public class Order {
  private String orderId;
  private List<Item> items;
  private String deliveryLocation;
}

The Item and Order classes
```

```c#
class Item {
  private string itemId;
  private int quantity;
}

class Order {
  private string orderId;
  private List<Item> items;
  private string deliveryLocation;
}

The Item and Order classes
```

```python
class Item:
  def __init__(self, item_id, quantity):
    self.__item_id = item_id
    self.__quantity = quantity

class Order:
  def __init__(self, order_id, items, delivery_location):
    self.__order_id = order_id
    self.__items = items # List of items
    self.__delivery_location = delivery_location 

    The Item and Order classes
```

```c++
class Item {
  private: 
    string itemId;
    int quantity;
};

class Order {
  private: 
    string orderId;
    vector<Item> items;
    string deliveryLocation;
};

The Item and Order classes

```

```javascript
class Item {
  #itemId;
  #quantity;
  constructor(itemId, quantity) {
    this.#itemId = itemId;
    this.#quantity = quantity; 
  }
}

class Order {
  #orderId;
  #items;
  #deliveryLocation;
  constructor(orderId, items, status) {
    this.#orderId = orderId;
    this.#items = items; // List of items
    this.#deliveryLocation = deliveryLocation; 
  }
}

The Item and Order classes

```

### Package and LockerPackage
When an order is packed, it is represented by the Package , and the package which is contained in the locker is represented by the LockerPackage class. The code to implement these classes is shown below:

```java
public class Package {
  private String packageId;
  private double packageSize;
  private Order order;

  public void pack();
}

public class LockerPackage extends Package {
  private int codeValidDays;
  private String lockerId;
  private String packageId;
  private String code;
  private Date packageDeliveryTime;

  public boolean isValidCode();
  public boolean verifyCode(String code);
}

The Package and LockerPackage classes

```

```c#
class Package {
  private string packageId;
  private double packageSize;
  private Order order;

  public void Pack();
}

class LockerPackage : Package {
  private int codeValidDays;
  private string lockerId;
  private string packageId;
  private string code;
  private DateTime PackageDeliveryTime;

  public bool IsValidCode();
  public bool VerifyCode(String code);
}

The Package and LockerPackage classes

```

```python
class Package:
    def __init__(self, package_id, package_size, order):
        self.__package_id = package_id
        self.__package_size = package_size
        self.__order = order
  
    def pack():
        None

class LockerPackage(Package):
    def __init__(self, code_valid_days, locker_id, package_id, code, package_delivery_time, package_id, package_size, order):
        self.__code_valid_days = code_valid_days
        self.__locker_id = locker_id
        self.__package_id = package_id
        self.__code = code
        self.__package_delivery_time = package_delivery_time
        super().__init__(package_id, package_size, order)
  
    def is_valid_code():
        None
    
    def verify_code(code):
        None

        The Package and LockerPackage classes

```

```c++
class Package {
  private:
    string packageId;
    double packageSize;
    Order order;

  public:
    void pack();
};

class LockerPackage : public Package {
  private: 
    int codeValidDays;
    string lockerId;
    string packageId;
    string code;
    time_t packageDeliveryTime;

  public: 
    bool isValidCode();
    bool verifyCode(string code);
};

The Package and LockerPackage classes

```

```javascript
class Package {
  #packageId;
  #packageSize;
  #order;

    constructor(packageId, packageSize, order) {
        this.#packageId = packageId;
        this.#packageSize = packageSize;
        this.#order = order;
    }
  pack();
}

class LockerPackage extends Package {
  #codeValidDays;
  #lockerId;
  #packageId;
  #code;
  #packageDeliveryTime;
    constructor(codeValidDays, lockerId, packageId, code, packageDeliveryTime, packageId, packageSize, order) {
        this.#codeValidDays = codeValidDays;
        this.#lockerId = lockerId; 
        this.#packageId = packageId;
        this.#code = code; 
        this.#packageDeliveryTime = packageDeliveryTime;
        super(packageId, packageSize, order);
    }
  isValidCode();
  verifyCode(code);
}

The Package and LockerPackage classes

```

### Locker and LockerLocation
The Locker is the most important class of the system and a LockerLocation can contain multiple Locker instances. The implementation of these classes is given below:
```java
public class Locker {
  private String lockerId;
  private LockerSize lockerSize;
  private String locationId;
  private LockerState lockerState;

  public boolean addPackage();
  public boolean removePackage();
}

public class LockerLocation {
  private String name;
  private List<Locker> lockers;
  private double longitude;
  private double latitude;
  private Date openTime;
  private Date closeTime;
}

The Locker and LockerLocation classes

```

```c#
class Locker {
  private string lockerId;
  private LockerSize lockerSize;
  private string locationId;
  private LockerState lockerState;

  public bool AddPackage();
  public bool RemovePackage();
}

class LockerLocation {
  private string name;
  private List<Locker> lockers;
  private double longitude;
  private double latitude;
  private DateTime openTime;
  private DateTime closeTime;
}

The Locker and LockerLocation classes

```

```python
class Locker:
    def __init__(self, locker_id, locker_size, location_id, locker_state):
        self.__locker_id = locker_id
        self.__locker_size = locker_size
        self.location_id = location_id
        self.__locker_state = locker_state 
  
    def add_package():
        None
    def remove_package():
        None

class LockerLocation:
    def __init__(self, name, lockers, longitude, latitude, open_time, close_time):
        self.__name = name
        self.__lockers = lockers # list of lockers
        self.__longitude = longitude
        self.__latitude = latitude 
        self.__open_time = open_time
        self.__close_time = close_time 

        The Locker and LockerLocation classes

```

```c++
class Locker {
  private: 
    string lockerId;
    LockerSize lockerSize;
    string locationId;
    LockerState lockerState;

  public: 
    bool addPackage();
    bool removePackage();
};

class LockerLocation {
  private: 
    string name;
    vector<Locker> lockers;
    double longitude;
    double latitude;
    time_t openTime;
    time_t closeTime;
};

The Locker and LockerLocation classes

```

```javascript
class Locker {
  #lockerId;
  #lockerSize;
  #locationId;
  #lockerState;

  constructor(lockerId, lockerSize, locationId, lockerState){
    this.#lockerId = lockerId;
    this.#lockerSize = lockerSize;
    this.#locationId = locationId;
    this.#lockerState = lockerState;
  }
  addPackage();
  removePackage();
}

class LockerLocation {
  #name;
  #lockers;
  #longitude;
  #latitude;
  #openTime;
  #closeTime;

  constructor(name, lockers, longitude, latitude, openTime, closeTime){
    this.#name = name;
    this.#lockers = new Array();  // list of lockers
    this.#longitude = longitude;
    this.#latitude = latitude;
    this.#openTime = openTime;
    this.#closeTime = closeTime; 
  }
}

The Locker and LockerLocation classes

```
### LockerService and Notification
The final class of an Amazon Locker service is the LockerService class which will be singleton class, which means that the entire system will have only one instance of this class. The following code provides the definition of the LockerService and Notification classes used in the Amazon Locker service:

```java
public class LockerService {
    private List<LockerLocation> locations;

    // The LockerService is a Singleton class that ensures it will have only one active instance at a time
    private static LockerService lockerService = null;
    
    // Created a static method to access the Singleton instance of LockerService class
    public static LockerService getInstance() {
        if (lockerService == null) {
            lockerService = new LockerService();
        }
        return lockerService;
    }
}

public class Notification {
    private String customerId;
    private String orderId;
    private String lockerId;
    private String code;

    public void send();
}

The LockerService and Notification classes

```

```c#
class LockerService {
    private List<LockerLocation> locations;

    // The LockerService is a singleton class that ensures it will have only one active instance at a time
    private static LockerService lockerService = null;
    
    // Created a static method to access the singleton instance of LockerService class
    public static LockerService GetInstance() {
        if (lockerService == null) {
            lockerService = new LockerService();
        }
        return lockerService;
    }
}

class Notification {
    private String customerId;
    private String orderId;
    private String lockerId;
    private String code;

    public void Send();
}

The LockerService and Notification classes

```

```python
class __LockerService(object):
  __instances = None
  
  def __new__(cls):
    if cls.__instances is None:
        cls.__instances = super(__LockerService, cls).__new__(cls)
    return cls.__instances

class LockerService(metaclass=__LockerService):
    def __init__(self):
      self.__locations = {}

class Notification:
    def __init__(self, customer_id, order_id, locker_id, code):
        self.__customer_id = customer_id
        self.__order_id = order_id
        self.__locker_id = locker_id
        self.__code = code
    
    def send():
      pass

      The LockerService and Notification classes

```

```c++
class LockerService {
    private:
        vector<LockerLocation> locations;
        static LockerService lockerService = NULL;
    public: 
        static LockerService getInstance() {
            if (lockerService == NULL) {
            lockerService = new LockerService();
            }
            return lockerService;
        }
};

class Notification {
    private: 
        string customerId;
        string orderId;
        string lockerId;
        string code;

    public:
        void send();
};

The LockerService and Notification classes

```

```javascript
class LockerService {
    #locations;
    constructor(){
        this.#locations = new Array();
    }

    // The LockerService is a singleton class that ensures it will have only one active instance at a time
    #lockerService = null;
    
    // Created a static method to access the singleton instance of LockerService class
    getInstance() {
        if (lockerService == null) {
            lockerService = new LockerService();
        }
        return lockerService;
    }
}

class Notification {
    #customerId;
    #orderId;
    #lockerId;
    #code;
    constructor(customerId, orderId, lockerId, code) {
        this.#customerId = customerId;
        this.#orderId = orderId;
        this.#lockerId = lockerId;
        this.#code = code;
    }
    send();
}

The LockerService and Notification classes

```
## Wrapping up
We've explored the complete design of an Amazon Locker service in this chapter. We've looked at how an Amazon Locker service design can be visualized using various UML diagrams.
