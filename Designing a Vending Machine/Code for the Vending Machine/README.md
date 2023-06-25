# Code for the Vending Machine
We’ve reviewed different aspects of the vending machine problem and observed the attributes attached to the problem using various UML diagrams. Let us now explore the more practical side of things, where we will work on implementing the vending machine using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the vending machine:

- Java

- C#

- Python

- C++

- JavaScript

## Vending machine classes
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```
### Enumerations
The following code provides the definition of the enumeration used in the vending machine system:
```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```

```java
// Enumerations
enum ProductType {
  CHOCOLATE,
  SNACK,
  BEVERAGE,
  OTHER
}

Enum definitions
```

```c#
// Enumerations
enum ProductType {
  CHOCOLATE,
  SNACK,
  BEVERAGE,
  OTHER
}

Enum definitions

```

```python
# Enumerations
class ProductType(Enum):
  CHOCOLATE = 1
  SNACK = 2
  BEVERAGE = 3
  OTHER = 4

  Enum definitions

```

```c++
// Enumerations
enum ProductType {
  CHOCOLATE,
  SNACK,
  BEVERAGE,
  OTHER
}

Enum definitions

```

```javascript
// Enumerations
const ProductType = Object.freeze({
  CHOCOLATE, 
  SNACK, 
  BEVERAGE, 
  OTHER
});

Enum definitions

```
### State
State is an interface and the NoMoneyInsertedState, MoneyInsertedState, and DispenseState classes implement the State interface. The definition of these classes is provided below:
```java
// State is an interface
public interface State {
    // Interface method (does not have a body)
    public void insertMoney(VendingMachine machine, double amount);
    public void pressButton(VendingMachine machine, int rackNumber);
    public void returnChange(double amount);
    public void updateInventory(VendingMachine machine, int rackNumber);
    public void dispenseProduct(VendingMachine machine, int rackNumber);
}
 
public class NoMoneyInsertedState implements State {
    @override
    public void insertMoney(VendingMachine machine, double amount) {
      // changes state to MonenInsertedState
    }
    public void pressButton(VendingMachine machine, int rackNumber) {}
    public void returnChange(double amount) {}
    public void updateInventory(VendingMachine machine, int rackNumber) {}
    public void dispenseProduct(VendingMachine machine, int rackNumber) {}
}

public class MoneyInsertedState implements State {
    @override
    public void insertMoney(VendingMachine machine, double amount) {}
    public void pressButton(VendingMachine machine, int rackNumber) {
        // check if product item is available
        // validate money
        // change state to DispenseState 
    }
    public void returnChange(double amount) {}
    public void updateInventory(VendingMachine machine, int rackNumber) {}
    public void dispenseProduct(VendingMachine machine, int rackNumber) {}
}

public class DispenseState implements State {
    @override
    public void insertMoney(VendingMachine machine, double amount) {}
    public void pressButton(VendingMachine machine, int rackNumber) {}
    public void returnChange(double amount){}
    public void updateInventory(VendingMachine machine, int rackNumber) {}
    public void dispenseProduct(VendingMachine machine, int rackNumber) {
        // dispense product
        // change state to NoMoneyInsertedState
    }
}
             The State interface and its derived classes

```

```c#
// State is an interface
public interface State {
    // Interface method (does not have a body)
    public void InsertMoney(VendingMachine machine, double amount);
    public void PressButton(VendingMachine machine, int rackNumber);
    public void ReturnChange(double amount);
    public void UpdateInventory(VendingMachine machine, int rackNumber);
    public void DispenseProduct(VendingMachine machine, int rackNumber);
}
 
class NoMoneyInsertedState : State {
    public void InsertMoney(VendingMachine machine,double amount) {
      // changes state to MonenInsertedState
    }
    public void PressButton(VendingMachine machine, int rackNumber) {}
    public void ReturnChange(double amount) {}
    public void UpdateInventory(VendingMachine machine, int rackNumber) {}
    public void DispenseProduct(VendingMachine machine, int rackNumber) {}
}

class MoneyInsertedState : State {
    public void InsertMoney(VendingMachine machine, double amount) {}
    public void PressButton(VendingMachine machine, int rackNumber) {
        // check if product item is available
        // validate money
        // change state to DispenseState 
    }
    public void ReturnChange(double amount) {}
    public void UpdateInventory(VendingMachine machine, int rackNumber) {}
    public void DispenseProduct(VendingMachine machine, int rackNumber) {}
}

