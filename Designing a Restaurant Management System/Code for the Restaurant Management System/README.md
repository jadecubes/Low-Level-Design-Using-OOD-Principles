# Code for the Restaurant Management System
We've covered different aspects of the restaurant management system and observed the attributes attached to the problem using various UML diagrams. Let us now explore the more practical side of things, where we will work on implementing the restaurant management system using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the RMS:

- Java

- C#

- Python

- C++

- JavaScript
## Restaurant management system classes
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```
### Enumerations and custom data type
The following code provides the definition of the enumeration and custom data type used in the restaurant management system.

PaymentStatus: This enumeration keeps track of an order's payment status by the customer.

TableStatus: This enumeration keeps track of the table’s status.

SeatType: This enumeration represents the type of seat for a customer.

AccountStatus: This enumeration keeps track of an account's status.

OrderStatus: This enumeration keeps the customer's order status in check.

ReservationStatus: This enumeration represents the reservation status of a table.

Address: This custom datatype represents the address of the restaurant's branch or a person.
```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze() method as an alternative. This freezes an object and prevents further modifications.
```
```java
// Enumerations
enum PaymentStatus {
  Unpaid,
  Pending,
  Completed,
  Failed,
  Declined,
  Canceled,
  Abondoned,
  Settling,
  Refunded
}

enum TableStatus {
  Free,
  Reserved,
  Occupied,
  Other
}

enum SeatType {
  Regular,
  Kid,
  Accessible,
  Other
}

enum AccountStatus {
  Active,
  Closed,
  Canceled,
  Blacklisted
}

enum OrderStatus {
  Received,
  Preparing,
  Complete,
  Canceled,
  None
}

enum ReservationStatus {
  Requested,
  Pending,
  Confirmed,
  CheckedIn,
  Canceled,
  Abondoned
}

// Custom Address data type class
public class Address {
  private int zipCode;
  private String address;
  private String city;
  private String state;
  private String country;
}
```

```c#
// Enumerations
enum PaymentStatus {
  Unpaid,
  Pending,
  Completed,
  Failed,
  Declined,
  Canceled,
  Abondoned,
  Settling,
  Refunded
}

enum TableStatus {
  Free,
  Reserved,
  Occupied,
  Other
}

enum SeatType {
  Regular,
  Kid,
  Accessible,
  Other
}

enum AccountStatus {
  Active,
  Closed,
  Canceled,
  Blacklisted
}

enum OrderStatus {
  Received,
  Preparing,
  Complete,
  Canceled,
  None
}

enum ReservationStatus {
  Requested,
  Pending,
  Confirmed,
  CheckedIn,
  Canceled,
  Abondoned
}

// Custom Address data type class
class Address {
  private int zipCode;
  private String address;
  private String city;
  private String state;
  private String country;
}
```

```python
# Enumerations
class PaymentStatus(enum.Enum):
  Unpaid = 1
  Pending = 2
  Completed = 3
  Failed = 4
  Declined = 5
  Canceled = 6
  Abondoned = 7
  Settling = 8
  Refunded = 9
}

class TableStatus(enum.Enum):
  Free = 1
  Reserved = 2
  Occupied = 3
  Other = 4
}

class SeatType(enum.Enum):
  Regular = 1
  Kid = 2
  Accessible = 3
  Other = 4
}

class AccountStatus(enum.Enum):
  Active = 1
  Closed = 2
  Canceled = 3
  Blacklisted = 4
}

class OrderStatus(enum.Enum):
  Received = 1
  Preparing = 2
  Complete = 3
  Canceled = 4
  None = 5
}

class ReservationStatus(enum.Enum):
  Requested = 1
  Pending = 2
  Confirmed = 3
  CheckedIn = 4
  Canceled = 5
  Abondoned = 6
}
```

```c++
// Enumerations
enum PaymentStatus {
  Unpaid,
  Pending,
  Completed,
  Failed,
  Declined,
  Canceled,
  Abondoned,
  Settling,
  Refunded
};

enum TableStatus {
  Free,
  Reserved,
  Occupied,
  Other
};

enum SeatType {
  Regular,
  Kid,
  Accessible,
  Other
};

enum AccountStatus {
  Active,
  Closed,
  Canceled,
  Blacklisted
};

