# Code for the Online Stock Brokerage System
We've reviewed different aspects of the online stock brokerage system and observed the attributes attached to the problem using various UML diagrams. Let’s explore the more practical side of things, where we will work on implementing the online stock brokerage system using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the online stock brokerage system:

- Java

- C#

- Python

- C++

- JavaScript

## Online stock brokerage system classes
In this section, we’ll provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```

### Enumerations and custom data type
First of all, we will define all the enumerations required in the stock brokerage system. According to the class diagram, there are three enumerations used in the system i.e. OrderStatus, TimeEnforcementType and AccountStatus. The code to implement these enumerations and custom data types is as follows:
```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```

```java
// Enumeration
enum OrderStatus {
  OPEN, 
  FILLED, 
  PARTIALLY_FILLED, 
  CANCELED
}

enum TimeEnforcementType {
  GOOD_TILL_CANCELED, 
  FILL_OR_KILL, 
  IMMEDIATE_OR_CANCEL, 
  ON_THE_OPEN,
  ON_THE_CLOSE
}

enum AccountStatus {
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  NONE
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
// Enumeration
enum OrderStatus {
  OPEN, 
  FILLED, 
  PARTIALLY_FILLED, 
  CANCELED
}

enum TimeEnforcementType {
  GOOD_TILL_CANCELED, 
  FILL_OR_KILL, 
  IMMEDIATE_OR_CANCEL, 
  ON_THE_OPEN,
  ON_THE_CLOSE
}

enum AccountStatus {
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  NONE
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

```python
class OrderStatus(Enum):
  OPEN = 1
  FILLED = 2
  PARTIALLY_FILLED = 3
  CANCELED = 4


class TimeEnforcementType(Enum):
  GOOD_TILL_CANCELED = 1
  FILL_OR_KILL = 2
  IMMEDIATE_OR_CANCEL = 3
  ON_THE_OPEN = 4
  ON_THE_CLOSE = 5


class AccountStatus(Enum):
  ACTIVE = 1
  CLOSED = 2
  CANCELED = 3
  BLACKLISTED = 4
  NONE = 5


class Address:
  def __init__(self, street, city, state, zip_code, country):
    self.__street_address = street
    self.__city = city
    self.__state = state
    self.__zip_code = zip_code
    self.__country = country
```

```c++
// Enumeration
enum OrderStatus {
  OPEN, 
  FILLED, 
  PARTIALLY_FILLED, 
  CANCELED
};

enum TimeEnforcementType {
  GOOD_TILL_CANCELED, 
  FILL_OR_KILL, 
  IMMEDIATE_OR_CANCEL, 
  ON_THE_OPEN,
  ON_THE_CLOSE
};

enum AccountStatus {
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  NONE
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
// Enumeration
const OrderStatus = Object.freeze({
  OPEN, 
  FILLED, 
  PARTIALLY_FILLED, 
  CANCELED
});

const TimeEnforcementType = Object.freeze({
  GOOD_TILL_CANCELED, 
  FILL_OR_KILL, 
  IMMEDIATE_OR_CANCEL, 
  ON_THE_OPEN,
  ON_THE_CLOSE
});

const AccountStatus = Object.freeze({
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  NONE
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

### Account
The Account class will be an abstract class, which will have the actors, Admin and Member, as child classes. The definition of these classes is given below:

```java
// Account is an abstract class
public abstract class Account {
  private String id;
  private String password;
  private String name;
  private AccountStatus status;
  private Address address;
  private String email;
  private String phone;

  public abstract boolean resetPassword();
}

public class Member extends Account {
  private double availableFundsForTrading;
  private Date dateOfMembership;
  private HashMap<string, StockPosition> stockPositions;
  private HashMap<Integer, Order> activeOrders;

