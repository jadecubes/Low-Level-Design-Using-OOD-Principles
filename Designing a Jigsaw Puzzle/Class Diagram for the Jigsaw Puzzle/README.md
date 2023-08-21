# Class Diagram for the Jigsaw Puzzle
In this lesson, we’ll identify and design the classes, abstract classes, and interfaces based on the requirements that we have previously gathered from the interviewer in our jigsaw puzzle.

## Components of a jigsaw puzzle
As mentioned earlier, we should design the jigsaw puzzle using a bottom-up approach.

### Side
The Side class represents the shape of our jigsaw piece and whether it contains an indentation, extrusion, or flat edge. The UML representation of the class is shown below:

[The class diagram of the Side class]

```
R2: All pieces will have four sides that can either have an indentation, an extrusion, or a flat edge.
```

### Piece
The Piece class contains an array of sides of size four. It will also be used to identify middle pieces, corner pieces, and edge pieces. The class representation of the Piece class is provided below:

[The class diagram of the Piece class]

```
R2: All pieces will have four sides that can either have an indentation, an extrusion, or a flat edge.

R3: There are four corner pieces, some edge pieces, and the remaining ones are middle pieces. A corner piece has two flat sides, an edge piece only has one flat side, and a middle piece is one that does not have any flat edge.
```

### Puzzle
The Puzzle class represents the board of our jigsaw game. Since our board is a rectangle, it will be represented by a 2-D array. There will be a 1-D array to represent the unused free pieces yet to be inserted into the puzzle board. It will also have the insertPiece() function to insert the piece into the board, which will first ensure that the piece being inserted is unique from its counterparts and only then place the piece in the specified row and column.
```
Note: Since the puzzle board does not have the functionality of rotating pieces yet, all pieces need to be unique to fit into the board and solve the puzzle.
```
This class is represented below:

[The class diagram of the Puzzle class]

```
R1: Our board will be in the shape of a rectangle.

R4: All pieces will be unique, so only one piece will fit with only one other piece.
```

### Puzzle solver
The PuzzleSolver class is responsible for solving an unsolved jigsaw puzzle board using its matchPieces() function. The visual representation of this class is given below:

[The class diagram of the PuzzleSolver class]

```
R5: Two pieces fit together by the curvature of the indentation on one piece matching up to the curvature of the extrusion on another.
```
### Edge enumeration
The Edge enum describes the various edges present in a jigsaw puzzle piece. It is represented using the class diagram given below:

[The class diagram of the Edge enum]

## Relationship between the classes
Now, we’ll discuss the relationships between the classes we have defined above in our jigsaw puzzle.

### Association
The class diagram has the following association relationships:

- The Puzzle has a one-way association with PuzzleSolver.

[The association relationship between classes]

### Composition
The class diagram has the following composition relationships:

- The Puzzle class is composed of the Piece class, which is composed of the Side class.

[The composition relationship between classes]

## Class diagram for the jigsaw puzzle
Here’s the complete class diagram for our jigsaw puzzle:

[The class diagram of the jigsaw puzzle]

## Design pattern
In the jigsaw puzzle, there is only one instance of the puzzle board. Therefore, we use the Singleton design pattern to ensure that only one instance for the board is created using a special creation method, and this instance has a global point of access.

## Additional requirements
The interviewer can introduce some additional requirements in the jigsaw puzzle, or they can ask some follow-up questions. Let's see some examples of additional requirements:

Rotate piece: Pieces can be rotated to fit on the puzzle. The class diagram provided below shows the added functionality of rotation in the Piece class:

[The class diagram of the rotation functionality in the Piece class]

We have completed the class diagram of the jigsaw puzzle according to the requirements. Now, let’s write the code for our designed classes in some of the most popular languages.