enum OrderStatus {
  Received,
  Preparing,
  Complete,
  Canceled,
  None
};

enum ReservationStatus {
  Requested,
  Pending,
  Confirmed,
  CheckedIn,
  Canceled,
  Abondoned
};

// Custom Address data type class
class Address {
  private: 
    int zipCode;
    string address;
    string city;
    string state;
    string country;
};
```

```javascript
// Enumerations
const PaymentStatus = Object.freeze({
  Unpaid,
  Pending,
  Completed,
  Failed,
  Declined,
  Canceled,
  Abondoned,
  Settling,
  Refunded
});

const TableStatus = Object.freeze({
  Free,
  Reserved,
  Occupied,
  Other
});

const SeatType = Object.freeze({
  Regular,
  Kid,
  Accessible,
  Other
});

const AccountStatus = Object.freeze({
  Active,
  Closed,
  Canceled,
  Blacklisted
});

const OrderStatus = Object.freeze({
  Received,
  Preparing,
  Complete,
  Canceled,
  None
});

const ReservationStatus = Object.freeze({
  Requested,
  Pending,
  Confirmed,
  CheckedIn,
  Canceled,
  Abondoned
});

// Custom Addres data type class
class Address {
  #zipCode;
  #address;
  #city;
  #state;
  #country;

  constructor(zipCode, address, city, state, country) {
    this.#zipCode = zipCode;
    this.#address = address;
    this.#city = city;
    this.#state = state;
    this.#country = country;
  }
}
```
### Account and person
The Account class represents a user account that has an ID, address, status, and a password that can be reset and is validated using the resetPassword() function.

The Person class stores the personal details of a person who can either be an Employee or a Customer of the restaurant. The derived class Employee is further extended by the following:

- Receptionist: Has a method named createReservation() to create reservations for customers

- Manager: Has a method named addEmployee() to hire new employees to the restaurant

- Chef: Has a method named prepareOrder() for preparing the order

- Waiter: Has a method named takeOrder() for taking new orders

The derived Customer class has a private member that stores the last visited date of the customer. The definitions of these classes are provided below:

```java
public class Account {
  private String accountId;
  private String password;
  private Address address;
  private AccountStatus status;

  public boolean resetPassword();
}

public abstract class Person {
  private String name;
  private String email;
  private String phone; 
}

public abstract class Employee extends Person {
  private int employeeID;
  private Date dateJoined;
  private Account account;
}

public class Customer extends Person {
  private Date lastVisitedDate;
}

public class Receptionist extends Employee {
  public boolean createReservation();
}

public class Manager extends Employee {
  public boolean addEmployee();
}

public class Chef extends Employee {
  public boolean prepareOrder();
}

public class Waiter extends Employee {
  public boolean takeOrder();
}
```

```c#
class Account {
  private String accountId;
  private String password;
  private Address address;
  private AccountStatus status;

  public bool resetPassword();
}

public abstract class Person {
  private String name;
  private String email;
  private String phone; 
}

public abstract class Employee : Person {
  private int employeeID;
  private Date dateJoined;
  private Account account;
}

class Customer : Person {
  private Date lastVisitedDate;
}

public class Receptionist : Employee {
  public bool createReservation();
}

public class Manager : Employee {
  public bool addEmployee();
}

public class Chef : Employee {
  public bool prepareOrder();
}

public class Waiter : Employee {
  public boolean takeOrder();
}
```

```python
from abc import ABC, abstractmethod
class Account:
  def __init__(self, account_id, password, address, status):
    self.__account_id = account_id
    self.__password = password
    self.__address = address
    self.__status = status # Refers to the AccountStatus enum

  def reset_password(self):
    pass 

class Person(ABC):
  def __init__(self, name, email, phone_number):
    self.__name = name
    self.__email = email
    self.__phone_number = phone_number

class Customer(Person):
  def __init__(self, name, email, phone_number, last_visited_date):
    super().__init__(name, email, phoneNumber)
    self.__last_visited_date = last_visited_date

class Employee(Person):
  def __init__(self, name, email, phone_number, employee_id, joining_date):
    super().__init__(name, email, phoneNumber)
    self.__employee_id = employee_id
    self.__joining_date = joining_date

