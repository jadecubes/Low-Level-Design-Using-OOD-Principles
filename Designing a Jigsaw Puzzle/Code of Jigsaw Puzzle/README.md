# Code of Jigsaw Puzzle
We’ve gone over the different aspects of the jigsaw puzzle and observed the attributes attached to the problem using various UML diagrams. Let’s explore the more practical side of things, where we will work on implementing the jigsaw puzzle using multiple languages. This is usually the last step in an object-oriented design interview process.

We have chosen the following languages to write the skeleton code of the different classes present in the jigsaw puzzle:

- Java

- C#

- Python

- C++

- JavaScript

## Jigsaw puzzle
In this section, we’ll provide the skeleton code of the classes designed in the class diagram lesson.
```
Note: For simplicity, we are not defining getter and setter functions. The reader can assume that all class attributes are private and accessed through their respective public getter methods and modified only through their public method functions.
```

### Enumerations
The following code defines the Edge enum that represents the shape of the puzzle piece:
```
Note: JavaScript does not support enumerations, so we will be using the Object.freeze() method as an alternative that freezes an object and prevents further modifications.
```

```java
enum Edge {
  INDENTATION, 
  EXTRUSION, 
  FLAT
}
```

```c#
enum Edge {
  INDENTATION, 
  EXTRUSION, 
  FLAT
}
```

```python
class Edge(enum.Enum):
  INDENTATION = 1 
  EXTRUSION = 2
  FLAT = 3
```

```c++
enum Edge {
  INDENTATION, 
  EXTRUSION, 
  FLAT
};
```

```javascript
const Edge  = Object.freeze({
	INDENTATION, 
  EXTRUSION, 
  FLAT
});
```

### Side
The Side class contains a reference to the Edge enum that will describe the edge shape of any side of a puzzle piece. Its definition is given below:

```java
public class Side {
  private Edge edge;
}
```

```c#
class Side {
  private Edge edge;
}
```

```python
class Side: 
  def __init__(self, edge):
    self.__edge = edge
```

```c++
class Side {
  private Edge edge;
}
```

```javascript
class Side {
  #edge;

  constructor(edge) {
    this.#edge = edge;
  }
}
```

### Piece
The Piece class contains a list of sides (representing each side of a piece) and ensures if a particular piece is a corner, middle, or edge using its respective functions. The definition of this class is provided below:

```java
public class Piece {
  private List<Side> sides = Arrays.asList(new Side[4]);
  public boolean checkCorner() {}
  public boolean checkEdge() {}
  public boolean checkMiddle() {}
}
```

```c#
class Piece {
  private List<Side> sides = new List<Side>(4);
  public bool CheckCorner() {}
  public bool CheckEdge() {}
  public bool CheckMiddle() {}
}
```

```python
class Piece:
  def __init__(self):
    self.__sides = [None] * 4 # List of sides and will be of length 4

  def check_corner(self):
    pass

  def check_edge(self):
    pass

  def check_middle(self):
    pass
```

```c++
class Piece {
  private:
    Side sides[4];
  public:
    bool checkCorner() {}
    bool checkEdge() {}
    bool checkMiddle() {}
}
```

```javascript
class Piece {
  constructor() {
    this.#sides = new Array(4) // List of sides and will be of length 4
  }
  
  checkCorner() {}
  checkEdge() {}
  checkMiddle() {}
}
```

### Puzzle
The Puzzle class includes the entire board of the jigsaw puzzle as well as the unused pieces. Since the board is a rectangle, it will be represented using a 2-D array. In addition, there will be only one instance of the puzzle board in the jigsaw puzzle. Therefore, the Puzzle class will be a Singleton class to ensure that only one instance for the board is created in the entire system. The definition of this class is given below:

```java
public class Puzzle {
  private List<List<Piece>> board;
  private List<Piece> free; // represents the currently free pieces (yet to be inserted in board)
  public void insertPiece(Piece piece, int row, int column) {};

  // Puzzle is a singleton class that ensures it will have only one active instance at a time
  private static Puzzle puzzle = null;
    
  // Created a static method to access the singleton instance of Puzzle class
  public static Puzzle getInstance() {
      if (puzzle == null) {
          puzzle = new Puzzle();
      }
      return puzzle;
  }  
}
```

```c#
class Puzzle {
  private List<List<Piece>> board;
  private List<Piece> free; // represents the currently free pieces (yet to be inserted in board)
  public void InsertPiece(Piece piece, int row, int column) {}

  // Puzzle is a singleton class that ensures it will have only one active instance at a time
  private static Puzzle puzzle = null;
    
  // Created a static method to access the singleton instance of Puzzle class
  public static Puzzle GetInstance() {
    if (puzzle == null) {
        puzzle = new Puzzle();
    }
    return puzzle;
  }  
}
```

```python
class __Puzzle(object):
  __instances = None

  # Puzzle is a singleton class that ensures it will have only one active instance at a time
  def __new__(cls):
    if cls.__instances is None:
        cls.__instances = super(__Puzzle, cls).__new__(cls)
    return cls.__instances

class Puzzle(metaclass=__Puzzle):
  def __init__(self):
    self.__board = [[]] # List of List of Piece (2D array)
    self.__free = [] # List of Piece for currently free pieces (yet to be inserted in board)

  def insert_piece(self, piece, row, column):
    pass
```

```c++
class Puzzle {
  private:
    static Puzzle *puzzle = NULL;
    vector<vector<Piece>> board;
    vector<Piece> free; // represents the currently free pieces (yet to be inserted in board)

  public:
    void insertPiece(Piece piece, int row, int column) {}
    static Puzzle *getInstance() {
      if (puzzle == nullptr) {
        puzzle = new Puzzle();
      }
      return puzzle;
    }
};
```

```javascript
class Puzzle {
  // Puzzle is a singleton class that ensures it will have only one active instance at a time
  constructor(board=null, free=null){
    if (Puzzle._instance){
      throw new Error("Singleton classes can't be instantiated more than once.")
    }

    Puzzle._instance = this;
    this.#board = new Array(new Array()); // List of List of Piece
    this.#free = new Array(); // List of Piece for currently free pieces (yet to be inserted in board)
  }

  // Created a static method to access the singleton instance of Puzzle class
  static getInstance() {
    if(!Puzzle._instance){
        return new Puzzle();
    }

    return Puzzle._instance;
  }

  insertPiece(piece, row, column) {}
}
```
### Puzzle solver
The PuzzleSolver class tries to solve the puzzle using the matchPieces() function. Its definition is given below:

```java
public class PuzzleSolver {
  public Puzzle matchPieces(Puzzle board) {}
}
```

```c#
class PuzzleSolver {
  public Puzzle MatchPieces(Puzzle board) {}
}
```

```python
class PuzzleSolver:
  # board here refers to the instance of the Puzzle board
  def match_pieces(self, board):
    # Returns the Puzzle board
    pass
```

```c++
class PuzzleSolver {
  public:
    Puzzle matchPieces(Puzzle board) {}
}
```

```javascript
class PuzzleSolver {
  // board here refers to the instance of the Puzzle board
  matchPieces(board) {
    // Returns the Puzzle board
  }
}
```



## Wrapping up
We've explored the complete design of a jigsaw puzzle in this chapter. We've looked at how a basic jigsaw puzzle can be visualized using various UML diagrams and designed it using object-oriented principles and design patterns.