  public ErrorCode placeSellLimitOrder(string stockId, float quantity, int limitPrice, TimeEnforcementType enforcementType);
  public ErrorCode placeBuyLimitOrder(string stockId, float quantity, int limitPrice, TimeEnforcementType enforcementType);
  public void callbackStockExchange(int orderId, List<OrderPart> orderParts, OrderStatus status);
  public boolean resetPassword(){
    // definition
  }
}

public class Admin extends Account {
  public boolean blockMember();
  public boolean unblockMember();
  public boolean cancelMembership();
  public boolean resetPassword(){
    // definition
  }
}
```

```c#
// Account is an abstract class
public abstract class Account {
  private String id;
  private String password;
  private String name;
  private AccountStatus status;
  private Address address;
  private String email;
  private String phone;

  public abstract bool ResetPassword();
}

class Member : Account {
  private double availableFundsForTrading;
  private DateTime dateOfMembership;
  private HashMap<string, StockPosition> stockPositions;
  private HashMap<int, Order> activeOrders;

  public ErrorCode PlaceSellLimitOrder(string stockId, float quantity, int limitPrice, TimeEnforcementType enforcementType);
  public ErrorCode PlaceBuyLimitOrder(string stockId, float quantity, int limitPrice, TimeEnforcementType enforcementType);
  public void CallbackStockExchange(int orderId, List<OrderPart> orderParts, OrderStatus status);
  public override bool resetPassword(){
    // definition
  }
}

class Admin : Account {
  public bool BlockMember();
  public bool UnblockMember();
  public bool CancelMembership();
  public override bool resetPassword(){
    // definition
  }
}
```

```python
from abc import ABC, abstractmethod

class Account(ABC):
  def __init__(self, id, password, name, address, email, phone):
    self.__id = id
    self.__password = password
    self.__name = name
    self.__address = address
    self.__email = email
    self.__phone = phone
    self.__status = AccountStatus.NONE

  @abstractmethod
  def reset_password(self):
    None

class Member(Account):
  def __init__(self):
    self.__available_funds_for_trading = 0.0
    self.__date_of_membership = datetime.date.today()
    self.__stock_positions = {}
    self.__active_orders = {}

  def place_sell_limit_order(self, stock_id, quantity, limit_price, enforcement_type):
    pass

  def place_buy_limit_order(self, stock_id, quantity, limit_price, enforcement_type):
    pass
    
  def callback_stock_exchange(self, order_id, order_parts, status):
    pass
  
  def reset_password(self):
    # functionality
    
class Admin(Account):
  def block_member():
    pass

  def unblock_member():
    pass

  def cancel_membership():
    pass
  
  def reset_password(self):
    # functionality
```

```c++
// Account is an abstract class
class Account {
  private: 
    string id;
    string password;
    string name;
    AccountStatus status;
    Address address;
    string email;
    string phone;

  public: 
    bool resetPassword() = 0;
};

class Member : public Account {
  private: 
    double availableFundsForTrading;
    time_t dateOfMembership;
    map<string, StockPosition> stockPositions;
    map<int, Order> activeOrders;

  public: 
    ErrorCode placeSellLimitOrder(string stockId, float quantity, int limitPrice, TimeEnforcementType enforcementType);
    ErrorCode placeBuyLimitOrder(string stockId, float quantity, int limitPrice, TimeEnforcementType enforcementType);
    void callbackStockExchange(int orderId, vector<OrderPart> orderParts, OrderStatus status);
    bool resetPassword(){
      // definition
    }
};

class Admin : public Account {
  public: 
    bool blockMember();
    bool unblockMember();
    bool cancelMembership();
};
```

```javascript
// Account is an abstract class
class Account {
  #id;
  #password;
  #name;
  #status;
  #address;
  #email;
  #phone;