class Chef(Employee):
  def prepare_order():
    pass

class Waiter(Employee):
  def take_order():
    pass

class Manager(Employee):
  def add_employee():
    pass

class Receptionist(Employee):
  def create_reservation():
    pass
```

```javascript
class Account {
  #accountId;
  #password;
  #address;
  #email;
  #status;

  constructor(accountId, password, address, status) {
    this.#accountId = accountId;
    this.#password = password;
    this.#address = address;
    this.#status = status; // Refers to the AccountStatus enum
  }

  resetPassword();
}

class Person {
    #name;
    #email;
    #phone;

    // Data members
    constructor(name, email, phone) {
        if (this.constructor === Person) {
            throw new Error("Abstract classes can't be instantiated.");
        }
        else {
            this.#name = name;
            this.#email = email;
            this.#phone = phone;
        }
    }
}

class Employee extends Person{
    #employeeID;
    #dateJoined;
    #account;

    // Data members
    constructor(name, email, phone, employeeID, dateJoined, account) {
        if (this.constructor === Employee) {
            throw new Error("Abstract classes can't be instantiated.");
        }
        else {
            this.#employeeID = employeeID;
            this.#dateJoined = dateJoined;
            this.#account = account; 
            super(name, email, phone)
        }
    }
}

class Customer extends Person{
    #lastVisitedDate;

    // Data members
    constructor(name, email, phone, lastVisitedDate) {
        this.#lastVisitedDate = lastVisitedDate;
        super(name, email, phone)
    }
}

class Receptionist extends Employee{
    createReservation();
}

class Manager extends Employee{
    addEmployee();
}

class Chef extends Employee{
    prepareOrder();
}

class Waiter extends Employee{
    takeOrder();
}
```

### Table and table seat
The Table class has a unique ID. It stores the table status, table location, and maximum capacity. Reservations can be added to a table using the addReservation() method. It also maintains a list of all the seats it has, where each TableSeat is identified by a seat number and has a type. The definitions of these classes are provided below:

```java
public class Table {
  private int tableID;
  private TableStatus status;
  private int maxCapacity;
  private int locationIdentifier;
  private List<TableSeat> seats;

  public boolean isTableFree();
  public boolean addReservation();
  public static List<Table> search(int capacity, Date startTime);
}

public class TableSeat {
  private int tableSeatNumber;
  private SeatType type;

  public boolean updateSeatType(SeatType type);
}
```

```c#
class Table {
  private int tableID;
  private TableStatus status;
  private int maxCapacity;
  private int locationIdentifier;
  private List<TableSeat> seats;

  public bool isTableFree();
  public bool addReservation();
  public static List<Table> search(int capacity, Date startTime);
}

class TableSeat {
  private int tableSeatNumber;
  private SeatType type;

  public bool updateSeatType(SeatType type);
}
```

```python
class Table:
  def __init__(self, table_id, status, max_capacity, location_identifier, seats):
    self.__table_id = table_id
    self.__status = status
    self.__max_capacity = max_capacity
    self.__location_identifier = location_identifier
    self.__seats = []

  def is_table_free(self):
    pass
  
  def add_reservation(self):
    pass
  
  def search(self, capacity, start_time):
    pass
    
class TableSeat:
  def __init__(self, table_seat_number, typee):
    self.__table_seat_number = table_seat_number
    self.__typee = typee
  
  def update_seat_type(self, typee):
    pass
```

```c++
class Table {
  private: 
    int tableID;
    TableStatus status;
    int maxCapacity;
    int locationIdentifier;
    list<TableSeat> seats;

  public: 
    bool isTableFree();
    bool addReservation();
    static List<Table> search(int capacity, Date startTime);
};

class TableSeat {
  private: 
    int tableSeatNumber;
    SeatType type;

  public: 
    bool updateSeatType(SeatType type);
};
```

```javascript
class Table {
  #tableID;
  #status;
  #maxCapacity;
  #locationIdentifier;
  #seats;

  constructor(tableID, status, maxCapacity, locationIdentifier, seats) {
    this.#tableID = tableID;
    this.#status = status;
    this.#maxCapacity = maxCapacity;
    this.#locationIdentifier = locationIdentifier;
    this.#seats = seats;
  }
  isTableFree();
  addReservation();
  search(capacity, startTime);
}

