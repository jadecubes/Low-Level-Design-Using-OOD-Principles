# Code for the Amazon Online Shopping System
We’ve gone over the different aspects of Amazon and observed the attributes attached to the problem using various UML diagrams. Let’s explore the more practical side of things, where we’ll implement Amazon using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in Amazon:

- Java

- C#

- Python

- C++

- JavaScript

## Amazon classes
In this section, we’ll provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```

### Constants
The following code provides the definition of the various enums and custom data types being used in the Amazon design:
```
Note: JavaScript does not support enumerations so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```

```java
public class Address {
  private int zipCode;
  private String address;
  private String city;
  private String state;
  private String country;
}

enum OrderStatus {
  UNSHIPPED, 
  PENDING, 
  SHIPPED, 
  CONFIRMED, 
  CANCELED, 
  REFUNDED
}

enum AccountStatus {
  ACTIVE, 
  INACTIVE, 
  BLOCKED
}

enum ShipmentStatus {
  PENDING, 
  SHIPPED, 
  DELIVERED, 
  ON_HOLD
}

enum PaymentStatus {
  CONFIRMED, 
  DECLINED, 
  PENDING, 
  REFUNDED
}
```

```c#
class Address {
  private int zipCode;
  private string address;
  private string city;
  private string state;
  private string country;
}

enum OrderStatus {
  UNSHIPPED, 
  PENDING, 
  SHIPPED, 
  CONFIRMED, 
  CANCELED, 
  REFUNDED
}

enum AccountStatus {
  ACTIVE, 
  INACTIVE, 
  BLOCKED
}

enum ShipmentStatus {
  PENDING, 
  SHIPPED, 
  DELIVERED, 
  ON_HOLD
}

enum PaymentStatus {
  CONFIRMED, 
  DECLINED, 
  PENDING, 
  REFUNDED
}
```

```python
class Address:
  def __init__(self, zip_code, address, city, state, country):
    self.__zip_code = zip_code
    self.__address = address
    self.__city = city
    self.__state = state
    self.__country = country

class OrderStatus(enum.Enum):
  UNSHIPPED = 1 
  PENDING = 2
  SHIPPED = 3
  CONFIRMED = 4
  CANCELED = 5
  REFUNDED = 6

class AccountStatus(enum.Enum):
  ACTIVE = 1 
  INACTIVE = 2
  BLOCKED = 3

class ShipmentStatus(enum.Enum):
  PENDING = 1 
  SHIPPED = 2
  DELIVERED = 3
  ON_HOLD = 4

class PaymentStatus(enum.Enum):
  CONFIRMED = 1 
  DECLINED = 2
  PENDING = 3
  REFUNDED = 4
```

```c++
class Address {
  private:
    int zipCode;
    string address;
    string city;
    string state;
    string country;
}

enum OrderStatus {
  UNSHIPPED, 
  PENDING, 
  SHIPPED, 
  CONFIRMED, 
  CANCELED, 
  REFUNDED
}

enum AccountStatus {
  ACTIVE, 
  INACTIVE, 
  BLOCKED
}

enum ShipmentStatus {
  PENDING, 
  SHIPPED, 
  DELIVERED, 
  ON_HOLD
}

enum PaymentStatus {
  CONFIRMED, 
  DECLINED, 
  PENDING, 
  REFUNDED
}
```

```javascript
class Address {
  #zipCode
  #address
  #city
  #state
  #country

  constructor(zipCode, address, city, state, country) {
    this.#zipCode = zipCode;
    this.#address = address;
    this.#city = city;
    this.#state = state;
    this.#country = country;
  }
}

const OrderStatus = Object.freeze({
  UNSHIPPED, 
  PENDING, 
  SHIPPED, 
  CONFIRMED, 
  CANCELED, 
  REFUNDED
});

const AccountStatus = Object.freeze({
  ACTIVE, 
  INACTIVE, 
  BLOCKED
});

const ShipmentStatus = Object.freeze({
  PENDING, 
  SHIPPED, 
  DELIVERED, 
  ON_HOLD
});

const PaymentStatus = Object.freeze({
  CONFIRMED, 
  DECLINED, 
  PENDING, 
  REFUNDED
});
```

### Account
The Account class refers to an account of a customer on Amazon and contains the personal details of a customer, such as their name, shipping address, credit card information, etc. It also provides authenticated users and admins with the functionality to add products, product reviews, and reset passwords. The definition of this class is given below:

```java
public class Account {
  private String userName;
  private String password;
  private String name;
  private List<Address> shippingAddress;
  private AccountStatus status;
  private String email;
  private String phone;