class DispenseState : State {
    public void InsertMoney(VendingMachine machine, double amount) {}
    public void PressButton(VendingMachine machine, int rackNumber){ }
    public void ReturnChange(double amount) {}
    public void UpdateInventory(VendingMachine machine, int rackNumber) {}
    public void DispenseProduct(VendingMachine machine, int rackNumber) {
        // dispense product
        // change state to NoMoneyInsertedState
    }
}
                The State interface and its derived classes

```

```python
from abc import ABC, abstractmethod

class State(ABC):
  def insert_money(self, machine, amount):
    pass

  def press_button(self, machine, rack_number):
    pass

  def return_change(self, amount):
    pass

  def update_inventory(self, machine, rack_number):
    pass

  def dispense_product(self, machine, rack_number):
    pass

class NoMoneyInsertedState(State):
  def __init__(self):
    None

  def insert_money(self, machine, amount):
    # changes state to MonenInsertedState
    pass

  def press_button(self, machine, rack_number):
    pass

  def return_change(self, amount):
    pass

  def update_inventory(self, machine, rack_number):
    pass

  def dispense_product(self, machine, rack_number):
    pass

class MoneyInsertedState(State):
  def __init__(self):
    None

  def insert_money(self, machine, amount):
    pass

  def press_button(self, machine, rack_number):
    # check if product item is available
    # validate money
    # change state to DispenseState 
    pass

  def return_change(self, amount):
    pass

  def update_inventory(self, machine, rack_number):
    pass

  def dispense_product(self, machine, rack_number):
    pass

class DispenseState(State):
  def __init__(self):
    None

  def insert_money(self, machine, amount):
    pass

  def press_button(self, machine, rack_number):
    pass

  def return_change(self, amount):
    pass

  def update_inventory(self, machine, rack_number):
    pass
    
  def dispense_product(self, machine, rack_number):
    # dispense product
    # change state to NoMoneyInsertedState
    pass
                The State interface and its derived classes

```

```c++
// State is an abstract class
class State {
  public:
    virtual void insertMoney(VendingMachine machine, double amount) = 0;
    virtual void pressButton(VendingMachine machine, int rackNumber) = 0;
    virtual void returnChange(double amount) = 0;
    virtual void updateInventory(VendingMachine machine, int rackNumber) = 0;
    virtual void dispenseProduct(VendingMachine machine, int rackNumber) = 0;
}
 
class NoMoneyInsertedState : public State {
  public:
    void insertMoney(VendingMachine machine, double amount) {
      // changes state to MonenInsertedState
    }
    void pressButton(VendingMachine machine, int rackNumber) {}
    void returnChange(double amount) {}
    void updateInventory(VendingMachine machine, int rackNumber) {}
    void dispenseProduct(VendingMachine machine, int rackNumber) {}
}

class MoneyInsertedState : public State {
  public:
    void insertMoney(VendingMachine machine, double amount) {}
    void pressButton(VendingMachine machine, int rackNumber) {
        // check if product item is available
        // validate money
        // change state to DispenseState 
    }
    void returnChange(double amount) {}
    void updateInventory(VendingMachine machine, int rackNumber) {}
    void dispenseProduct(VendingMachine machine, int rackNumber) {}
}

class DispenseState : public State {
  public:
    void insertMoney(VendingMachine machine, double amount) {}
    void pressButton(VendingMachine machine, int rackNumber) {}
    void returnChange(double amount) {}
    void updateInventory(VendingMachine machine, int rackNumber) {}
    void dispenseProduct(VendingMachine machine, int rackNumber) {
        // dispense product
        // change state to NoMoneyInsertedState
    }
}

            The State interface and its derived classes

```

```javascript
class State {
    insertMoney(machine, amount);
    pressButton(machine, rackNumber);
    returnChange(amount);
    updateInventory(machine, rackNumber);
    dispenseProduct(machine, rackNumber);
}

class NoMoneyInsertedState extends Search {
    insertMoney(machine, amount) {
        // changes state to MonenInsertedState
    }
    pressButton(machine, rackNumber);
    returnChange(amount);
    updateInventory(machine, rackNumber);
    dispenseProduct(machine, rackNumber);
}