class TableSeat {
  #tableSeatNumber;
  #type;

  constructor(tableSeatNumber, type) {
    this.#tableSeatNumber = tableSeatNumber;
    this.#type = type;
  }
  updateSeatType(type);
}
```
### Meal and meal item
The MealItem class is identified by a unique ID and stores and updates the quantity of a menu item. It can be added to a Meal using the addMealItem() method, where the Meal class represents the meal ordered for a specific table. The definitions of these classes are provided below:

```java
public class MealItem {
  private int mealItemID;
  private int quantity;
  private MenuItem menuItem;

  public boolean updateQuantity(int quantity);
}

public class Meal {
  private int mealID;
  private TableSeat seat;
  private List<MenuItem> menuItems;

  public boolean addMealItem(MealItem mealItem);
}
```

```c#
class MealItem {
  private int mealItemID;
  private int quantity;
  private MenuItem menuItem;

  public bool updateQuantity(int quantity);
}

class Meal {
  private int mealID;
  private TableSeat seat;
  private List<MenuItem> menuItems;

  public bool addMealItem(MealItem mealItem);
}
```

```python
class MealItem:
  def __init__(self, meal_item_id, quantity, menu_item):
    self.__meal_item_id = meal_item_id
    self.__quantity = quantity
    self.__menu_item = menu_item

  def update_quantity(self, quantity):
    pass

class Meal:
  def __init__(self, meal_id, seat, menu_items):
    self.__meal_id = meal_id
    self.__seat = seat
    self.__menu_items = []

  def add_meal_item(self, meal_item):
    pass
```

```c++
class MealItem {
  private: 
    int mealItemID;
    int quantity;
    MenuItem menuItem;

  public: 
    bool updateQuantity(int quantity);
};

class Meal {
  private: 
    int mealID;
    TableSeat seat;
    list<MenuItem> menuItems;

  public: 
    bool addMealItem(MealItem mealItem);
};
```

```javascript
class MealItem {
  #mealItemID;
  #quantity;
  #menuItem;

  constructor(mealItemID, quantity, menuItem) {
    this.#mealItemID = mealItemID;
    this.#quantity = quantity;
    this.#menuItem = menuItem;
  }
  
  updateQuantity(quantity);
}

class Meal {
  #mealID;
  #seat;
  #menuItems;

  constructor(mealID, seat, menuItems) {
    this.#mealID = mealID;
    this.#seat = seat;
    this.#menuItems = menuItems;
  }
  
  updateQuantity(quantity);
}
```
### Menu, menu section, and menu item
The Menu class represents the menu of a restaurant. It is identified by a unique ID and maintains a list of MenuSection, where the MenuSection class is the representation of a menu's different sections. A MenuSection has a list of MenuItem in which an item's price can be updated. The definitions of these classes are provided below:
```java
public class Menu {
  private int menuID;
  private String title;
  private String description;
  private double price;
  private List<MenuSection> menuSections;

  public boolean addMenuSection(MenuSection menuSection);
  public boolean print();
}

public class MenuSection {
  private int menuSectionID;
  private String title;
  private String description;
  private List<MenuItem> menuItems;

  public boolean addMenuItem(MenuItem menuItem);
}

public class MenuItem {
  private int menuItemID;
  private String title;
  private String description;
  private double price;

  public boolean updatePrice(double price);
}
```

```c#
class Menu {
  private int menuID;
  private String title;
  private String description;
  private double price;
  private List<MenuSection> menuSections;

  public bool addMenuSection(MenuSection menuSection);
  public bool print();
}

class MenuSection {
  private int menuSectionID;
  private String title;
  private String description;
  private List<MenuItem> menuItems;

  public bool addMenuItem(MenuItem menuItem);
}

public class MenuItem {
  private int menuItemID;
  private String title;
  private String description;
  private double price;

  public bool updatePrice(double price);
}
```

```python
class Menu:
  def __init__(self, menu_id, title, description, price, menu_sections):
    self.__menu_id = menu_id
    self.__title = title
    self.__description = description
    self.__price = price
    self.__menu_sections = []

  def add_menu_section(self, menu_section):
    pass

  def print():
    pass

