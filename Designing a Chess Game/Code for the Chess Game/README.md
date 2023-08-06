# Code for the Chess Game
We've covered different aspects of the chess game and observed the attributes attached to the problem using various UML diagrams. Let's now explore the more practical side of things where we will work on implementing the chess game using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the chess game:

- Java

- C#

- Python

- C++

- JavaScript

## Chess game classes
In this section, we will provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```

### Enumerations and custom data type
The following code provides the definition of the enumeration and custom data type used in the chess game.

GameStatus: This enumeration keeps track of the active status of the player and the game, i.e, who wins and whether or not the game is a draw.

AccountStatus: We need to create an enumeration to keep track of the status of the account – whether it is active, canceled, closed, blocked, or none.

The Person class is used as a custom data type. The implementation of the Person class can be found below:
```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```

```java
// Enumerations
enum GameStatus {
  Active,
  BlackWin,
  WhiteWin,
  Forfeit,
  Stalemate,
  Resignation
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
```

```c#
// Enumerations
enum GameStatus {
  Active,
  BlackWin,
  WhiteWin,
  Forfeit,
  Stalemate,
  Resignation
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
```

```python
# Enumerations
class GameStatus(enum.Enum):
  Active =1
  BlackWin =2
  WhiteWin = 3
  Forfeit = 4
  Stalemate = 5
  Resignation = 6

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
```

```c++
// Enumerations
enum GameStatus {
  Active,
  BlackWin,
  WhiteWin,
  Forfeit,
  Stalemate,
  Resignation 
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
```
```javascript
// Enumerations
const GameStatus = Object.freeze({
  Active,
  BlackWin,
  WhiteWin,
  Forfeit,
  Stalemate,
  Resignation 
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
```

### Box and chessboard
The Box class holds the piece where the Chessboard contains the boxes and has the functionality of updating or resetting the board. The definitions of these classes are provided below:

```java
public class Box {
  private Piece piece;
  private int x;
  private int y;
}

public class Chessboard {
  private Box[][] boxes;
  private Date creationDate;
  
  public List<Piece> getPieces()
  public void resetBoard()
  public void updateBoard()
}
```

```c#
class Box {
  private Piece piece;
  private int x;
  private int y;
}

class Chessboard {
  private Box[][] boxes;
  private Date creationDate;
  
  public List<Piece> getPieces()
  public void resetBoard()
  public void updateBoard()
}
```

```python
class Box:
  def __init__(self, piece, x, y):
    self.__piece = piece
    self.__x = x
    self.__y = y

class Chessboard:
  def __init__(self, boxes, creation_date):
    self.__boxes = boxes
    self.__creation_date = creation_date

  def get_pieces(self):
    None
  def reset_board(self):
    None
  def update_board(self):
    None
```

```c++
class Box {
  private: 
    Piece piece;
    int x;
    int y;
};

class Chessboard {
  private:
    Box boxes[8][8]; 
    Date creationDate;

  public:
    list<Piece> getPieces();
    void resetBoard();
    void updateBoard();
};
```

```javascript
class Box {
    #piece;
    #x;
    #y;
    constructor(piece, x, y) {
        this.#piece = piece;
        this.#x = x;
        this.#y = y;
    }
}

class Chessboard {
  #boxes
  #creationDate;
  constructor(creationDate, boxes) {
        this.#creationDate = creationDate;
        this.#boxes = boxes;
    }

  getPieces();
  resetBoard();
  updateBoard();
}
```

### Piece
Piece is an abstract class that is extended by King, Queen, Knight, Bishop, Rook and Pawn. These derived classes override the canMove() function of Piece. The definitions of these classes are provided below:

```java
public abstract class Piece {
  private boolean killed = false;
  private boolean white = false;

  public boolean isWhite();
  public boolean isKilled(); 
  public abstract boolean canMove(Chessboard board, Box start, Box end);
}

public class King extends Piece {
  private boolean castlingDone = false;

  @Override
  public boolean canMove(Board board, Box start, Box end) {
    // definition
  }
}

public class Queen extends Piece {

  @Override
  public boolean canMove(Board board, Box start, Box end) {
    // definition
  }
}

public class Knight extends Piece {

  @Override
  public boolean canMove(Board board, Box start, Box end) {
    // definition
  }
}

public class Bishop extends Piece {

  @Override
  public boolean canMove(Board board, Box start, Box end) {
    // definition
  }
}

public class Rook extends Piece {

  @Override
  public boolean canMove(Board board, Box start, Box end) {
    // definition
  }
}

public class Pawn extends Piece {

  @Override
  public boolean canMove(Board board, Box start, Box end) {
    // definition
  }
}
```

```c#
public abstract class Piece {
  private bool killed = false;
  private bool white = false;

  public bool isWhite();
  public bool isKilled(); 
  public abstract bool canMove(Chessboard board, Box start, Box end);
}

public class King : Piece {
  private bool castlingDone = false;

  public override bool canMove(Chessboard board, Box start, Box end) {
    // definition
  }
}

public class Queen : Piece {
  public override bool canMove(Chessboard board, Box start, Box end) {
    // definition
  }
}

public class Knight : Piece {
  public override bool canMove(Chessboard board, Box start, Box end) {
    // definition
  }
}

public class Bishop : Piece {
  public override bool canMove(Chessboard board, Box start, Box end) {
    // definition
  }
}

public class Rook : Piece {
  public override bool canMove(Chessboard board, Box start, Box end) {
    // definition
  }
}

public class Pawn : Piece {
  public override bool canMove(Chessboard board, Box start, Box end) {
    // definition
  }
}
```

```python
from abc import ABC, abstractmethod
class Piece(ABC):
  def __init__(self, killed, white):
    self.__killed = killed
    self.__white = white

  def is_white(self):
    pass
    
  def is_killed(self):
    pass

  @abstractmethod
  def can_move(self, board, start, end):
    pass

class King(Piece):
  def __init__(self, killed, white, castling_done):
    super().__init__(killed, white)
    self.__castling_done = False
  
  def can_move(self, board, start, end):
    pass

class Queen(Piece):
  def __init__(self, killed, white):
    super().__init__(killed, white)
  
  def can_move(self, board, start, end):
    pass

class Knight(Piece):
  def __init__(self, killed, white):
    super().__init__(killed, white)
  
  def can_move(self, board, start, end):
    pass

class Bishop(Piece):
  def __init__(self, killed, white):
    super().__init__(killed, white)
  
  def can_move(self, board, start, end):
    pass

class Rook(Piece):
  def __init__(self, killed, white):
    super().__init__(killed, white)
  
  def can_move(self, board, start, end):
    pass

class Pawn(Piece):
  def __init__(self, killed, white):
    super().__init__(killed, white)
  
  def can_move(self, board, start, end):
    pass
```

```c++
class Piece {
  private: 
    bool killed = false;
    bool white = false;

  public: 
    bool isWhite();
    bool isKilled(); 
    bool virtual canMove(Chessboard board, Box start, Box end) = 0;
};

public class King : public Piece {
  private: 
    bool castlingDone = false;

  public: 
    bool canMove(Chessboard board, Box start, Box end) {
      // definition
    }
};

public class Queen : public Piece {
  public: 
    bool canMove(Chessboard board, Box start, Box end) {
      // definition
    }
};

public class Knight : public Piece {
  public: 
    bool canMove(Chessboard board, Box start, Box end) {
      // definition
    }
};

public class Bishop : public Piece {
  public: 
    bool canMove(Chessboard board, Box start, Box end) {
      // definition
    }
};

public class Rook : public Piece {
  public: 
    bool canMove(Chessboard board, Box start, Box end) {
      // definition
    }
};

public class Pawn : public Piece {
  public: 
    bool canMove(Chessboard board, Box start, Box end) {
      // definition
    }
};
```

```javascript
class Piece {
  #killed;
  #white;

  constructor(killed, white) {
    if (this.constructor == Vehicle) {
      throw new Error("Abstract classes can't be instantiated.");
    }
    else {
      this.#killed = killed;
      this.#white = white;
    }
  }
  isWhite();
  isKilled(hand);
  canMove();
}

class King extends Piece {
  #castlingDone;

    constructor(killed, white, castlingDone) {
      this.#killed = killed;
      this.#white = white;
      this.#castlingDone = castlingDone;
    }
  canMove() {
        // definition
    }
}

class Queen extends Piece {
  canMove() {
        // definition
    }
}

class Knight extends Piece {
  canMove() {
        // definition
    }
}

class Bishop extends Piece {
  canMove() {
        // definition
    }
}

class Rook extends Piece {
  canMove() {
        // definition
    }
}

class Pawn extends Piece {
  canMove() {
        // definition
    }
}
```


### Move
The Move class represents the move that will be taken by the player. It can tell the source and destiation box of the active Piece and whether or not it was a castling move. It also identifies the captured piece. The definitions of these classes are provided below:

```java
public class Move {
  private Box start;
  private Box end;
  private Piece pieceKilled;
  private Piece pieceMoved;
  private Player player;
  private boolean castlingMove = false;

  public boolean isCastlingMove();
}
```

```c#
class Move {
  private Box start;
  private Box end;
  private Piece pieceKilled;
  private Piece pieceMoved;
  private Player player;
  private bool castlingMove = false;

  public bool isCastlingMove();
}
```

```python
class Move:
  def __init__(self, start, end, piece_killed, piece_moved, player, castling_move):
    self.__start = start
    self.__end = end
    self.__piece_killed = piece_killed
    self.__piece_moved = piece_moved
    self.__player = player
    self.__castling_move = castling_move

  def is_castling_move(self):
    None
```

```c++
class Move {
  private: 
    Box start;
    Box end;
    Piece pieceKilled;
    Piece pieceMoved;
    Player player;
    bool castlingMove = false;

  public: 
    bool isCastlingMove();
};
```

```javascript
class Move {
  #start;
  #end;
  #pieceKilled;
  #pieceMoved;
  #player;
  #castlingMove;

  constructor(start, end, pieceKilled, pieceMoved, player, castlingMove) {
    this.#start = start;
    this.#end = end;
    this.#pieceKilled = pieceKilled;
    this.#pieceMoved = pieceMoved;
    this.#player = player;
    this.#castlingMove = false;
  }
  
  isCastlingMove();
}
```
### Account, player, and admin
The Account class is extended by the Player and Admin classes.

- The Player class records the player's information by storing the Person object, along with the chosen color, i.e., – whether or not the player is playing with white pieces.

- The Admin class decides whether or not the user is blocked.

The definitions of these classes are provided below:

```java
public class Account {
  private int id;
  private String password;
  private AccountStatus status;

  public boolean resetPassword();
}

public class Player extends Account {
  private Person person;
  private boolean whiteSide = false;
  private int totalGamesPlayed;

  public boolean isWhiteSide();
  public boolean isChecked();
}

public Admin extends Account {
  public boolean blockUser();
}
```

```c#
class Account {
  private int id;
  private String password;
  private AccountStatus status;

  public bool resetPassword();
}

class Player : Account {
  private Person person;
  private bool whiteSide = false;
  private int totalGamesPlayed;

  public bool isWhiteSide();
  public bool isChecked();
}

public Admin : Account {
  public bool blockUser();
}
```

```python
class Account:
  def __init__(self, id, password, status):
    self.__id = id
    self.__password = password
    self.__status = status

  def reset_password(self):
    None

class Player(Account):
  def __init__(self, id, password, status, person, total_games_played, white_side):
    super().__init__(id, password, status)
    self.__person = person
    self.__total_games_played = total_games_played
    self.__white_side = False
  
  def is_white_side(self):
    pass

  def is_checked(self):
    pass

class Admin(Account):
  def __init__(self, id, password, status):
    super().__init__(id, password, status)
  
  def block_user(self):
    pass
```

```c++
class Account {
  private: 
    int id;
    string password;
    AccountStatus status;

  public: 
    bool resetPassword();
};

class Player : public Account {
  private: 
    Person person;
    bool whiteSide = false;
    int totalGamesPlayed;

  public: 
    bool isWhiteSide();
    bool isChecked();
};

public Admin : public Account {
  public bool blockUser();
};
```

```javascript
class Account {
  #id;
  #password;
  #status;

  constructor(id, password, status) {
    this.#id = id;
    this.#password = password;
    this.#status = status;
  }
  resetPassword();
}

class Player extends Account {
  #person;
  #whiteSide;
  #totalGamesPlayed;

  constructor(person, whiteSide, totalGamesPlayed) {
    this.#person = person;
    this.#whiteSide = false;
    this.#totalGamesPlayed = totalGamesPlayed;
  }
  isWhiteSide(bet);
  isChecked();
}

class Admin extends Account {
  blockUser();
}
```


### Chess move controller and the game view
The ChessMoveController class validates the moves and responds accordingly. The ChessGameView class represents the game view. The definitions of these classes are provided below:

```java
public class ChessMoveController {
  public boolean validateMove();
}

public class ChessGameView {
  public void playMove();
}
```

```c#
class ChessMoveController {
  public bool ValidateMove();
}

class ChessGameView {
  public void playMove();
}
```

```python
class ChessMoveController:
  def validate_move():
    None

class ChessGameView:
  def play_move(self):
    None
```

```c++
class ChessMoveController {
  public: 
    bool validateMove();
};

class ChessGameView {
  public: 
    void playMove();
};
```

```javascript
class ChessMoveController {
  validateMove();
}

class ChessGameView {
  playMove();
}
```


### Chess game
The ChessGame class represents the current situation of the game while keeping track of turns and moves, and also decides when the game ends. The definition of this class is provided below:

```java
public class ChessGame {
  private Player[] players;
  private Chessboard board;
  private Player currentTurn;
  private GameStatus status;
  private List<Move> movesPlayed;

  public boolean isOver();
  public boolean playerMove(Player player, int startX, int startY, int endX, int endY) {
    /* 1. start box 
       2. end box
       3. move
       4. call makeMove() method
    */
  }
  private boolean makeMove(Move move, Player player) {
    /* 1. Validation of source piece
       2. Check whether or not the color ofthe piece is white
       3. Check if it is a valid move or not
       4. Check whether it is a castling move or not
       5. Store the move
    */
  }
}
```

```c#
public class ChessGame {
  private Player[] players;
  private Chessboard board;
  private Player currentTurn;
  private GameStatus status;
  private List<Move> movesPlayed;

  public bool isOver();
  public bool playerMove(Player player, int startX, int startY, int endX, int endY) {
    /* 1. start box 
       2. end box
       3. move
       4. call makeMove() method
    */
  }
  private bool makeMove(Move move, Player player) {
    /*  1. Validation of source piece
        2. Check whether or not the color ofthe piece is white
        3. Check if it is a valid move or not
        4. Check whether it is a castling move or not
        5. Store the move
    */
  }
}
```

```python
class BlackjackGame:
  def __init__(self, players, board, current_turn, status, moves_played):
    self.__player = player
    self.__board = board
    self.__current_turn = current_turn
    self.__status = status
    self.__moves_played = moves_played

  def is_over(self):
    pass

  def player_move(self, player, start_x, start_y, end_x, end_y):
    # 1. start box 
    # 2. end box
    # 3. move
    # 4. call makeMove() method
    

  def make_move(self, move, player):
    # 1. Validation of source piece
    # 2. Check whether or not the color ofthe piece is white
    # 3. Check if it is a valid move or not
    # 4. Check whether it is a castling move or not
    # 5. Store the move
```

```c++
class ChessGame {
  private: 
    list<Player> players;
    Chessboard board;
    Player currentTurn;
    GameStatus status;
    list<Move> movesPlayed;

  public: 
    bool isOver();
    bool playerMove(Player player, int startX, int startY, int endX, int endY) {
      /* 1. start box 
         2. end box
         3. move
         4. call makeMove() method
      */
    }
    bool makeMove(Move move, Player player) {
      /* 1. Validation of source piece
         2. Check whether or not the color ofthe piece is white
         3. Check if it is a valid move or not
         4. Check whether it is a castling move or not
         5. Store the move
      */
    }
}
```

```javascript
class ChessGame {
  #players;
  #board;
  #currentTurn;
  #status;
  #movesPlayed;

  constructor(players, board, currentTurn, status, movesPlayed) {
    this.#players = players;
    this.#board = board;
    this.#currentTurn = currentTurn;
    this.#status = status;
    this.#movesPlayed = movesPlayed;
  }

  isOver();
  playerMove(player, startX, startY, endX, endY) {
    /* 1. start box 
       2. end box
       3. move
       4. call makeMove() method
    */
  }
  makeMove(move, player) {
    /* 1. Validation of source piece
       2. Check whether or not the color ofthe piece is white
       3. Check if it is a valid move or not
       4. Check whether it is a castling move or not
       5. Store the move
    */
  }
}
```

## Wrapping up
We've explored the complete design of the chess game in this chapter. We've looked at how a basic chess game can be visualized using various UML diagrams and designed using object-oriented principles and design patterns.
