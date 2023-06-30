# Code for the Online Blackjack Game
We've covered different aspects of the Blackjack game and observed the attributes attached to the problem using various UML diagrams. Let us now explore the more practical side of things where we will work on implementing the Blackjack game using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the Blackjack game:

- Java

- C#

- Python

- C++

- JavaScript

## Blackjack game classes
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```
### Enumerations and custom data type
The following code provides the definition of the enumeration and custom data type used in the Blackjack game.

Suit: We need to create an enumeration to keep track of the suit of the card, whether it is diamond, spade, heart, or club.

AccountStatus: We need to create an enumeration to keep track of the status of the account, whether it is active, canceled, closed, blocked, or none.

The Person class is used as a custom data type. The implementation of the Person class can be found below:
```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```

```java
// Enumeration
enum Suit {
  HEART,
  SPADE, 
  CLUB, 
  DIAMOND
}

enum AccountStatus {
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  NONE
}

// Custom Person data type class
public class Person {
  private String name;
  private String streetAddress;
  private String city;
  private String state;
  private int zipCode;
  private String country;
}
        Definition of enums and custom datatypes
```

```c#
// Enumeration
enum Suit {
  HEART,
  SPADE, 
  CLUB, 
  DIAMOND
}

enum AccountStatus {
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  NONE
}

// Custom Person data type class
class Person {
  private String name;
  private String streetAddress;
  private String city;
  private String state;
  private int zipCode;
  private String country;
}

Definition of enums and custom datatypes

```

```python
# Enumeration
class Suit(enum.Enum):
  HEART = 1
  SPADE = 2
  CLUB = 3
  DIAMOND = 4

class AccountStatus(enum.Enum):
  ACTIVE = 1
  CLOSED = 2
  CANCELED = 3
  BLACKLISTED = 4
  NONE = 5

# Custom Person data type class
class Person:
  def __init__(self, name, street_address, city, state, zip_code, country):
    self.__name = name
    self.__street_address = street_address
    self.__city = city
    self.__state = state
    self.__zip_code = zip_code
    self.__country = country

Definition of enums and custom datatypes

```

```c++
// Enumeration
enum Suit {
  HEART, 
  SPADE, 
  CLUB, 
  DIAMOND, 
};

enum AccountStatus {
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  NONE
};

// Custom Person data type class
class Person {
    private: 
        string name;
        string streetAddress;
        string city;
        string state;
        int zipCode;
        string country;
};

Definition of enums and custom datatypes

```

```javascript
// Enumeration
const Suit = Object.freeze({
  HEART, 
  SPADE, 
  CLUB, 
  DIAMOND, 
});

const AccountStatus = Object.freeze({
  ACTIVE, 
  CLOSED, 
  CANCELED, 
  BLACKLISTED, 
  BLOCKED
});

// Custom Person data type class
class Person {
    #name;
    #streetAddress;
    #city;
    #state;
    #zipCode
    #country;
    constructor(name, streetAddress, city, state,zipCode, country){
        this.#name = name;
        this.#streetAddress = streetAddress;
        this.#city = city;
        this.#state = state;
        this.#zipCode = zipCode;
        this.#country = country;
    }
}

Definition of enums and custom datatypes

```
### Card
This class contains the playing cards or cards used in the Blackjack game.

```java
public class Card {
  private Suit suit;
  private int faceValue;

  public Card(Suit suit, int faceValue);
}

The Card class

```

```c#
class Card {
  private Suit suit;
  private int faceValue;

  public Card(Suit suit, int faceValue);
}

The Card class

```

```python
class Card:
  def __init__(self, suit, face_value):
    self.__suit = suit
    self.__face_value = face_value

The Card class

```

```c++
class Card {
  private: 
    Suit suit;
    int faceValue;
    
  public: 
    Card(Suit suit, int faceValue);
};

The Card class

```

```javascript
class Card {
    #suit;
    #faceValue;
    constructor(suit, faceValue) {
        this.#suit = suit;
        this.#faceValue = faceValue;
    }
}


The Card class

```

### Deck and shoe
Shoe is a device to hold multiple Deck and a Deck has 52 cards of four suits. One suit contains nine number cards (2–10) and four face cards (King, Queen, Jack, and Ace).
```java
public class Deck {
  private List<Card> cards;

  public Deck();
  public List<Card> getCards();
}

public class Shoe {
  private List<Deck> decks;
  private int numberOfDecks;

  public Shoe(int numberOfDecks, List<Deck> decks) {
    // 1. createShoe();
    // 2. shuffle();
  }
  public void createShoe();
  public void shuffle();
  public Card dealCard();
}

The Deck and Shoe classes

```

```c#
class Deck {
  private List<Card> cards;