class MenuSection:
  def __init__(self, menu_section_id, title, description, menu_items):
    self.__menu_section_id = menu_section_id
    self.__title = title
    self.__description = description
    self.__menu_items = []

  def add_menu_item(menu_item):
    pass

class MenuItem:
  def __init__(self, menu_item_id, title, description, price):
    self.__menu_item_id = menu_item_id
    self.__title = title
    self.__description = description
    self.__price = price

  def update_price(price):
    pass
```

```c++
class Menu {
  private: 
    int menuID;
    string title;
    string description;
    double price;
    list<MenuSection> menuSections;

  public: 
    bool addMenuSection(MenuSection menuSection);
    bool print();
};

class MenuSection {
  private: 
    int menuSectionID;
    string title;
    string description;
    list<MenuItem> menuItems;

  public: 
    bool addMenuItem(MenuItem menuItem);
};

class MenuItem {
  private: 
    int menuItemID;
    string title;
    string description;
    double price;

  public: 
    bool updatePrice(double price);
};
```

```javascript
class Menu {
  #menuID;
  #title;
  #description;
  #price;
  #menuSections;

  constructor(menuID, title, description, price, menuSections) {
    this.#menuID = menuID;
    this.#title = title;
    this.#description = description;
    this.#price = price;
    this.#menuSections = menuSections;
  }
  addMenuSection(menuSection);
  print();
}

class MenuSection {
  #menuSectionID;
  #title;
  #description;
  #price;
  #menuSections;

  constructor(menuSectionID, title, description, menuItems) {
    this.#menuSectionID = menuSectionID;
    this.#title = title;
    this.#description = description;
    this.#menuItems = menuItems;
  }
  addMenuItem(menuItem);
}

class MenuItem {
  #menuItemID;
  #title;
  #description;
  #price;

  constructor(menuItemID, title, description, price) {
    this.#menuItemID = menuItemID;
    this.#title = title;
    this.#description = description;
    this.#price = price;
  }
  updatePrice(price);
}
```

### Order, kitchen, and reservation
An Order has a number of meals and is assigned to a waiter and chef for a specific table. Meals can be updated in an Order using the addMeal() and removeMeal() methods.

A Kitchen has a number of chefs where new chefs can be assigned using the assignChef() method.

The Reservation class represents the reservation of a table that stores the reservation time, people count, status, check-in time, and customer information. It also maintains a list of notifications for the customer.

The definitions of these classes are provided below:

```java
public class Order {
  private int OrderID;
  private OrderStatus status;
  private Date creationTime;
  private Meal[] meals;
  private Table table;
  private Waiter waiter;
  private Chef chef;

  public boolean addMeal(Meal meal);
  public boolean removeMeal(Meal meal);
}

public class Kitchen {
  private String name;
  private Chef[] chefs;

  public boolean assignChef();
}

public class Reservation {
  private int reservationID;
  private Date timeOfReservation;
  private int peopleCount;
  private ReservationStatus status;
  private String notes;
  private Date checkInTime;
  private Customer customer;
  private Table[] tables;
  private List<Notification> notifications;
  
  public boolean updatePeopleCount(int count);
}
```

```c#
class Order {
  private int OrderID;
  private OrderStatus status;
  private Date creationTime;
  private Meal[] meals;
  private Table table;
  private Waiter waiter;
  private Chef chef;

  public bool addMeal(Meal meal);
  public bool removeMeal(Meal meal);
}

class Kitchen {
  private String name;
  private Chef[] chefs;

  public bool assignChef();
}

class Reservation {
  private int reservationID;
  private Date timeOfReservation;
  private int peopleCount;
  private ReservationStatus status;
  private String notes;
  private Date checkInTime;
  private Customer customer;
  private Table[] tables;
  private List<Notification> notifications;
  
  public bool updatePeopleCount(int count);
}
```

```python
class Order:
  def __init__(self, order_id, status, __creation_time, meals, table, waiter, chef):
    self.__order_id = order_id
    self.__status = status
    self.__creation_time = creation_time
    self.__meals = []
    self.__table = table
    self.__waiter = waiter
    self.__chef = chef

  def add_meal(self, meal):
    None

  def remove_meal(self, meal):
    None