  constructor(id, password, name, status, address, email, phone) {
        if (this.constructor == Account) {
            throw new Error("Abstract classes can't be instantiated.");
        }
        else {
            this.#id = id;
            this.#password = password;
            this.#name = name;
            this.#status = status;
            this.#address = address;
            this.#email = email;
            this.#phone = phone;
        }
  }
  resetPassword();
}

class Member extends Account {
  #availableFundsForTrading;
  #dateOfMembership;
  #stockPositions;
  #activeOrders;

  placeSellLimitOrder(stockId, quantity, limitPrice, enforcementType);
  placeBuyLimitOrder(stockId, quantity, limitPrice, enforcementType);
  callbackStockExchange(orderId, orderParts, status);
}

class Admin extends Account {
  blockMember();
  unblockMember();
  cancelMembership();
}
```

### Watchlist and stock
A Watchlist class is a list of stocks that an investor keeps an eye on, to profit from price drops. The Stock class is an equity or a security that represents a portion of the issuing company's ownership.

```java
public class Watchlist {
  private String name;
  private List<Stock> stocks;

  public List<Stock> getStocks();
}

public class Stock {
  private String symbol;
  private double price;
}
```

```c#
class Watchlist {
  private String name;
  private List<Stock> stocks;

  public List<Stock> GetStocks();
}

class Stock {
  private String symbol;
  private double price;
}
```

```python
class Watchlist:
  def __init__(self, name, stocks):
    self.__name = name
    self.__stocks = stocks

  def get_stocks():
    pass

class Stock:
  def __init__(self, symbol, price):
    self.__symbol = symbol
    self.__price = price
```

```c++
class Watchlist {
  private: 
    string name;
    vector<Stock> stocks;

  public:
    vector<Stock> getStocks();
};

class Stock {
  private: 
    string symbol;
    double price;
};
```

```javascript
class Watchlist {
  #name;
  #stocks;

  constructor(name, stocks) {
    this.#name = name;
    this.#stocks = stocks;
  }
  getStocks();
}

class Stock {
  #symbol;
  #price;
}
```

### Search and stock inventory
The StockInventory class implements the Search interface.

```java
public interface Search {
    // Interface method (does not have a body)
    public Stock searchSymbol(String symbol);
}

public class StockInventory implements Search {
  private String inventoryName;
  private Date lastUpdate;
  public Stock searchSymbol(String symbol) {
      // definition
  }
}
```

```c#
public interface ISearch {
    // Interface method (does not have a body)
    public Stock SearchSymbol(String symbol);
}

public class StockInventory : ISearch {
  private String inventoryName;
  private DateTime lastUpdate;
  public Stock SearchSymbol(String symbol) {
      // definition
  }
}
```

```python
from abc import ABC, abstractmethod

class Search(ABC):
  def search_symbol(self, symbol):
    None

class StockInventory(Search):
  def __init__(self, inventory_name, last_update):
    self.__inventory_name = inventory_name
    self.__last_update = last_update

  def search_symbol(self, symbol):
    pass
```

```c++
class Search {
    public: 
      Stock searchSymbol(string symbol) = 0;
}

public class StockInventory : public Search {
  private: 
    string inventoryName;
    time_t lastUpdate;
  public: 
    Stock searchSymbol(string symbol) {
      // definition
    }
}
```

```javascript
class Search {
    searchSymbol(symbol);
}

class StockInventory extends Search {
    #inventoryName;
    #lastUpdate;

    constructor(inventoryName, lastUpdate){
        this.inventoryName = inventoryName;
        this.lastUpdate = lastUpdate;
    }
    searchSymbol(symbol);
}
```


### Stock position and stock lot
All the stocks that the user owns will be included in the StockPosition class. A member may purchase various lots of the same stock at various dates. The StockLot class will represent these particular lots.
```java
public class StockPosition {
  private String symbol;
  private double quantity;
}

public class StockLot {
  private String iotNumber;
  private Order buyingOrder;

  public double getBuyingPrice();
}
```

```c#
class StockPosition {
  private String symbol;
  private double quantity;
}

class StockLot {
  private String iotNumber;
  private Order buyingOrder;