  public Deck();
  public List<Card> GetCards();
}

class Shoe {
  private List<Deck> decks;
  private int numberOfDecks;

  public Shoe(int numberOfDecks, List<Deck> decks) {
    // 1. CreateShoe();
    // 2. Shuffle();
  }
  public void CreateShoe();
  public void Shuffle();
  public Card DealCard();
}

The Deck and Shoe classes

```

```python
class Deck:
  def __init__(self, cards):
    self.__cards = []

  def get_cards(self):
    None

class Shoe:
  def __init__(self, decks, number_of_decks):
    self.__decks = {}
    self.__number_of_decks = number_of_decks

  def create_shoe(self):
    None

  def shuffle(self):
    None

  def deal_card(self):
    None

The Deck and Shoe classes

```

```c++
class Deck {
  private: 
    vector<Card> cards;

  public: 
    Deck();
    vector<Card> getCards();
};

class Shoe {
  private: 
    vector<Deck> decks;
    int numberOfDecks;

  public: 
    Shoe(int numberOfDecks, vector<Deck> decks) {
      // 1. createShoe();
      // 2. shuffle();
    }
    void createShoe();
    void shuffle();
    Card dealCard();
};

The Deck and Shoe classes

```

```javascript
class Deck {
  #cards;

  constructor(cards) {
    this.#cards = cards;
  }
  getCards();
}

class Shoe {
  #decks;
  #numberOfDecks;

  constructor(numberOfDecks, decks) {
    this.#decks = decks;
    this.#numberOfDecks = numberOfDecks;
  }
  createShoe();
  shuffle();
  dealCard();
}

The Deck and Shoe classes

```

### Hand
The Hand class represents a Blackjack hand used in this game and contains multiple cards.
```java
class Hand {
  #cards;

  constructor(cards) {
    this.#cards = cards;
  }
  
  getScores();
  addCard(Card card);
}

The Hand class

```

```c#
class Hand {
  private List<Card> cards;

  public Hand(Card card1, Card card2);
  public int GetScores();
  public void AddCard(Card card);
}

The Hand class

```

```python
class Hand:
  def __init__(self, cards):
    self.__cards = []

  def get_scores(self):
    None

  def add_card(self, card):
    None

The Hand class

```

```c++
class Hand {
  private: 
    vector<Card> cards;

  public: 
    Hand(Card card1, Card card2);
    int getScores();
    void addCard(Card card);
};

The Hand class

```

```javascript
class Hand {
  #cards;

  constructor(cards) {
    this.#cards = cards;
  }
  
  getScores();
  addCard(Card card);
}

The Hand class

```


### Players
The Player is an abstract class and the BlackjackPlayer and Dealer classes extend the Player class.

- BlackjackPlayer: They place the first wager and update the stake with winning and losing sums. They can choose between the hit and stand options.

- Dealer: They are primarily in charge of dealing cards and following the Blackjack rules.

```java
public abstract class Player {
  private String id;
  private String password;
  private double balance;
  private AccountStatus status;
  private Person person;
  private Hand hand;

  public void addHand(Hand hand);
  public void removeHand(Hand hand);
  public abstract boolean resetPassword();
  public void addToHand(Hand hand);
}

public class BlackjackPlayer extends Player {
  private int bet;
  private int totalCash;

  public BlackjackPlayer(Hand hand);
  public void placeBet(int bet);
  public boolean resetPassword(){
    // definition
  }
}

public class Dealer extends Player {
  private Hand hand;

  public int getTotalScore();
  public boolean resetPassword(){
    // definition
  }
}

Player and its derived classes

```

```c#
public abstract class Player {
  private String id;
  private String password;
  private double balance;
  private AccountStatus status;
  private Person person;
  private Hand hand;

  public void AddHand(Hand hand);
  public void RemoveHand(Hand hand);
  public abstract bool ResetPassword();
  public void AddToHand(Hand hand);
}

class BlackjackPlayer : Player {
  private int bet;
  private int totalCash;

  public BlackjackPlayer(Hand hand);
  public void PlaceBet(int bet);
  public override bool resetPassword(){
    // definition
  }
}

class Dealer : Player {
  private Hand hand;

  public int GetTotalScore();
  public override bool resetPassword(){
    // definition
  }
}

Player and its derived classes

```

```python
from abc import ABC, abstractmethod
class Player:
  def __init__(self, id, password, balance, status, person, hand):
    self.__id = id
    self.__password = password
    self.__balance = balance
    self.__status = status
    self.__person = person
    self.__hand = hand

  def add_hand(self, Hand hand):
    None
  def remove_hand(self, Hand hand):
    None

  c
  def reset_password(self):
    None
  def add_to_hand(self, Hand hand):
    None