class Kitchen:
  def __init__(self, name):
    self.__name = name
    self.__chefs = []

  def assign_chef(self, chef):
    None

class Reservation:
  def __init__(self, id, people_count, notes, customer):
    self.__reservation_id = id
    self.__time_of_reservation = datetime.datetime.now()
    self.__people_count = people_count
    self.__status = ReservationStatus.REQUESTED
    self.__notes = notes
    self.__checkin_time = checkin_time
    self.__customer = customer
    self.__tables = []
    self.__notifications = []

  def update_people_count(self, count):
    None
```

```c++
class Order {
  private: 
    int orderID;
    OrderStatus status;
    Date creationTime;
    list<Meal> meals;
    Table table;
    Waiter waiter;
    Chef chef;

  public: 
    bool addMeal(Meal meal);
    bool removeMeal(Meal meal);
}

class Kitchen {
  private: 
    string name;
    list<Chef> chefs;

  public: 
    bool assignChef();
}

class Reservation {
  private: 
    int reservationID;
    Date timeOfReservation;
    int peopleCount;
    ReservationStatus status;
    string notes;
    Date checkInTime;
    Customer customer;
    list<Table> tables;
    list<Notification> notifications;

  public: 
    bool updatePeopleCount(int count);
}
```

```javascript
class Order {
  #orderID;
  #status;
  #creationTime;
  #meals;
  #table;
  #waiter;
  #chef;

  constructor(OrderID, status, creationTime, meals, table, waiter, chef) {
    this.#OrderID = OrderID;
    this.#status = status;
    this.#creationTime = creationTime;
    this.#meals = meals;
    this.#table = table;
    this.#waiter = waiter;
    this.#chef = chef;
  }
  addMeal(meal);
  removeMeal(meal);
}

class Kitchen {
  #name;
  #chefs;

  constructor(name, chefs) {
    this.#name = name;
    this.#chefs = chefs;
  }
  assignChef();
}

class Reservation {
  #reservationID;
  #timeOfReservation;
  #peopleCount;
  #status;
  #notes;
  #checkInTime;
  #customer;
  #tables;
  #notifications;

  constructor(reservationID, timeOfReservation, peopleCount, status, notes, checkInTime, customer, tables, notifications) {
    this.#reservationID = reservationID;
    this.#timeOfReservation = timeOfReservation;
    this.#peopleCount = peopleCount;
    this.#status = status;
    this.#notes = notes;
    this.#checkInTime = checkInTime;
    this.#customer = customer;
    this.#tables = tables;
    this.#notifications = notifications;
  }
  updatePeopleCount(count);
}
```
### Payment and bill
The Payment class is an abstract class with the Check, CreditCard, and Cash classes as its child classes. This takes the PaymentStatus enum to keep track of the payment status. The Bill class represents the bill generated for a customer's order. The definitions of these classes are provided below:

```java
// Payment is an abstract class
public abstract class Payment {
    private int paymentID;
    private Date creationDate;
    private double amount;      
    private PaymentStatus status;

    public abstract void initiateTransaction();
}

public class Check extends Payment {
    private String bankName;
    private String checkNumber;

    public void initiateTransaction() {
        // functionality 
    }
}

public class CreditCard extends Payment {
    private String nameOnCard;
    private int zipcode;

    public void initiateTransaction() {
        // functionality 
    }
}

public class Cash extends Payment {
    private double cashTendered;

    public void initiateTransaction() {
        // functionality 
    }
}

public class Bill {
    private int billId;
    private float amount;
    private float tip;
    private float tax;
    private boolean isPaid;

    public boolean generateBill();
}
```

```c#
// Payment is an abstract class
public abstract class Payment {
    private int paymentID;
    private DateTime creationDate;
    private double amount;      
    private PaymentStatus status;

    public abstract void InitiateTransaction();
}

public class Check : Payment {
    private String bankName;
    private String checkNumber;

    public override void InitiateTransaction() {
        // functionality 
    }
}

public class CreditCard : Payment {
    private String nameOnCard;
    private int zipCode;

    public override void InitiateTransaction() {
        // functionality 
    }
}

public class Cash : Payment {
    private double cashTendered;

    public override void InitiateTransaction() {
        // functionality 
    }
}

