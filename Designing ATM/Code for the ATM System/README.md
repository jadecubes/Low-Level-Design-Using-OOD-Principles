# Code for the ATM System
We've covered different aspects of the ATM and observed the attributes attached to the problem using various UML diagrams. Let's now explore the more practical side of things where we will work on implementing the ATM using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the ATM system:

- Java

- C#

- Python

- C++

- JavaScript

## ATM classes
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```

### Enumerations
The following code provides the definition of the enumeration used in the ATM system.

ATMState: This enumeration keeps track of the following states of an ATM:

- Idle

- Card inserted by the user

- Option selected

- Cash withdrawal

- Money transfer

- Display the account balance
```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```

```java
// Enumeration
enum ATMState {
  Idle,
  HasCard,
  SelestionOption,
  Withdraw,
  TransferMoney,
  BalanceInquiry
}
```

```c#
// Enumerations
enum ATMState {
  Idle,
  HasCard,
  SelestionOption,
  Withdraw,
  TransferMoney,
  BalanceInquiry
}
```

```python
# Enumerations
class ATMState(enum.Enum):
  Idle = 1
  HasCard = 2
  SelestionOption = 3
  Withdraw = 4
  TransferMoney = 5
  BalanceInquiry = 6
```

```c++
// Enumerations
enum ATMState {
  Idle,
  HasCard,
  SelestionOption,
  Withdraw,
  TransferMoney,
  BalanceInquiry 
};
```

```javascript
// Enumerations
const ATMState = Object.freeze({
  Idle,
  HasCard,
  SelestionOption,
  Withdraw,
  TransferMoney,
  BalanceInquiry 
});
```

### User and ATM card
The User class stores the user's ATMcard and bank account, where the ATMCard class holds the card number, customer name, card expiration date, and PIN. The definitions of these classes are provided below:
```java
public class User {
  private ATMCard card;
  private BankAccount account;
}

public class ATMCard {
  private String cardNumber;
  private String customerName;
  private Date cardExpiryDate;
  private int pin;
}
```

```c#
class User {
  private ATMCard card;
  private BankAccount account;
}

class ATMCard {
  private String cardNumber;
  private String customerName;
  private Date cardExpiryDate;
  private int pin;
}
```

```python
class User:
  def __init__(self, card, account):
    self.__card = card
    self.__account = account

class ATMCard:
  def __init__(self, cardNumber, customerName, cardExpiryDate):
    self.__cardNumber = cardNumber
    self.__customerName = customerName
    self.__cardExpiryDate = cardExpiryDate
    self.__pin = pin
```

```c++
class User {
  private: 
    ATMCard card;
    BankAccount account;
};

class ATMCard {
  private: 
    string cardNumber;
    string customerName;
    date cardExpiryDate;
    int pin;
};
```

```javascript
class User {
    #card;
    #account;
    constructor(card, account) {
        this.#card = card;
        this.#account = account;
    }
}

class User {
    #cardNumber;
    #customerName;
    #cardExpiryDate;
    #pin;
    constructor(cardNumber, customerName, cardExpiryDate, pin) {
        this.#cardNumber = cardNumber;
        this.#customerName = customerName;
        this.#cardExpiryDate = cardExpiryDate;
        this.#pin = pin;
    }
}
```

### Bank and bank account
The Bank class represents a bank having a name and code and can also add an ATM. The BankAccount class represents a bank account that has two child classes: SavingAccount and CurrentAccount. These derived classes have a method for finding the withdrawal limit. The definitions of these classes are provided below:

```java
public class Bank {
  private String name;
  private String bankCode;

  public String getBankCode();
  public boolean addATM();
}

public class BankAccount {
  private int accountNumber;
  private double totalBalance;
  private double availableBalance;

  public double getAvailableBalance();
}

public class SavingAccount extends BankAccount {
  public double withdrawLimit();
}

public class CurrentAccount extends BankAccount {
  public double withdrawLimit();
}
```

```c#
class Bank {
  private String name;
  private String bankCode;

  public String getBankCode();
  public bool addATM();
}

class BankAccount {
  private int accountNumber;
  private double totalBalance;
  private double availableBalance;

  public double getAvailableBalance();
}

public class SavingAccount : BankAccount {
  public double withdrawLimit();
}

public class CurrentAccount : BankAccount {
  public double withdrawLimit();
}
```

```python
from abc import ABC, abstractmethod
class Bank:
  def __init__(self, name, bankCode, availableBalance):
    self.__name = name
    self.__bankCode = bankCode
    self.__availableBalance = availableBalance

  def getBankCode(self):
    pass

  def addATM(self):
    pass