class BlackjackPlayer(Player):
  def __init__(self, id, password, balance, status, person, hand, bet, total_cash):
    super().__init__(id, password, balance, status, person, hand)
    self.__bet = bet
    self.__total_cash = total_cash

  def place_bet(self, int bet):
    None
  
  def reset_password(self):
    # functionality

class Dealer(Player):
  def __init__(self, id, password, balance, status, person, hand,):
    super().__init__(id, password, balance, status, person, hand)

  def get_total_score(self):
    None

  def reset_password(self):
    # functionality

Player and its derived classes

```

```c++
// Player is an abstract class
class Player {
  private: 
    string id;
    string password;
    double balance;
    AccountStatus status;
    Person person;
    Hand hand;

  public: 
    void addHand(Hand hand);
    void removeHand(Hand hand);
    bool resetPassword() = 0;
    void addToHand(Hand hand);
};

class BlackjackPlayer : public Player {
  private: 
    int bet;
    int totalCash;

  public: 
    BlackjackPlayer(Hand hand);
    void placeBet(int bet);
    bool resetPassword(){
      // definition
    }
};

class Dealer : public Player {
  private: 
    Hand hand;

  public: 
    int getTotalScore();
    bool resetPassword(){
      // definition
    }
};

Player and its derived classes

```

```javascript
class Player {
  #id;
  #password;
  #balance;
  #status;
  #person;
  #hand;

  constructor(id, password, balance, status, person, hand) {
    if (this.constructor == Vehicle) {
      throw new Error("Abstract classes can't be instantiated.");
    }
    else {
      this.#id = id;
      this.#password = password;
      this.#balance = balance;
      this.#status = status;
      this.#status = status;
      this.#person = person;
      this.#hand = hand;
    }
  }
  addHand(hand);
  removeHand(hand);
  resetPassword();
  addToHand(hand);
}

class BlackjackPlayer extends Player {
  #bet;
  #totalCash;

  constructor(bet, totalCash) {
    this.#bet = bet;
    this.#totalCash = totalCash;
  }
  placeBet(bet);
  resetPassword();
}

class Dealer extends Player {
  #hand;

  constructor(hand) {
    this.#hand = hand;
  }
  getTotalScore();
  resetPassword();
}

Player and its derived classes

```

### Blackjack controller and game view
The BlackjackController class validates the actions (hit or stand) and responds accordingly. The BlackjackGameView class represents the game view.

```java
public class BlackjackController {
  public boolean validateAction();
}

public class BlackjackGameView {
  public void playAction(String action, Hand hand);
}
```

```c#
class BlackjackController {
  public bool ValidateAction();
}

class BlackjackGameView {
  public void PlayAction(String action, Hand hand);
}
```

```python
class BlackjackController:
  def validate_action():
    None

class BlackjackGameView:
  def play_action(self, action, hand):
    None
```

```javascript
class BlackjackController {
  validateAction();
}

class BlackjackGameView {
  playAction(action, hand);
}
```

### Blackjack game
The BlackjackGame class represents how we can play this game or its basic sequence of play.

```java
public class BlackjackGame {
  private Player player;
  private Dealer dealer;
  private Shoe shoe;
  private final int MAX_NUM_OF_DECKS = 4;

  public BlackjackGame(BlackjackPlayer player, Dealer dealer);
  public void playAction(String action, Hand hand);
  public void hit(Hand hand);
  public void stand();
  public void start();
}
```

```c#
class BlackjackGame {
  private Player player;
  private Dealer dealer;
  private Shoe shoe;
  private const int MAX_NUM_OF_DECKS = 4;

  public BlackjackGame(BlackjackPlayer player, Dealer dealer);
  public void PlayAction(String action, Hand hand);
  public void Hit(Hand hand);
  public void Stand();
  public void Start();
}
```

```python
class BlackjackGame:
  def __init__(self, player, dealer, shoe):
    self.__id = id
    self.__player = player
    self.__dealer = dealer
    self.__shoe = shoe
    self.__MAX_NUM_OF_DECKS = 4

  def play_action(action, hand):
    pass

  def hit(hand):
    pass

  def stand():
    pass

  def start():
    pass
```

```javascript
class BlackjackGame {
  #player;
  #dealer;
  #shoe;
  #MAX_NUM_OF_DECKS

  constructor(player, dealer, shoe) {
    this.#player = player;
    this.#dealer = dealer;
    this.#shoe = shoe;
    this.#MAX_NUM_OF_DECKS = 4;
  }

  playAction(action, hand);
  hit(hand);
  stand();
  start();
}
```

## Wrapping up
We've explored the complete design of the Blackjack game in this chapter. We've looked at how a basic Blacljack game can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