class Bill {
    private int billId;
    private float amount;
    private float tip;
    private float tax;
    private bool isPaid;

    public bool generateBill();
}
```

```python
# Payment is an abstract class
from abc import ABC, abstractmethod
class Payment(ABC):
    def __init__(self, payment_id, creation_date, amount, status):
        self.__payment_id = payment_id
        self.__creation_date = creation_date
        self.__amount = amount
        self.status = status

    @abstractmethod
    def initiate_transaction():
        pass

class Check(Payment):
    def __init__(self, payment_id, creation_date, amount, status, bank_name, check_number):
        super().__init__(payment_id, creation_date, amount, status)
        self.__bank_name = bank_name
        self.__check_number = check_number

    def initiate_transaction():
        pass

class CreditCard(Payment):
    def __init__(self, payment_id, creation_date, amount, status, name_on_card, zip_code):
        super().__init__(payment_id, creation_date, amount, status)
        self.__name_on_card = name_on_card
        self.__zip_code = zip_code

    def initiate_transaction():
        pass

class Cash(Payment):
    def __init__(self, payment_id, creation_date, amount, status, cash_tendered):
        super().__init__(payment_id, creation_date, amount, status)
        self.__cash_tendered = cash_tendered

    def initiate_transaction():
        pass

class Bill:
    def __init__(self, bill_id, amount, tip, tax, is_paid):
        self.__bill_id = bill_id
        self.__amount = amount
        self.__tip = tip
        self.__tax = tax
        self.__is_paid = is_paid

    def generate_bill():
        pass
```

```c++
// Payment is an abstract class
class Payment {
    private: 
        int paymentId;
        time_t creationDate;
        double amount;      
        PaymentStatus status;

    public: 
        void initiateTransaction() = 0;
};

class Check : public Payment {
    private: 
        string bankName;
        string checkNumber;

    public: 
        void initiateTransaction() {
            // functionality 
        }
};

class CreditCard : public Payment {
    private: 
        string nameOnCard;
        int zipcode;

    public: 
        void initiateTransaction() {
            // functionality 
        }
};

class Cash : public Payment {
    private: 
        double cashTendered;

    public: 
        void initiateTransaction() {
            // functionality 
        }
};

class Bill {
    private: 
        int billId;
        float amount;
        float tip;
        float tax;
        bool isPaid;

    public: 
        bool generateBill();
};
```

```javascript
// Payment is an abstract class
class Payment {
    #payementId;
    #creationDate;
    #amount;      
    #status;

    constructor(payementId, creationDate, amount, status) {
        if (this.constructor == Payment) {
          throw new Error("Abstract classes can't be instantiated.");
        }
        else {
            this.#payementId = payementId;
            this.#creationDate = creationDate;
            this.#amount = amount;
            this.#status = status;
        }
    }

    initiateTransaction();
}

class Check extends Payment {
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

class CreditCard extends Payment {
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

class Cash extends Payment {
    #cashTendered;

    constructor(cashTendered, creationDate, amount, status) {
        this.#cashTendered = cashTendered;
        super(creationDate,amount,status);
    }

    initiateTransaction() {
        // functionality 
    }
}

class Bill {
    #billId;
    #amount;
    #tip;
    #tax;
    #isPaid;

    constructor(billId, amount, tip, tax, isPaid) {
        this.#billId = billId;
        this.#amount = amount;
        this.#tip = tip;
        this.#tax = tax;
        this.#isPaid = isPaid;
    }
    generateBill();
}
```

### Notification
The Notification class is another abstract class responsible for sending notifications, with the SmsNotification and EmailNotification classes as its child. The implementation of this class is shown below:

```java
// Notification is an abstract class
public abstract class Notification {
    private int notificationId;
    // The Date data type represents and deals with both date and time.
    private Date createdOn;      
    private String content;

    public abstract void send(Person person);
}

class SmsNotification extends Notification {
    private String phone;

    public void sendNotification(Person person) {
        // functionality 
    }
}

class EmailNotification extends Notification {
    private String email;

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

    public abstract void Send(Person person);
}

class SmsNotification : Notification {
    private String phone;
    
    public override void Send(Person person) {
        // functionality 
    }
}

class EmailNotification : Notification {
    private String email;
    