class BankAccount:
  def __init__(self, accountNumber, totalBalance, availableBalance):
    self.__accountNumber = accountNumber
    self.__totalBalance = totalBalance
    self.__availableBalance = availableBalance

  def getAvailableBalance(self):
    pass
    
class SavingAccount(BankAccount):
  def __init__(self, accountNumber, totalBalance, availableBalance):
    super().__init__(accountNumber, totalBalance, availableBalance)
  
  def withdrawLimit(self):
    pass

class CurrentAccount(BankAccount):
  def __init__(self, accountNumber, totalBalance, availableBalance):
    super().__init__(accountNumber, totalBalance, availableBalance)
  
  def withdrawLimit(self):
    pass
```

```c++
class Bank {
  private: 
    string name;
    string bankCode;

  public: 
    string getBankCode();
    bool addATM();
};

class BankAccount {
  private: 
    int accountNumber;
    double totalBalance;
    double availableBalance;

  public: 
    double getAvailableBalance();
};

public class SavingAccount : BankAccount {
  public: 
    double withdrawLimit();
};

public class CurrentAccount : BankAccount {
  public: 
    double withdrawLimit();
};
```

```javascript
class Bank {
  #name;
  #bankCode;

  constructor(name, bankCode) {
    this.#name = name;
    this.#bankCode = bankCode;
  }
  getBankCode();
  addATM();
}

class BankAccount {
  #accountNumber;
  #totalBalance;
  #availableBalance;

  constructor(accountNumber, totalBalance, availableBalance) {
    this.#accountNumber = accountNumber;
    this.#totalBalance = totalBalance;
    this.#availableBalance = availableBalance;
  }
  getAvailableBalance();
}

class SavingAccount extends BankAccount {
  constructor(accountNumber, totalBalance, availableBalance) {
    this.#accountNumber = accountNumber;
    this.#totalBalance = totalBalance;
    this.#availableBalance = availableBalance;
  }
  withdrawLimit();
}

class CurrentAccount extends BankAccount {
  constructor(accountNumber, totalBalance, availableBalance) {
    this.#accountNumber = accountNumber;
    this.#totalBalance = totalBalance;
    this.#availableBalance = availableBalance;
  }
  withdrawLimit();
}
```
### Card reader, card dispenser, printer, screen, and keypad
The CardReader, CashDispenser, Keypad, Screen and Printer classes compose the ATM and have the following functionalities:

- CardReader: It reads the card inserted by the user.

- CashDispenser: It dispenses cash upon withdrawal request.

- Keypad: It is used by the user to enter the PIN for authentication.

- Screen: It displays messages.

- Printer: It prints receipts.

The definitions of these classes are provided below:

```java
public class CardReader {
  public boolean readCard();
}

public class CashDispenser {
  public boolean dispenseCash();
}

public class Keypad {
  public String getInput();
}

public class Screen {
  public void showMessage();
}

public class Printer {
  public void printReceipt();
}
```

```c#
class CardReader {
  public bool readCard();
}

class CashDispenser {
  public bool dispenseCash();
}

class Keypad {
  public String getInput();
}

class Screen {
  public void showMessage();
}

class Printer {
  public void printReceipt();
}
```

```python
class CardReader:
  def readCard():
    pass

class CashDispenser:
  def dispenseCash():
    pass

class Keypad:
  def getInput():
    pass

class Screen:
  def showMessage():
    pass

class Printer:
  def printReceipt():
    pass
```

```c++
class CardReader {
  public: 
    bool readCard();
};

class CashDispenser {
  public: 
    bool dispenseCash();
};

class Keypad {
  public: 
    string getInput();
};

class Screen {
  public: 
    void showMessage();
};

class Printer {
  public: 
    void printReceipt();
};
```

```javascript
class CardReader {
  readCard();
}

class CashDispenser {
  dispenseCash();
}

class Keypad {
  getInput();
}

class Screen {
  showMessage();
}