  private List<CreditCard> creditCards;
  private List<ElectronicBankTransfer> bankAccounts;

  public Address getShippingAddress();
  public boolean addProduct(Product product);
  public boolean addProductReview(ProductReview review, Product product);
  public boolean deleteProduct(Product product);
  public boolean deleteProductReview(ProductReview review, Product product);
  public boolean resetPassword();
}
```

```c#
class Account {
  private string userName;
  private string password;
  private string name;
  private List<Address> shippingAddress;
  private AccountStatus status;
  private string email;
  private string phone;

  private List<CreditCard> creditCards;
  private List<ElectronicBankTransfer> bankAccounts;

  public Address GetShippingAddress();
  public bool AddProduct(Product product);
  public bool AddProductReview(ProductReview review, Product product);
  public bool DeleteProduct(Product product);
  public bool DeleteProductReview(ProductReview review, Product product);
  public bool ResetPassword();
}
```

```python
class Account:
  def __init__(self, user_name, password, name, shipping_address, status, email, phone, credit_cards, bank_accounts):
    self.__user_name = user_name
    self.__password = password
    self.__name = name
    self.__shipping_address = shipping_address # List of shipping addresses
    self.__status = status # Refers to the AccountStatus enum
    self.__email = email
    self.__phone = phone
    self.__credit_cards = credit_cards # List of credit cards
    self.__bank_accounts = bank_accounts # List of bank accounts

  # Returns list of shipping addresses
  def get_shipping_address(self):
    pass

  # product here refers to an instance of the Product class
  def add_product(self, product):
    pass 

  # review here refers to an instance of the ProductReview class
  # product here refers to an instance of the Product class
  def add_product_review(self, review, product):
    pass  

  # product here refers to an instance of the Product class
  def delete_product(self, product):
    pass 

  # review here refers to an instance of the ProductReview class
  # product here refers to an instance of the Product class
  def delete_product_review(self, review, product):
    pass  

  def reset_password(self):
    pass
```

```c++
class Account {
  private:
    string userName;
    string password;
    string name;
    vector<Address> shippingAddress;
    AccountStatus status;
    string email;
    string phone;

    vector<CreditCard> creditCards;
    vector<ElectronicBankTransfer> bankAccounts;

  public: 
    Address getShippingAddress();
    bool addProduct(Product product);
    bool addProductReview(ProductReview review, Product product);
    bool deleteProduct(Product product);
    bool deleteProductReview(ProductReview review, Product product);
    bool resetPassword();
}
```

```javascript
class Account {
  #userName;
  #password;
  #name;
  #shippingAddress;
  #status;
  #email;
  #phone;
  #creditCards;
  #bankAccounts;

  constructor(userName, password, name, shippingAddress, status, email, phone, creditCards, bankAccounts) {
    this.#userName = userName;
    this.#password = password;
    this.#name = name;
    this.#shippingAddress = shippingAddress; // List of shipping addresses
    this.#status = status; // Refers to the AccountStatus enum
    this.#email = email;
    this.#phone = phone;
    this.#creditCards = creditCards; // List of credit cards
    this.#bankAccounts = bankAccounts; // List of bank accounts
  }
  
  // Returns list of shipping addresses
  getShippingAddress();
  // product here refers to an instance of the Product class
  addProduct(product);
  // review here refers to an instance of the ProductReview class
  // product here refers to an instance of the Product class
  addProductReview(review, product);
  // product here refers to an instance of the Product class
  deleteProduct(product);
  // review here refers to an instance of the ProductReview class
  // product here refers to an instance of the Product class
  deleteProductReview(review, product);
  resetPassword();
}
```
### Admin
The Admin class refers to a person from the administration of Amazon that can block users, and add, modify, or delete product categories. The definition of this class is provided below:

```java
public class Admin {
  private Account account;
  public boolean blockUser(Account account);
  public boolean addNewProductCategory(ProductCategory category);
  public boolean modifyProductCategory(ProductCategory category);
  public boolean deleteProductCategory(ProductCategory category);
}
```

```c#
class Admin {
  private Account account;
  public bool BlockUser(Account account);
  public bool AddNewProductCategory(ProductCategory category);
  public bool ModifyProductCategory(ProductCategory category);
  public bool DeleteProductCategory(ProductCategory category);
}
```

```python
class Admin:
  def __init__(self, account):
    self.__account = account # Refers to an instance of the Account class

  # account here refers to an instance of the Account class
  def block_user(self, account):
    pass

  # category here refers to an instance of the ProductCategory class
  def add_new_product_category(self, category):
    pass

  # category here refers to an instance of the ProductCategory class
  def modify_product_category(self, category):
    pass

  # category here refers to an instance of the ProductCategory class
  def delete_product_category(self, category):
    pass