  public double GetBuyingPrice();
}
```

```python
class StockPosition:
  def __init__(self, symbol, quantity):
    self.__symbol = symbol
    self.__quantity = quantity

class StockLot:
  def __init__(self, iot_number, buying_order):
    self.__iot_number = iot_number
    self.__buying_order = buying_order

  def get_buying_price():
    pass
```

```c++
class StockPosition {
  private: 
    string symbol;
    double quantity;
};

class StockLot {
  private: 
    string iotNumber;
    Order buyingOrder;

  public: 
    double getBuyingPrice();
};
```

```javascript
class StockPosition {
  #symbol;
  #quantity;

  constructor(symbol, quantity) {
    this.#symbol = symbol;
    this.#quantity = quantity;
  }
}

class StockLot {
  #iotNumber;
  #buyingOrder;

  constructor(iotNumber, buyingOrder) {
    this.#iotNumber = iotNumber;
    this.#buyingOrder = buyingOrder;
  }
  getBuyingPrice();
}
```

### Order
Members can place stock trading orders when they want to sell or acquire StockPosition.

```java
public class OrderPart {
  private double price;
  private double quantity;
  private Date executedAt;
}

// Order is an abstract class
public abstract class Order {
  private String orderNumber;
  public boolean isBuyOrder;
  private OrderStatus status;
  private TimeEnforcementType timeEnforcement;
  private Date creationTime;
  private HashMap<int, OrderPart> parts;

  public void setStatus(OrderStatus status);
  public boolean saveInDatabase();
  public void addOrderParts(OrderParts parts);
}

public class LimitOrder extends Order {
}

public class StopLimitOrder extends Order {
}

public class StopLossOrder extends Order {
}

public class MarketOrder extends Order {
}
```

```c#
class OrderPart {
  private double price;
  private double quantity;
  private DateTime executedAt;
}

// Order is an abstract class
public abstract class Order {
  private String orderNumber;
  public bool isBuyOrder;
  private OrderStatus status;
  private TimeEnforcementType timeEnforcement;
  private DateTime creationTime;
  private HashMap<int, OrderPart> parts;

  public void SetStatus(OrderStatus status);
  public bool SaveInDatabase();
  public void AddOrderParts(OrderParts parts);
}

class LimitOrder : Order {
}

class StopLimitOrder : Order {
}

class StopLossOrder : Order {
}

class MarketOrder : Order {
}
```

```python
class OrderPart:
  def __init__(self, price, quantity, executed_at):
    self.__price = price
    self.__quantity = quantity
    self.__executed_at = executed_at

from abc import ABC, abstractmethod

class Order(ABC):
  def __init__(self, order_number, is_buy_order, status, time_enforcement, creation_time):
    self.__order_number = order_number
    self.__is_buy_order = is_buy_order
    self.__status = status
    self.__time_enforcement = time_enforcement
    self.__creation_time = creation_time
    self.__parts = {}

  def set_status(OrderStatus status):
    pass
  
  def save_in_database():
    pass
  
  def add_order_parts(OrderParts parts):
    pass

class LimitOrder(Account):
  def __init__(self, order_number, is_buy_order, status, time_enforcement, creation_time):
    super().__init__(order_number, is_buy_order, status, time_enforcement, creation_time)

class StopLimitOrder(Account):
  def __init__(self, order_number, is_buy_order, status, time_enforcement, creation_time):
    super().__init__(order_number, is_buy_order, status, time_enforcement, creation_time)

class StopLossOrder(Account):
  def __init__(self, order_number, is_buy_order, status, time_enforcement, creation_time):
    super().__init__(order_number, is_buy_order, status, time_enforcement, creation_time)

class MarketOrder(Account):
  def __init__(self, order_number, is_buy_order, status, time_enforcement, creation_time):
    super().__init__(order_number, is_buy_order, status, time_enforcement, creation_time)
```

```c++
class OrderPart {
  private double price;
  private double quantity;
  private time_t executedAt;
};

// Order is an abstract class
class Order {
  private: 
    string orderNumber;
    bool isBuyOrder;
    OrderStatus status;
    TimeEnforcementType timeEnforcement;
    time_t creationTime;
    HashMap<int, OrderPart> parts;