    public override void Send(Person person) {
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
    def send(person):
        pass

class SmsNotification(Notification):
    def __init__(self, phone, notification_id, created_on, content):
        self.__phone = phone
        super().__init__(notification_id, created_on, content)

    # account here refers to an instance of the Account class 
    def send(person):
        # functionality 
        pass

class EmailNotification(Notification):
    def __init__(self, email, notification_id, created_on, content):
        self.__email = email
        super().__init__(notification_id, created_on, content)

    # account here refers to an instance of the Account class 
    def send(person):
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
        void send(Person person) = 0;
};

class SmsNotification : public Notification {
    private:
        string phone;

    public: 
        void send(Person person) {
            // functionality 
        }
};

class EmailNotification : public Notification {
    private:
        string email;

    public: 
        void send(Person person) {
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
    // account here refers to an instance of the Person class 
    send(person);
}

class SmsNotification extends Notification {
    #phone;
    constructor(phone){
        super(notificationId, createdOn, content);
        this.#phone = phone;
    }

    // account here refers to an instance of the Person class 
    sendNotification(person) {
        // functionality 
    }
}

class EmailNotification extends Notification {
    #email;
    constructor(email) {
        super(notificationId, createdOn, content);
        this.#email = email;
    }

    // account here refers to an instance of the Person class 
    sendNotification(person) {
        // functionality 
    }
}
```
### Seating chart, branch, and restaurant
The SeatingChart class stores the seating plan for a Branch of the Restaurant, which can be printed. The Branch of a restaurant has a specific name, address, and kitchen. The Restaurant class maintains a list of all the branches under it. The definitions of these classes are provided below:

```java
public class SeatingChart {
  private int seatingChartID;
  private byte[] seatingChartImage;

  public boolean print();
}

public class Branch {
  private String name;
  private Address location;
  private Kitchen kitchen;
  private Menu menu;

  public Address addseatingChart();
}

public class Restaurant {
  private String name;
  private List<Branch> branches;

  public boolean addBranch(Branch branch);
}
```

```c#
class SeatingChart {
  private int seatingChartID;
  private byte[] seatingChartImage;

  public bool print();
}

class Branch {
  private String name;
  private Address location;
  private Kitchen kitchen;
  private Menu menu;

  public Address addSeatingChart();
}

class Restaurant {
  private String name;
  private List<Branch> branches;

  public bool addBranch(Branch branch);
}
```

```python
class SeatingChart:
  def __init__(self, id):
    self.__seating_chart_id = id
    self.__seating_chart_image = []

  def print(self):
    None

class Branch:
  def __init__(self, name, location, kitchen, menu):
    self.__name = name
    self.__location = location
    self.__kitchen = kitchen
    self.__menu = menu

  def add_seating_chart(self):
    None

class Restaurant:
  def __init__(self, name):
    self.__name = name
    self.__branches = []

  def add_branch(self, branch):
    None
```

```c++
class SeatingChart {
  private: 
    int seatingChartID;
    int[] seatingChartImage;

  public: 
    bool print();
};

class Branch {
  private: 
    string name;
    Address location;
    Kitchen kitchen;
    Menu menu;

  public: 
    Address addSeatingChart();
};

class Restaurant {
  private: 
    string name;
    list<Branch> branches;

  public: 
    bool addBranch(Branch branch);
};
```

```javascript
class SeatingChart {
  #seatingChartId;
  #seatingChartImage;

  constructor(seatingChartId, seatingChartImage) {
    this.#seatingChartId = seatingChartId;
    this.#seatingChartImage = seatingChartImage;
  }
  print();
}

class Branch {
  #name;
  #location;
  #kitchen;
  #menu;

  constructor(name, location, kitchen, menu) {
    this.#name = name;
    this.#location = location;
    this.#kitchen = kitchen;
    this.#menu = menu;
  }
  addSeatingChart();
}

class Restaurant {
  #name;
  #branches;
  #kitchen;

  constructor(name, branches, kitchen) {
    this.#name = name;
    this.#branches = branches;
  }
  addBranch(branch);
}
```
## Wrapping up
We've explored the complete design of the restaurant management system in this chapter. We've looked at how a basic restaurant management system can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