```

```c++
class Admin {
  private:
    Account account;
  public:
    bool blockUser(Account account);
    bool addNewProductCategory(ProductCategory category);
    bool modifyProductCategory(ProductCategory category);
    bool deleteProductCategory(ProductCategory category);
}
```

```javascript
class Admin {
  #account

  constructor(account) {
    this.#account = account // Refers to an instance of the Account class
  }

  // account here refers to an instance of the Account class
  blockUser(account);
  // category here refers to an instance of the ProductCategory class
  addNewProductCategory(category);
  // category here refers to an instance of the ProductCategory class
  modifyProductCategory(category);
  // category here refers to an instance of the ProductCategory class
  deleteProductCategory(category);
}
```

### Customer
The Customer class is an abstract class that has the AuthenticatedUser and Guest classes derived from it. The classes are defined below:

```java
// Customer is an abstract class
public abstract class Customer {
  private ShoppingCart cart;
  public abstract ShoppingCart getShoppingCart();
}

public class Guest extends Customer {
  public boolean registerAccount();

  public ShoppingCart getShoppingCart() {
    // functionality
  }
}

public class AuthenticatedUser extends Customer {
  private Account account;
  private Order order;
  public OrderStatus placeOrder(Order order);

  public ShoppingCart getShoppingCart() {
    // functionality
  }
}
```

```c#
// Customer is an abstract class
public abstract class Customer {
  private ShoppingCart cart;
  public abstract ShoppingCart getShoppingCart();
}

class Guest : Customer {
  public bool registerAccount();

  public override ShoppingCart getShoppingCart() {
    // functionality
  }
}

class AuthenticatedUser : Customer {
  private Account account;
  private Order order;
  public OrderStatus placeOrder(Order order);

  public override ShoppingCart getShoppingCart() {
    // functionality
  }
}
```

```python
# Customer is an abstract class
from abc import ABC, abstractmethod

class Customer(ABC):
  def __init__(self, cart, order):
    self.__cart = cart # Refers to an instance of the ShoppingCart class

  # Returns the ShoppingCart class
  @abstractmethod
  def get_shopping_cart(self):
    pass

class Guest(Customer):
  def __init__(self, cart, order):
    super().__init__(cart, order)

  def register_account(self):
    pass

  # Returns the ShoppingCart class
  def get_shopping_cart(self):
    # Add functionality
    pass

class AuthenticatedUser(Customer):
  def __init__(self, account, cart, order):
    self.__account = account # Refers to an instance of the Account class
    self.__order = order # Refers to an instance of the Order class
    super().__init__(cart, order)

  # order here refers to an instance of the Order class
  # Returns a value from the OrderStatus enum
  def place_order(self, order):
    pass

  # Returns the ShopppingCart class
  def get_shopping_cart(self):
    # Add functionality
    pass
```

```c++
// Customer is an abstract class
public abstract class Customer {
  private:
    ShoppingCart cart;

  public: 
    virtual ShoppingCart getShoppingCart() = 0;
}

class Guest : public Customer {
  public:
    bool registerAccount();
    ShoppingCart getShoppingCart() {
      // functionality
    }
}

class AuthenticatedUser : public Customer {
  private:
    Account account;
    Order order;

  public: 
    OrderStatus placeOrder(Order order);
    ShoppingCart getShoppingCart() {
      // functionality
    }
}
```

```javascript
// Customer is an abstract class
class Customer {
  #cart;
  constructor(cart) {
    if (this.constructor == Customer) {
      throw new Error("Abstract classes can't be instantiated.");
    }
    else {
      this.#cart = cart; // Refers to an instance of the ShopppingCart class
    }
  }
  // Returns the ShopppingCart class
  getShoppingCart();
}

class Guest extends Customer {
  constructor(cart) {
    super(cart);
  }
  registerAccount();
  // Returns the ShopppingCart class
  getShoppingCart() {
    // functionality
  }
}

class AuthenticatedUser extends Customer {
  #account;
  #order;

  constructor(cart, order, account) {
    this.#account = account; // Refers to an instance of the Account class
    this.#order = order; // Refers to an instance of the Order class
    super(cart, order);
  }