  public: 
    void setStatus(OrderStatus status);
    bool saveInDatabase();
    void addOrderParts(OrderParts parts);
};

class LimitOrder : public Order {
};

class StopLimitOrder : public Order {
};

class StopLossOrder : public Order {
};

class MarketOrder : public Order {
};
```

```javascript
class OrderPart {
  #price;
  #quantity;
  #executedAt;

  constructor(price, quantity, executedAt) {
    this.#price = price;
    this.#quantity = quantity;
    this.#executedAt = executedAt;
  }
}

// Order is an abstract class
class Order {
  #orderNumber;
  #isBuyOrder;
  #status;
  #timeEnforcement;
  #creationTime;
  #parts;

  constructor(orderNumber, isBuyOrder, status, timeEnforcement, creationTime, parts) {
    if (this.constructor == Account) {
      throw new Error("Abstract classes can't be instantiated.");
    }
    else {
      this.#orderNumber = orderNumber;
      this.#isBuyOrder = isBuyOrder;
      this.#status = status;
      this.#timeEnforcement = timeEnforcement;
      this.#creationTime = creationTime;
      this.#parts = parts;
    }
  }
  setStatus(status);
  saveInDatabase();
  addOrderParts(parts);
}

class LimitOrder extends Order {
}

class StopLimitOrder extends Order {
}

class StopLossOrder extends Order {
}

class MarketOrder extends Order {
}
```


### Transfer money
Members should be able to deposit and withdraw money either via Check, Wire, or ElectronicBank transfer.

```java
// TransferMoney is an abstract class
public abstract class TransferMoney {
  private int id;
  private Date creationDate;
  public int fromAccount;
  private int toAccount;

  public abstract boolean initiateTransaction();
}

public class ElectronicBank extends TransferMoney {
  private String bankName;
  
  public boolean initiateTransaction(){
    // definition
  }
}

public class Wire extends TransferMoney {
  private int wire;

  public boolean initiateTransaction(){
    // definition
  }
}

public class Check extends TransferMoney {
  private String checkNumber;

  public boolean initiateTransaction(){
    // definition
  }
}

public class DepositMoney {
  private int transactionId;

  public boolean initiateTransaction(){
    // definition
  }
}

public class WithdrawMoney {
  private int transactionId;
}
```

```c#
// TransferMoney is an abstract class
public abstract class TransferMoney {
  private int id;
  private DateTime creationDate;
  public int fromAccount;
  private int toAccount;

  public abstract bool InitiateTransaction();
}

class ElectronicBank : TransferMoney {
  private String bankName;

  public override bool initiateTransaction(){
    // definition
  }
}

class Wire : TransferMoney {
  private int wire;

  public override bool initiateTransaction(){
    // definition
  }
}

class Check : TransferMoney {
  private String checkNumber;

  public override bool initiateTransaction(){
    // definition
  }
}

class DepositMoney {
  private int transactionId;

  public override bool initiateTransaction(){
    // definition
  }
}

class WithdrawMoney {
  private int transactionId;
}
```

```python
from abc import ABC, abstractmethod

class TransferMoney(ABC):
  def __init__(self, id, creation_date, from_account, to_account):
    self.__id = id
    self.__creation_date = creation_date
    self.__from_account = from_account
    self.__to_account = to_account

  @abstractmethod
  def initiate_transaction():
    pass
  
class ElectronicBank(TransferMoney):
  def __init__(self, id, creation_date, from_account, to_account, bank_name):
    super().__init__(id, creation_date, from_account, to_account)
    self.__bank_name = bank_name