class Printer {
  printReceipt();
}
```


### ATM state
ATMState is an abstract class that is extended by IdleState, HasCardState, SelectOperationState, CheckBalanceState, CashWithdrawalState and TransferMoneyState. All of these derived classes override the returnCard() and exit() functions of the ATMState class. The derived classes individually override the following functions:

- IdleState: This class overrides the insertCard() function.

- HasCardState: This class overrides the authenticatePin() function.

- SelectOperationState: This class overrides the selectOperation() function.

- CheckBalanceState: This class overrides the displayBalance() function.

- CashWithdrawalState: This class overrides the cashWithdrawal() function.

- TransferMoneyState: This class overrides the transferMoney() function.

The definitions of these classes are provided below:
```java
public abstract class ATMState {
  public abstract void insertCard(ATM atm, ATMCard card);
  public abstract void authenticatePin(ATM atm, ATMCard card, int pin);
  public abstract void selectOperation(ATM atm, ATMCard card, TransactionType tType);
  public abstract void cashWithdrawal(ATM atm, ATMCard card, int withdrawAmount);
  public abstract void displayBalance(ATM atm, ATMCard card);
  public abstract void transferMoney(ATM atm, ATMCard card, int accountNumber, int transferAmount);
  public abstract void returnCard();
  public abstract void exit(ATM atm);

}

public class IdleState extends ATMState {
  @Override
  public void insertCard(ATM atm, ATMCard card) {
    // definition
  }

  @Override
  public void returnCard() {
    // definition
  }

  @Override
  public void exit(ATM atm) {
    // definition
  }
}

public class HasCardState extends ATMState {
  @Override
  public void authenticatePin(ATM atm, ATMCard card, int pin) {
    // definition
  }

  @Override
  public void returnCard() {
    // definition
  }

  @Override
  public void exit(ATM atm) {
    // definition
  }
}

public class SelectOperationState extends ATMState {
  @Override
  public void selectOperation(ATM atm, ATMCard card, TransactionType tType) {
    // definition
  }

  @Override
  public void returnCard() {
    // definition
  }

  @Override
  public void exit(ATM atm) {
    // definition
  }
}

public class CheckBalanceState extends ATMState {
  @Override
  public void displayBalance(ATM atm, ATMCard card) {
    // definition
  }

  @Override
  public void returnCard() {
    // definition
  }

  @Override
  public void exit(ATM atm) {
    // definition
  }
}

public class CashWithdrawalState extends ATMState {
  @Override
  public void cashWithdrawal(ATM atm, ATMCard card, int withdrawAmount) {
    // definition
  }

  @Override
  public void returnCard() {
    // definition
  }

  @Override
  public void exit(ATM atm) {
    // definition
  }
}

public class TransferMoneyState extends ATMState {
  @Override
  public void transferMoney(ATM atm, ATMCard card, int accountNumber, int transferAmount) {
    // definition
  }

  @Override
  public void returnCard() {
    // definition
  }

  @Override
  public void exit(ATM atm) {
    // definition
  }
}
```

```c#
public abstract class ATMState {
  public abstract void insertCard(ATM atm, ATMCard card);
  public abstract void authenticatePin(ATM atm, ATMCard card, int pin);
  public abstract void selectOperation(ATM atm, ATMCard card, TransactionType tType);
  public abstract void cashWithdrawal(ATM atm, ATMCard card, int withdrawAmount);
  public abstract void displayBalance(ATM atm, ATMCard card);
  public abstract void transferMoney(ATM atm, ATMCard card, int accountNumber, int transferAmount);
  public abstract void returnCard();
  public abstract void exit(ATM atm);

}

public class IdleState : ATMState {
  public override void insertCard(ATM atm, ATMCard card) {
    // definition
  }

  public override void returnCard() {
    // definition
  }

  public override void exit(ATM atm) {
    // definition
  }
}

public class HasCardState : ATMState {
  public override void authenticatePin(ATM atm, ATMCard card, int pin) {
    // definition
  }

  public override void returnCard() {
    // definition
  }

  public override void exit(ATM atm) {
    // definition
  }
}

public class SelectOperationState : ATMState {
  public override void selectOperation(ATM atm, ATMCard card, TransactionType tType) {
    // definition
  }

  public override void returnCard() {
    // definition
  }

  public override void exit(ATM atm) {
    // definition
  }
}

public class CheckBalanceState : ATMState {
  public override void displayBalance(ATM atm, ATMCard card) {
    // definition
  }

  public override void returnCard() {
    // definition
  }

  public override void exit(ATM atm) {
    // definition
  }
}

public class CashWithdrawalState : ATMState {
  public override void cashWithdrawal(ATM atm, ATMCard card, int withdrawAmount) {
    // definition
  }

  public override void returnCard() {
    // definition
  }

  public override void exit(ATM atm) {
    // definition
  }
}

public class TransferMoneyState : ATMState {
  public override void transferMoney(ATM atm, ATMCard card, int accountNumber, int transferAmount) {
    // definition
  }