  // order here refers to an instance of the Order class
  // Returns a value from the OrderStatus enum
  placeOrder(order);
  // Returns the ShopppingCart class
  getShoppingCart() {
    // functionality
  }
}
```

### Product, product category, and product review
The following code defines the classes relating to a particular product:

```java
public class Product {
  private String productId;
  private String name;
  private String description;
  private byte[] image;
  private double price;
  private ProductCategory category;
  private List<ProductReview> reviews;
  private int availableItemCount;
  private Account account;

  public int getAvailableCount();
  public int updateAvailableCount();
  public boolean updatePrice(double newPrice);
}

public class ProductCategory {
  private String name;
  private String description;
  private List<Product> products;
}

public class ProductReview {
  private int rating;
  private String review;
  private byte[] image;
  private AuthenticatedUser user;
}
```

```c#
class Product {
  private string productId;
  private string name;
  private string description;
  private sbyte[] image;
  private double price;
  private ProductCategory category;
  private List<ProductReview> reviews;
  private int availableItemCount;
  private Account account;

  public int GetAvailableCount();
  public int UpdateAvailableCount();
  public bool UpdatePrice(double newPrice);
}

public class ProductCategory {
  private string name;
  private string description;
  private List<Product> products;
}

public class ProductReview {
  private int rating;
  private string review;
  private sbyte[] image;
  private AuthenticatedUser user;
}
```

```python
class Product:
  def __init__(self, product_id, name, description, image, price, category, reviews, available_item_count, account):
    self.__product_id = product_id
    self.__name = name
    self.__description = description
    self.__image = image
    self.__price = price
    self.__category = category # Refers to an instance of the ProductCategory class
    self.__reviews = reviews # Refers to the list of the ProductReview instances
    self.__available_item_count = available_item_count
    self.__account = account # Refers to an instance of the Account class

  def get_available_count(self):
    pass
  def update_available_count(self):
    pass
  def update_price(self, new_price):
    pass

class ProductCategory:
  def __init__(self, name, description, products):
    self.__name = name
    self.__description = description
    self.__products = products # Refers to the list of products

class ProductReview:
  def __init__(self, rating, review, image, user):
    self.__rating = rating
    self.__review = review
    self.__image = image
    self.__user = user # Refers to an instance of the AuthenticatedUser class
```

```c++
class Product {
  private:
    string productId;
    string name;
    string description;
    signed char[] image;
    double price;
    ProductCategory category;
    vector <ProductReview> reviews;
    int availableItemCount;
    Account account;

  public:
    int getAvailableCount();
    int updateAvailableCount();
    bool updatePrice(double newPrice);
}

public class ProductCategory {
  private:
    string name;
    string description;
    vector <Product> products;
}

public class ProductReview {
  private:
    int rating;
    string review;
    signed char[] image;
    AuthenticatedUser user;
}
```

```javascript
class Product {
  #productId;
  #name;
  #description;
  #image;
  #price;
  #category;
  #reviews;
  #availableItemCount;
  #account;

  constructor(productId, name, description, image, price, category, reviews, availableItemCount, account) {
    this.#productId = productId;
    this.#name = name;
    this.#description = description;
    this.#image = image;
    this.#price = price;
    this.#category = category; // Refers to an instance of the ProductCategory class
    this.#reviews = reviews; // Refers to the list of the ProductReview instances
    this.#availableItemCount = availableItemCount;
    this.#account = account; // Refers to an instance of the Account class
  }

  getAvailableCount();
  updateAvailableCount();
  updatePrice(newPrice);
}

class ProductCategory {
  #name;
  #description;
  #products;

  constructor(name, description, products) {
    this.#name = name;
    this.#description = description;
    this.#products = products; // Refers to the list of products
  }
}

class ProductReview {
  #rating;
  #review;
  #image;
  #user;

  constructor(rating, review, image, user) {
    this.#rating = rating;
    this.#review = review;
    this.#image = image;
    this.#user = user; // Refers to an instance of the AuthenticatedUser class
  }
}
```


### Shopping cart and cart items
The ShoppingCart and CartItem classes are used to add items to the shopping cart, update the quantities, and send the list of items to checkout. Both classes are defined below:
```java
public class CartItem {
  private int quantity;
  private double price;
  public boolean updateQuantity(int quantity);
}

public class ShoppingCart {
  private int totalPrice;
  private List<Items> items;