  def initiate_transaction():
    # functionality

class Wire(TransferMoney):
  def __init__(self, id, creation_date, from_account, to_account, wire):
    super().__init__(id, creation_date, from_account, to_account)
    self.__wire = wire

  def initiate_transaction():
    # functionality

class Check(TransferMoney):
  def __init__(self, id, creation_date, from_account, to_account, check_number):
    super().__init__(id, creation_date, from_account, to_account)
    self.__check_number = check_number

  def initiate_transaction():
    # functionality

class DepositMonet:
  def __init__(self, transaction_id):
    self.__transaction_id = transaction_id

class WithdrawMoney:
  def __init__(self, transaction_id):
    self.__transaction_id = transaction_id
```

```c++
// TransferMoney is an abstract class
class TransferMoney {
  private:
    int id; 
    time_t creationDate;
    int fromAccount;
    int toAccount;

  public: 
    bool initiateTransaction();
};

class ElectronicBank : public TransferMoney {
  private: 
    string bankName;
};

class Wire : public TransferMoney {
  private: 
    int wire;
};

class Check : public TransferMoney {
  private 
    string checkNumber;
};

class DepositMoney {
  private:
    int transactionId;
};

class WithdrawMoney {
  private:
    int transactionId;
};
```

```javascript
// TransferMoney is an abstract class
class TransferMoney {
  #id
  #creationDate;
  #fromAccount;
  #toAccount;

  constructor(id, creationDate, fromAccount, toAccount) {
    if (this.constructor == Account) {
        throw new Error("Abstract classes can't be instantiated.");
    }
    else {
        this.#id = id;
        this.#creationDate = creationDate;
        this.#fromAccount = fromAccount;
        this.#toAccount = toAccount;
    }
  }
  initiateTransaction();
}

class ElectronicBank extends TransferMoney {
  #bankName;

  constructor(bankName) {
    this.#bankName = bankName;
  }
  initiateTransaction();
}

class Wire extends TransferMoney {
  #wire;

  constructor(wire) {
    this.#wire = wire;
  }
  initiateTransaction();
}

class Check extends TransferMoney {
  #checkNumber;

  constructor(checkNumber) {
    this.#checkNumber = checkNumber;
  }
}

class DepositMoney {
  #transactionId;

  constructor(transactionId) {
    this.#transactionId = transactionId;
  }
}

class WithdrawMoney {
  #transactionId;

  constructor(transactionId) {
    this.#transactionId = transactionId;
  }
}
```

### Notification
The Notification class is another abstract class responsible for sending notifications to the users, with the SmsNotification and EmailNotification classes as its child. The implementation of this class is shown below:
```java
public abstract class Notification {
    private String notificationId;
    private Date creationDate;
    private String content;

    public abstract boolean sendNotification();
}

public class SmsNotification extends Notification {
    private int phoneNumber;

    public boolean sendNotification(){
        // definition
    }
}

public class EmailNotification extends Notification {
    private String email;

    public boolean sendNotification(){
        // definition
    }
}
```

```c#
public abstract class Notification {
    private String notificationId;
    private DateTime creationDate;
    private String content;

    public abstract bool SendNotification();
}

class SmsNotification : Notification {
    private int phoneNumber;

    public override bool sendNotification(){
        // definition
    }
}

class EmailNotification : Notification {
    private String email;

    public override bool sendNotification(){
        // definition
    }
}
```

```python
from abc import ABC, abstractmethod

class Notification(ABC)):
  def __init__(self, notification_id, creation_date, content):
    self.__notification_id = notification_id
    self.__creation_date = creation_date
    self.__content = content

  @abstractmethod
  def send_notification(self):
    None

class SmsNotification(Notification):
  def __init__(self, notification_id, creation_date, content, phone_number):
    super().__init__(notification_id, creation_date, content)
    self.__phone_number = phone_number

