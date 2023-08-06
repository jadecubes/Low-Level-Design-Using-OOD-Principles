# Getting Ready: The Chess Game
## Problem definition
Chess is a board game for two players that involves strategy and is played on a checkered board made up of 64 squares in an 8x8 grid. Each player starts with 16 pieces, including a king, queen, two rooks, two knights, two bishops, and eight pawns. The goal is to checkmate the opponent's king. This occurs when the king is in a position to be captured (check), and there is no way to move the king out of capture (checkmate).

Each piece has its own unique movements. The rook can move horizontally or vertically, the knight can move in an L-shape position, the bishop can move diagonally, the queen can move in any direction, and the king can move one square in any direction. Pawns have the most complex movement rules and can move forward one square but capture diagonally.

The game can also end in a draw if the king is not in checkmate, and it is not possible for either player to force a win. A draw happens if there are not enough pieces on the board to force a checkmate (except the two kings), the same position is repeated three times, or both the players agree to a draw.
```
Note: There are numerous variations of the game of chess that are played globally. In this design problem, we'll focus on creating a digital version of the two-player chess game that can be played online.
```
## Expectations from the interviewee
There are several components in a chess game, each with specific constraints and requirements. The following provides an overview of some of the main expectations that the interviewer will want to hear you discuss in more detail during the interview.

### Chess pieces
The chess pieces have their own specifications according to the rules of the game that need to be clarified by the interviewer. Therefore, you may ask the following questions:

1. How many chess pieces are there in the game?

2. What are the different chess pieces, and what are their respective moves?

3. Which piece is the weakest in chess?

4. Which piece is the strongest in chess?

### Gameplay
In chess, the two opposing teams try to achieve the state of checkmate to win the game, or they face some special cases like a stalemate that need to be clarified by the interviewer. You may ask the following questions regarding them:

1. Which player takes the first turn?

2. What are the rules of the game?

3. What is a checkmate?

4. How does a stalemate happen?

5. Can a player forfeit/resign from the game?


## Design approach
We'll design this chess game system using the bottom-up design approach. For this purpose, we will follow the steps below:

- Identify and design the smallest components first – the box and piece.

- Use these small components to design bigger components, for example, the chessboard and move.

- Repeat the steps above until we design the whole chess game.

## Design patterns
It is always a good practice to discuss the design patterns that the online chess game falls under during the interview. Stating the design patterns will give the interviewer a positive impression and shows that the interviewee is well-versed in the advanced concepts of object-oriented design.

The following design patterns are used to design the online chess game:

- The Singleton design pattern

- The Command design pattern

Let's explore the requirements of the online Chess game in the next lesson.