  public boolean addItem(Item item);
  public boolean removeItem(Item item);
  public List<Item> getItems();
  public boolean checkout();
}
```

```c#
class CartItem {
  private int quantity;
  private double price;
  public bool UpdateQuantity(int quantity);
}

class ShoppingCart {
  private int totalPrice;
  private List<Items> items;

  public bool AddItem(Item item);
  public bool RemoveItem(Item item);
  public List<Item> GetItems();
  public bool Checkout();
}
```

```python
class CartItem:
  def __init__(self, quantity, price):
    self.__quantity = quantity
    self.__price = price
  
  def update_quantity(self, quantity):
    pass

class ShoppingCart {
  def __init__(self, total_price, items):
    self.__total_price = total_price
    self.__items = items # List of items

  # item here refers to an instance of the Item class
  def add_item(self, item):
    pass
  # item here refers to an instance of the Item class
  def remove_item(self, item):
    pass
  def get_items(self): # Returns list of items
    pass 
  def checkout(self):
    pass
```

```c++
class CartItem {
  private:
    int quantity;
    double price;
  
  public:
    bool updateQuantity(int quantity);
}

class ShoppingCart {
  private:
    int totalPrice;
    vector<Items> items;

  public:
    bool addItem(Item item);
    bool removeItem(Item item);
    vector<Item> getItems();
    bool checkout();
}
```

```javascript
class CartItem {
  #quantity;
  #price;

  constructor(quantity, price) {
    this.#quantity = quantity;
    this.#price = price;
  }
  
  updateQuantity(quantity);
}

class ShoppingCart {
  #totalPrice;
  #items;

  constructor(totalPrice, items) {
    this.#totalPrice = totalPrice;
    this.#items = items; // List of items
  }

  // item here refers to an instance of the Item class
  addItem(item);
  // item here refers to an instance of the Item class
  removeItem(item);
  getItems(); // Returns list of items
  checkout();
}
```

### Order and order log
The Order class is responsible for making the payment, updating the order status, and sending the particular order to shipment. The OrderLog class creates the log of the order and is referenced in the Order class to keep track of all the orders. The definition of these two classes is given below:

```java
public class Order {
  private String orderNumber;
  private OrderStatus status;
  private Date orderDate;
  private List<OrderLog> orderLog;

  public boolean sendForShipment();
  public boolean makePayment(Payment payment);
  public boolean addOrderLog(OrderLog orderLog);
}

public class OrderLog {
  private String orderNumber;
  private Date creationDate;
  private OrderStatus status;
}
```

```c#
class Order {
  private string orderNumber;
  private OrderStatus status;
  private DateTime orderDate;
  private List<OrderLog> orderLog;

  public bool SendForShipment();
  public bool MakePayment(Payment payment);
  public bool AddOrderLog(OrderLog orderLog);
}

class OrderLog {
  private string orderNumber;
  private DateTime creationDate;
  private OrderStatus status;
}
```

```python
class CartItem:
  def __init__(self, quantity, price):
    self.__quantity = quantity
    self.__price = price
  
  def update_quantity(self, quantity):
    pass

class ShoppingCart {
  def __init__(self, total_price, items):
    self.__total_price = total_price
    self.__items = items # List of items

  # item here refers to an instance of the Item class
  def add_item(self, item):
    pass
  # item here refers to an instance of the Item class
  def remove_item(self, item):
    pass
  def get_items(self): # Returns list of items
    pass 
  def checkout(self):
    pass
```

```c++
class CartItem {
  private:
    int quantity;
    double price;
  
  public:
    bool updateQuantity(int quantity);
}

class ShoppingCart {
  private:
    int totalPrice;
    vector<Items> items;

  public:
    bool addItem(Item item);
    bool removeItem(Item item);
    vector<Item> getItems();
    bool checkout();
}
```

```javascript
class Order {
  #orderNumber;
  #status;
  #orderDate;
  #orderLog;

  constructor(orderNumber, status, orderDate, orderLog) {
    this.#orderNumber = orderNumber;
    this.#status = status; // Refers to the OrderStatus enum
    this.#orderDate = orderDate;
    this.#orderLog = orderLog; // List of order logs
  }

  sendForShipment();
  // payment here refers to an instance of the Payment class
  makePayment(payment);
  // order_log here refers to an instance of the OrderLog class
  addOrderLog(orderLog);
}

class OrderLog {
  #orderNumber;
  #creationDate;
  #status;