  def send_notification(self):
    # functionality

class EmailNotification(Notification):
  def __init__(self, notification_id, creation_date, content, email):
    super().__init__(notification_id, creation_date, content)
    self.__email = email

  def send_notification(self):
    # functionality
```

```c++
class Notification {
    private: 
        string notificationId;
        time_t creationDate;
        string content;

    public:
        bool sendNotification() = 0;
};

class SmsNotification : public Notification {
    private int phoneNumber;

    public bool sendNotification(){
        // definition
    }
};

class EmailNotification : public Notification {
    private string email;

    public bool sendNotification(){
        // definition
    }
};
```

```javascript
class Notification {
    #notificationId;
    #creationDate;
    #content;
    
    constructor(notificationId, creationDate, content) {
      if (this.constructor == Account) {
        throw new Error("Abstract classes can't be instantiated.");
      }
      else {
        this.#notificationId = notificationId;
        this.#creationDate = creationDate;
        this.#content = content;
      }
    }

    sendNotification();
}

class SmsNotification extends Notification {
    #phoneNumber;
    constructor(phoneNumber) {
    this.#phoneNumber = phoneNumber;
  }
  sendNotification();
}

class EmailNotification extends Notification {
    #email;
    constructor(email) {
    this.#email = email;
  }
  sendNotification();
}
```

### Stock exchange
The stock brokerage system will get all the stocks and their current pricing from the StockExchange class.

```java
public class StockExchange {
  // The StockExchange is a singleton class that ensures it will have only one active instance at a time
  private static StockExchange instance = null;

  // Created a private constructor to add a restriction (due to Singleton)
  private StockExchange() {}

  // Created a static method to access the singleton instance of StockExchange
  public static StockExchange getInstance()
  {
    if(instance == null) {
      instance = new StockExchange();
    }
    return instance;
  }

  public boolean placeOrder(Order order);
}
```

```c#
public class StockExchange {
  // The StockExchange is a singleton class that ensures it will have only one active instance at a time
  private static StockExchange instance = null;

  // Created a private constructor to add a restriction (due to Singleton)
  private StockExchange() {}

  // Created a static method to access the singleton instance of StockExchange
  public static StockExchange GetInstance()
  {
    if(instance == null) {
      instance = new StockExchange();
    }
    return instance;
  }

  public bool PlaceOrder(Order order);
}
```

```python
# The StockExchange is a singleton class that ensures it will have only one active instance at a time
class __StockExchange(object):
  __instances = None
  
  def __new__(cls):
    if cls.__instances is None:
        cls.__instances = super(__StockExchange, cls).__new__(cls)
    return cls.__instances

class StockExchange(metaclass=__StockExchange):
  def __init__(self,):
    
  def place_order(Order order):
    pass
```

```c++
public class StockExchange {
  // The StockExchange is a singleton class that ensures it will have only one active instance at a time
  private: 
    static StockExchange instance = NULL;

  // Created a private constructor to add a restriction (due to Singleton)
    StockExchange() {}

  // Created a static method to access the singleton instance of StockExchange
  public: 
    static StockExchange getInstance()
      {
        if(instance == NULL) {
          instance = new StockExchange();
        }
        return instance;
      }

    bool placeOrder(Order order);
};
```

```javascript
class StockExchange {

  constructor() {
    if (StockExchange._instance) {
      throw new Error("Singleton classes can't be instantiated more than once.")
    }
    // The StockExchange is a singleton class that ensures it will have only one active instance at a time
    StockExchange._instance = this;
    }
    // Created a static method to access the singleton instance of StockExchange
    static getInstance() {
        if(!StockExchange._instance){
            return new StockExchange();
        }
        return StockExchange._instance;
    }
  
  placeOrder(order);
}
```


## Wrapping up
We've explored the complete design of an online stock brokerage system in this chapter. We've looked at how a basic online stock brokerage system can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