class MoneyInsertedState extends Search {
    insertMoney(machine, amount);
    pressButton(machine, rackNumber) {
        // check if product item is available
        // validate money
        // change state to DispenseState 
    }
    returnChange(amount);
    updateInventory(machine, rackNumber);
    dispenseProduct(machine, rackNumber);
}

class DispenseState extends Search {
    insertMoney(machine, amount);
    pressButton(machine, rackNumber);
    returnChange(amount);
    updateInventory(machine, rackNumber);
    dispenseProduct(machine,rackNumber) {
        // dispense product
        // change state to NoMoneyInsertedState
    }
}

       The State interface and its derived classes
```

### Product, rack and inventory
We will explore the Product, Rack, and Inventory classes that provide the details of the items available as well as their positions inside the vending machine. The definition of these classes is provided below:

```java
public class Product {
  private String name;
  private int id;
  private double price;
  private ProductType type;
}

public class Rack {
  private int productId;
  private int rackNumber;
  
  public boolean isEmpty();
}

public class Inventory {
  private int noOfProducts;
  private List<Product> products;

  public void addProduct(int productId, int rackId);
  public void removeProduct(int productId, int rackId);
}

The Product, Rack, and Inventory classes

```
```c#
class Product {
  private string name;
  private int id;
  private double price;
  private ProductType type;
}

class Rack {
  private int productId;
  private int rackNumber;
  
  public bool IsEmpty();
}

class Inventory {
  private int noOfProducts;
  private List<Product> products;

  public void AddProduct(int productId, int rackId);
  public void RemoveProduct(int productId, int rackId);
}

The Product, Rack, and Inventory classes

```

```python
class Product:
    def __init__(self, name, id, price, type):
        self.__name = name
        self.__id = id
        self.__price = price
        self.__type = type # here type is an instance of ProductType 
        

class Rack:
    def __init__(self, product_id, rack_number):
        self.__product_id = product_id
        self.__rack_number = rack_number
  
    def is_empty():
        None


class Inventory:
    def __init__(self, no_of_products, products):
        self.__no_of_products = no_of_products
        self.__products = products   
  
    def add_product(product_id, rack_id):
        None
    
    def remove_product(product_id, rack_id):
        None

        The Product, Rack, and Inventory classes

```
```c++
class Product {
  private:
    string name;
    int id;
    double price;
    ProductType type;
};

class Rack {
  private:
    int productId;
    int rackNumber;
  
  public:
    bool isEmpty();
};

class Inventory {
  private:
    int noOfProducts;
    vector<Product> products;

  public:
    void addProduct(int productId, int rackId);
    void removeProduct(int productId, int rackId);
};

The Product, Rack, and Inventory classes

```
```javascript
class Product {
  #name;
  #id;
  #price;
  #type;
    constructor(name, id, price, type){
        this.#name = name;
        this.#id = id;
        this.#price = price;
        this.#type = type; // ProductType object
    }
}
class Rack {
  #productId;
  #rackNumber;
    constructor(productId, rackNumber){
        this.#productId = productId;
        this.#rackNumber = rackNumber;
    }
  isEmpty();
}

class Inventory {
  #noOfProducts;
  #products;
    constructor(noOfProducts, products){
        this.#noOfProducts = noOfProducts;
        this.#products = products; 
    }
  addProduct(productId, rackId);
  removeProduct(productId,rackId);
}

The Product, Rack, and Inventory classes

```

### Vending machine
The VendingMachine class is the final class of the system, and it will also be a Singleton class so that there will only be a single instance of this class in the whole system. The definition of this class is given below:
```java
public class VendingMachine {
    private State currentState;
    private double amount;
    private int noOfRacks;
    private List<Rack> racks; 
    private List<int> availableRacks; 

    // The VendingMachine is a Singleton class that ensures it will have only one active instance at a time
    private static VendingMachine vendingMachine = null;

    // Created a private constructor to add a restriction (due to Singleton)
    private VendingMachine();

    // Created a static method to access the singleton instance of VendingMachine
    public static VendingMachine getInstance() {
        if (vendingMachine == null) {
            vendingMachine = new VendingMachine();
        }
        return vendingMachine;
    }