  constructor(orderNumber, creationDate, status) {
    this.#orderNumber = orderNumber;
    this.#creationDate = creationDate;
    this.#status = status; // Refers to the OrderStatus enum
  }
}
```
### Shipment and shipment log
The Shipment class keeps track of all the major details of the order’s dispatch and creates the shipment record using the ShipmentLog class. These classes are defined below:

```java
public class Shipment {
  private String shipmentNumber;
  private Date shipmentDate;
  private Date estimatedArrival;
  private String shipmentMethod;
  private List<ShipmentLog> shipmentLogs;

  public boolean addShipmentLog(ShipmentLog shipmentLog);
}

public class ShipmentLog {
  private String shipmentNumber;
  private Date creationDate;
  private ShipmentStatus status;
}
```

```c#
class Shipment {
  private string shipmentNumber;
  private DateTime shipmentDate;
  private DateTime estimatedArrival;
  private string shipmentMethod;
  private List<ShipmentLog> shipmentLogs;

  public bool AddShipmentLog(ShipmentLog shipmentLog);
}

class ShipmentLog {
  private string shipmentNumber;
  private DateTime creationDate;
  private ShipmentStatus status;
}
```

```python
class Shipment {
  def __init__(self, shipment_number, shipment_date, estimated_arrival, shipment_method, shipment_logs):
    self.__shipment_number = shipment_number
    self.__shipment_date = shipment_date
    self.__estimated_arrival = estimated_arrival
    self.__shipment_method = shipment_method
    self.__shipment_logs = shipment_logs # List of shipment logs

  # shipment_log here refers to an instance of the ShipmentLog class
  def add_shipment_log(self, shipment_log):
    pass

class ShipmentLog {
  def __init__(self, shipment_number, creation_date, status):
    self.__shipment_number = shipment_number
    self.__creation_date = creation_date
    self.__status = status # Refers to the ShipmentStatus enum
```

```c++
class Shipment {
  private:
    string shipmentNumber;
    time_t shipmentDate;
    time_t estimatedArrival;
    string shipmentMethod;
    vector<ShipmentLog> shipmentLogs;

  public bool addShipmentLog(ShipmentLog shipmentLog);
}

class ShipmentLog {
  private: 
    string shipmentNumber;
    time_t creationDate;
    ShipmentStatus status;
}
```

```javascript
class Shipment {
  #shipmentNumber;
  #shipmentDate;
  #estimatedArrival;
  #shipmentMethod;
  #shipmentLogs;

  constructor(shipmentNumber, shipmentDate, estimatedArrival, shipmentMethod, shipmentLogs) {
    this.#shipmentNumber = shipmentNumber;
    this.#shipmentDate = shipmentDate;
    this.#estimatedArrival = estimatedArrival;
    this.#shipmentMethod = shipmentMethod;
    this.#shipmentLogs = shipmentLogs; // List of shipment logs
  }

  // shipmentLog here refers to an instance of the ShipmentLog class
  addShipmentLog(shipmentLog);
}

class ShipmentLog {
  #shipmentNumber;
  #creationDate;
  #status;

  constructor(shipmentNumber, creationDate, status) {
    this.#shipmentNumber = shipmentNumber;
    this.#shipmentDate = creationDate;
    this.#estimatedArrival = status; // Refers to the ShipmentStatus enum
  }
}
```


### Payment
The Payment class is another abstract class with the ElectronicBankTranfer, CreditCard, and Cash classes as its child classes. This takes the PaymentStatus enum to keep track of the payment status. The definition of this class is provided below:
```java
// Payment is an abstract class
public abstract class Payment {
  private double amount;
  private Date timestamp;
  private PaymentStatus status;
  public abstract PaymentStatus makePayment();
}

public class CreditCard extends Payment {
  private String nameOnCard;
  private String cardNumber;
  private String billingAddress;
  private int code;
  public PaymentStatus makePayment() {
      // functionality
  }
}

public class ElectronicBankTransfer extends Payment {
  private String bankName;
  private String routingNumber; 
  private String accountNumber;
  private String billingAddress;
  public PaymentStatus makePayment() {
      // functionality
  }
}

public class Cash extends Payment {
  private String billingAddress;
  public PaymentStatus makePayment() {
      // functionality
  }
}
```

```c#
// Payment is an abstract class
public abstract class Payment {
  private double amount;
  private DateTime timestamp;
  private PaymentStatus status;
  public abstract PaymentStatus MakePayment();
}

class CreditCard : Payment {
  private string nameOnCard;
  private string cardNumber;
  private string billingAddress;
  private int code;
  public override PaymentStatus MakePayment() {
      // functionality
  }
}

class ElectronicBankTransfer : Payment {
  private string bankName;
  private string routingNumber; 
  private string accountNumber;
  private string billingAddress;
  public override PaymentStatus MakePayment() {
      // functionality
  }
}

class Cash : Payment {
  private string billingAddress;
  public override PaymentStatus makePayment() {
      // functionality
  }
}
```

```python
# Payment is an abstract class
from abc import ABC, abstractmethod

class Payment(ABC):
  def __init__(self, amount, timestamp, status):
    self.__amount = amount
    self.__timestamp = timestamp
    self.__status = status # Refers to the PaymentStatus enum