  public override void returnCard() {
    // definition
  }

  public override void exit(ATM atm) {
    // definition
  }
}
```

```python
from abc import ABC, abstractmethod
class ATMState(ABC):
  @abstractmethod
  def insertCard(self, atm, card):
    pass

  @abstractmethod
  def authenticatePin(self, atm, card, pin):
    pass

  @abstractmethod
  def selectOperation(self, atm, card, transactionType):
    pass

  @abstractmethod
  def cashWithdrawal(self, atm, card, withdrawAmount):
    pass

  @abstractmethod
  def displayBalance(self, atm, card):
    pass

  @abstractmethod
  def transferMoney(self, atm, card, accountNumber, transferAmount):
    pass

  @abstractmethod
  def returnCard(self):
    pass

  @abstractmethod
  def exit(self, atm):
    pass

class IdleState(ATMState):
  def insertCard(self, ATM atm, ATMCard card):
    pass

  def returnCard(self):
    pass

  def exit(self, ATM atm):
    pass

class HasCardState(ATMState):
  def authenticatePin(self, atm, card, pin):
    pass

  def returnCard(self):
    pass

  def exit(self, ATM atm):
    pass
    
class SelectOperationState(ATMState):
  def selectOperation(self, atm, card, transactionType):
    pass

  def returnCard(self):
    pass

  def exit(self, ATM atm):
    pass

class CheckBalanceState(ATMState):
  def displayBalance(self, atm, card):
    pass

  def returnCard(self):
    pass

  def exit(self, ATM atm):
    pass

class CashWithdrawalState(ATMState):
  def cashWithdrawal(self, atm, card, withdrawAmount):
    pass

  def returnCard(self):
    pass

  def exit(self, ATM atm):
    pass

class TransferMoneyState(ATMState):
  def transferMoney(self, atm, card, accountNumber, transferAmount):
    pass

  def returnCard(self):
    pass

  def exit(self, ATM atm):
    pass
```

```c++
class ATMState {
  public void insertCard(ATM atm, ATMCard card) = 0;
  public void authenticatePin(ATM atm, ATMCard card, int pin) = 0;
  public void selectOperation(ATM atm, ATMCard card, TransactionType tType) = 0;
  public void cashWithdrawal(ATM atm, ATMCard card, int withdrawAmount) = 0;
  public void displayBalance(ATM atm, ATMCard card) = 0;
  public void transferMoney(ATM atm, ATMCard card, int accountNumber, int transferAmount) = 0;
  public void returnCard() = 0;
  public void exit(ATM atm) = 0;
};

public class IdleState : public ATMState {
  public: 
    void insertCard(ATM atm, ATMCard card) {
      // definition
    }

    void returnCard() {
      // definition
    }

    void exit(ATM atm) {
      // definition
    }
};

public class HasCardState : public ATMState {
  public: 
    void authenticatePin(ATM atm, ATMCard card, int pin) {
      // definition
    }

    void returnCard() {
      // definition
    }

    void exit(ATM atm) {
      // definition
    }
};

public class SelectOperationState : public ATMState {
  public: 
    void selectOperation(ATM atm, ATMCard card, TransactionType tType) {
      // definition
    }

    void returnCard() {
      // definition
    }

    void exit(ATM atm) {
      // definition
    }
};

public class CheckBalanceState : public ATMState {
  public: 
    void displayBalance(ATM atm, ATMCard card) {
      // definition
    }

    void returnCard() {
      // definition
    }

    void exit(ATM atm) {
      // definition
    }
};

public class CashWithdrawalState : public ATMState {
  public: 
    void cashWithdrawal(ATM atm, ATMCard card, int withdrawAmount) {
      // definition
    }

    void returnCard() {
      // definition
    }

    void exit(ATM atm) {
      // definition
    }
};

public class TransferMoneyState : public ATMState {
  public: 
    void transferMoney(ATM atm, ATMCard card, int accountNumber, int transferAmount) {
      // definition
    }

    void returnCard() {
      // definition
    }

    void exit(ATM atm) {
      // definition
    }
};
```

```javascript
class ATMState {
  insertCard();
  authenticatePin(atm, card, pin);
  selectOperation(atm, card, transactionType);
  cashWithdrawal(atm, card, withdrawAmount);
  displayBalance(atm, card);
  transferMoney(atm, card, accountNumber, transferAmount);
  returnCard();
  exit();
}

class IdleState extends ATMState {
  insertCard() {
    // definition
  }
  returnCard() {
    // definition
  }
  exit() {
    // definition
  }
}