    public void insertMoney(double amount) {}
    public void pressButton(int rackNumber) {}
    public void returnChange(double amount) {}
    public void updateInventory(int rackNumber) {}
    public void dispenseProduct(int rackNumber) {}
    public int getProductIdAtRack(int rackNumber) {}
}
       
       The VendingMachine class

```
```c#
class VendingMachine {
    private State currentState;
    private double amount;
    private int noOfRacks;
    private List<Rack> racks; 
    private List<int> availableRacks; 

    // The VendingMachine is a singleton class that ensures it will have only one active instance at a time
    private static VendingMachine vendingMachine = null;

    // Created a private constructor to add a restriction (due to Singleton)
    VendingMachine() {}

    // Created a static method to access the singleton instance of VendingMachine
    public static VendingMachine GetInstance {
        get {
            if (vendingMachine == null) {
                vendingMachine = new VendingMachine();
            }
            return vendingMachine;
        }
    }

    public void InsertMoney(double amount) {}
    public void PressButton(int rackNumber) {}
    public void ReturnChange(double amount) {}
    public void UpdateInventory(int rackNumber) {}
    public void DispenseProduct(int rackNumber) {}
    public int GetProductIdAtRack(int rackNumber) {}
}

               The VendingMachine class

```
```python
# The __VendingMachine is a singleton class that ensures it will have only one active instance at a time
class __VendingMachine(object):
  __instances = None
  
  def __new__(cls):
    if cls.__instances is None:
        cls.__instances = super(__VendingMachine, cls).__new__(cls)
    return cls.__instances

class VendingMachine(metaclass=__VendingMachine):

  def __init__(self, current_state, amount, no_of_racks, racks, available_racks):
    self.__current_state = current_state
    self.__amount = amount
    self.__no_of_racks = no_of_racks
    self.__racks = racks
    self.__available_racks = available_racks

  def insert_money(self, amount):
    pass

  def press_button(self, rack_number):
    pass

  def return_change(self, amount):
    pass

  def update_inventory(self, rack_number):
    pass

  def dispense_product(self, rack_number):
    pass

  def get_product_id_at_rack(self, rack_number):
    pass

            The VendingMachine class

```

```c++
class VendingMachine {
    private:
        State currentState;
        double amount;
        int noOfRacks;
        list<Rack> racks; 
        list<int> availableRacks; 

        // The VendingMachine is a singleton class that ensures it will have only one active instance at a time
        static VendingMachine machine = NULL;

        // Created a private constructor to add a restriction (due to Singleton)
        VendingMachine() { }

    // Created a static method to access the singleton instance of VendingMachine
    public:
        static VendingMachine getInstance() {
            if (machine == NULL) {
                machine = new VendingMachine();
            }
            return machine;
        }
        
        void insertMoney(double amount){}
        void pressButton(int rackNumber){}
        void returnChange(double amount){}
        void updateInventory(int rackNumber){}
        void dispenseProduct(int rackNumber){}
        int getProductIdAtRack(int rackNumber){}
};

             The VendingMachine class

```

```javascript
class VendingMachine {
    #currentState;
    #amount;
    #noOfRacks;
    #racks;
    #availableRacks;
    constructor(currentState, amount, noOfRacks, racks, availableRacks) {
        if (VendingMachine._instance){
            throw new Error("Singleton classes can't be instantiated more than once.")
        }
        // The VendingMachine is a singleton class that ensures it will have only one active instance at a time
        VendingMachine._instance = this;

        this.#currentState = currentState;
        this.#amount = amount;
        this.#noOfRacks = noOfRacks;
        this.#racks = racks;
        this.#availableRacks = availableRacks;
    }
    // Created a static method to access the singleton instance of VendingMachine
    static getInstance() {
        if(!VendingMachine._instance){
            return new VendingMachine();
        }
        return VendingMachine._instance;
    }
    insertMoney(amount);
    pressButton(rackNumber);
    returnChange(amount);
    updateInventory(rackNumber);
    dispenseProduct(rackNumber);
    getProductIdAtRack(rackNumber);
}
              The VendingMachine class

```
## Wrapping up
We've explored the complete design of a vending machine in this chapter. We've looked at how a basic vending machine can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