  # Returns the PaymentStatus enum
  @abstractmethod
  def make_payment(self):
    pass

class CreditCard(Payment):
  def __init__(self, amount, timestamp, status, name_on_card, card_number, billing_address, code):
    self.__name_on_card = name_on_card
    self.__card_number = card_number
    self.__billing_address = billing_address
    self.__code = code
    super().__init__(amount, timestamp, status)

  # Returns the PaymentStatus enum
  def make_payment(self):
    # functionality
    pass

class ElectronicBankTransfer(Payment):
  def __init__(self, amount, timestamp, status, bank_name, routing_number, account_number, billing_address):
    self.__bank_name = bank_name
    self.__account_number = routing_number
    self.__account_number = account_number
    self.__billing_address = billing_address
    super().__init__(amount, timestamp, status)
  
  # Returns the PaymentStatus enum
  def make_payment(self):
    # functionality
    pass

class Cash(Payment):
  def __init__(self, amount, timestamp, status, billing_address):
    self.__billing_address = billing_address
    super().__init__(amount, timestamp, status)

  # Returns the PaymentStatus enum
  def make_payment(self):
    # functionality
    pass
```

```c++
// Payment is an abstract class
class Payment {
  private:
    double amount;
    time_t timestamp;
    PaymentStatus status;
  
  public:
    virtual abstract PaymentStatus makePayment() = 0;
}

class CreditCard : public Payment {
  private:  
    string nameOnCard;
    string cardNumber;
    string billingAddress;
    int code;

  public:
    PaymentStatus makePayment() {
      // functionality
  }
}

class ElectronicBankTransfer : public Payment {
  private: 
    string bankName;
    string routingNumber; 
    string accountNumber;
    string billingAddress;
  
  public:
    PaymentStatus makePayment() {
      // functionality
  }
}

class Cash extends public Payment {
  private:
    string billingAddress;
  public:
    PaymentStatus makePayment() {
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

  constructor(amount, timestamp, status) {
    if (this.constructor == Payment) {
        throw new Error("Abstract classes can't be instantiated.");
    }
    else {
      this.#amount = amount;
      this.#timestamp = timestamp;
      this.#status = status; // Refers to the PaymentStatus enum
    }
  }
  
  // Returns the PaymentStatus enum
  makePayment();
}

class CreditCard extends Payment {
  #nameOnCard;
  #cardNumber;
  #billingAddress;
  #code;

  constructor(amount, timestamp, status, nameOnCard, cardNumber, billingAddress, code) {
    this.#nameOnCard = nameOnCard;
    this.#cardNumber = cardNumber;
    this.#billingAddress = billingAddress;
    this.#code = code;
    super(amount, timestamp, status);
  }  

  // Returns the PaymentStatus enum
  makePayment() {
      // functionality
  }
}

class ElectronicBankTransfer extends Payment {
  #bankName;
  #routingNumber;
  #accountNumber;
  #billingAddress;

  constructor(amount, timestamp, status, bankName, routingNumber, accountNumber, billingAddress) {
    this.#bankName = bankName;
    this.#routingNumber = routingNumber; 
    this.#accountNumber = accountNumber;
    this.#billingAddress = billingAddress;
    super(amount, timestamp, status);
  } 
  
  // Returns the PaymentStatus enum
  makePayment() {
      // functionality
  }
}

class Cash extends Payment {
  #billingAddress;

  constructor(amount, timestamp, status, billingAddress) {
    this.#billingAddress = billingAddress;
    super(amount, timestamp, status);
  }

  // Returns the PaymentStatus enum
  makePayment() {
      // functionality
  }
}
```


### Notification
The Notification class is responsible for sending notifications to customers about the order and shipment status either via SMS or email. Since you can extend this by adding more options, the Notification class will be an abstract class. It is defined below:
```java
// Notification is an abstract class
public abstract class Notification {
  private int notificationId;
  private Date createdOn;
  private String content;