class HasCardState extends ATMState {
  authenticatePin(atm, card, pin) {
    // definition
  }
  returnCard() {
    // definition
  }
  exit() {
    // definition
  }
}

class SelectOperationState extends ATMState {
  selectOperation(atm, card, transactionType) {
    // definition
  }
  returnCard() {
    // definition
  }
  exit() {
    // definition
  }
}

class CheckBalanceState extends ATMState {
  displayBalance(atm, card) {
    // definition
  }
  returnCard() {
    // definition
  }
  exit() {
    // definition
  }
}

class CashWithdrawalState extends ATMState {
  cashWithdrawal(atm, card, withdrawAmount) {
    // definition
  }
  returnCard() {
    // definition
  }
  exit() {
    // definition
  }
}

class TransferMoneyState extends ATMState {
  transferMoney(atm, card, accountNumber, transferAmount) {
    // definition
  }
  returnCard() {
    // definition
  }
  exit() {
    // definition
  }
}
```
### ATM and ATM room
An ATMRoom has an ATM and a User with the following:

- A specific state at a given moment

- Balance

- A limited number of hundred, fifty, and ten dollar bills

The definitions of these classes are provided below:

```java
public class ATM {
  private static ATM atmObject = new ATM(); //Singleton
  private ATMState currentATMState;
  private int atmBalance;
  private int noOfHundredDollarBills;
  private int noOfFiftyDollarBills;
  private int noOfTenDollarBills;

  public void displayCurrentState();
  public void initializeATM(int atmBalance, int noOfHundredDollarBills, int noOfFiftyDollarBills, int noOfTenDollarBills);
}

public class ATMRoom {
  private ATM atm;
  private User user;
}
```

```c#
class ATM {
  private static ATM atmObject = new ATM(); //Singleton
  private ATMState currentATMState;
  private int atmBalance;
  private int noOfHundredDollarBills;
  private int noOfFiftyDollarBills;
  private int noOfTenDollarBills;

  public void displayCurrentState();
  public void initializeATM(int atmBalance, int noOfHundredDollarBills, int noOfFiftyDollarBills, int noOfTenDollarBills);
}

class ATMRoom {
  private ATM atm;
  private User user;
}
```

```python
class ATM:
  def __init__(self, currentATMState, atmBalance, noOfHundredDollarBills, noOfFiftyDollarBills, noOfTenDollarBills):
    self.__currentATMState = currentATMState
    self.atmBalance = atmBalance
    self.noOfHundredDollarBills = noOfHundredDollarBills
    self.noOfFiftyDollarBills = noOfFiftyDollarBills
    self.noOfTenDollarBills = noOfTenDollarBills

  def displayCurrentState(self):
    pass

  def initializeATM(self, atmBalance, noOfHundredDollarBills, noOfFiftyDollarBills, noOfTenDollarBills):
    pass


class ATMRoom:
  def __init__(self, atm, user):
    self.__atm = atm
    self.user = user
```

```c++
class ATM {
  private: 
    static ATM atmObject = new ATM(); //Singleton
    ATMState currentATMState;
    int atmBalance;
    int noOfHundredDollarBills;
    int noOfFiftyDollarBills;
    int noOfTenDollarBills;

  public: 
    void displayCurrentState();
    void initializeATM(int atmBalance, int noOfHundredDollarBills, int noOfFiftyDollarBills, int noOfTenDollarBills);
};

class ATMRoom {
  private: 
    ATM atm;
    User user;
};
```
```javascript
class ATM {
  #currentATMState;
  #atmBalance;
  #noOfHundredDollarBills;
  #noOfFiftyDollarBills;
  #noOfTenDollarBills;

  constructor(currentATMState, atmBalance, noOfHundredDollarBills, noOfFiftyDollarBills, noOfTenDollarBills) {
    this.#currentATMState = currentATMState;
    this.#atmBalance = atmBalance;
    this.#noOfHundredDollarBills = noOfHundredDollarBills;
    this.#noOfFiftyDollarBills = noOfFiftyDollarBills;
    this.#noOfTenDollarBills = noOfTenDollarBills;
  }

  displayCurrentState();
  initializeATM(atmBalance, noOfHundredDollarBills, noOfFiftyDollarBills, noOfTenDollarBills);
}

class ATMRoom {
  #atm;
  #user;

  constructor(atm, user) {
    this.#atm = atm;
    this.#user = user;
  }
}
```

## Wrapping up
We've explored the complete design of the ATM in this chapter. We've looked at how a basic ATM system can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