  public abstract boolean sendNotification(Account account);
}

public class EmailNotification extends Notification {
  public boolean sendNotification(Account account) {
    // functionality 
  }
}

public class PhoneNotification extends Notification {
  public boolean sendNotification(Account account) {
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

  public abstract bool SendNotification(Account account);
}

class EmailNotification : Notification {
  public override bool SendNotification(Account account) {
    // functionality 
  }
}

class PhoneNotification : Notification {
  public override bool SendNotification(Account account) {
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

  # account here refers to the Account class
  @abstractmethod
  def send_notification(self, account):
    pass

class EmailNotification(Notification):
  def __init__(self, notification_id, created_on, content):
    super().__init__(notification_id, created_on, content)

  # account here refers to the Account class
  def send_notification(self, account):
    # functionality
    pass

class PhoneNotification(Notification):
  def __init__(self, notification_id, created_on, content):
    super().__init__(notification_id, created_on, content)

  # account here refers to the Account class
  def send_notification(self, account):
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
    virtual bool sendNotification(Account account) = 0;
}

class EmailNotification : public Notification {
  public:
    bool sendNotification(Account account) {
    // functionality 
  }
}

class PhoneNotification : public Notification {
  public:
    bool sendNotification(Account account) {
    // functionality 
  }
}
```

```javascript
// Notification is an abstract class
class Notification {
  #notificationId;
  #createdOn;
  #content;

  constructor(notificationId, createdOn, content) {
    if (this.constructor === Notification) {
      throw new Error("Abstract classes can't be instantiated.");
    }
    else {
      this.#notificationId = notificationId;
      this.#createdOn = createdOn;
      this.#content = content;
    }
  }

  // account here refers to the Account class
  sendNotification(account) {
    // functionality
  };
}

class EmailNotification extends Notification {
  // account here refers to the Account class
  sendNotification(account) {
    // functionality 
  }
}

class PhoneNotification extends Notification {
  // account here refers to the Account class
  sendNotification(account) {
    // functionality 
  }
}
```

### Search and catalog
The Catalog class contains the product information and implements the Search interface class to enable the search functionality based on the given criteria (name and category of product). Both classes are defined below:
```java
public interface Search {
  public List<Product> searchProductsByName(String name);
  public List<Product> searchProductsByCategory(String category);
}

public class Catalog implements Search {
  private HashMap<String, List<Product>> products;

  public List<Product> searchProductsByName(String name) {
    // functionality
  }

  public List<Product> searchProductsByCategory(String category) {
    // functionality
  }
}

```

```c#
interface ISearch {
  public List<Product> SearchProductsByName(string name);
  public List<Product> SearchProductsByCategory(string category);
}

class Catalog : ISearch {
  private HashMap<string, List<Product>> products;

  public List<Product> SearchProductsByName(string name) {
    // functionality
  }

  public List<Product> SearchProductsByCategory(string category) {
    // functionality
  }
}

```

```python
from abc import ABC, abstractmethod

class Search(ABC):
  def search_products_by_name(self, name): # Returns list of product names
    pass
  def search_products_by_category(self, category): # Returns list of product categories
    pass

class Catalog(Search):
  def __init__(self):
    self.__products = {}

  # Returns list of product names
  def search_products_by_name(self, name):
    # functionality
    pass

  # Returns list of product categories
  def search_products_by_category(self, category):
    # functionality
    pass
```

```c++
class Search {
  public: 
    virtual vector<Product> searchProductsByName(string name) = 0;
    virtual vector<Product> searchProductsByCategory(string category) = 0;
}

class Catalog : public Search {
  private:
    map<string, vector<Product>> products;

  public:
    vector<Product> searchProductsByName(string name) {
      // functionality
    }

    vector<Product> searchProductsByCategory(string category) {
      // functionality
    }
}
```

```javascript
class Search {
  constructor() {
    if (this.constructor == Search) {
      throw new Error("Abstract classes can't be instantiated.");
    }
  }

  searchProductsByName(name); // Returns list of product names
  searchProductsByCategory(category); // Returns list of product categories
}

class Catalog extends Search {
  #products;

  constructor() {
    this.#products = new Map();
  }

  // Returns list of product names
  searchProductsByName(name) {
    // functionality
  }

  // Returns list of product categories
  searchProductsByCategory(category) {
    // functionality
  }
}

```


## Wrapping up
We’ve explored the complete design of Amazon in this chapter. We’ve looked at how Amazon is visualized using various UML diagrams and designed using object-oriented principles and design patterns.


