# Requirements for the Chess Game
In this lesson, we’ll list the requirements of the online chess game. This is a very crucial step since requirements define the scope of a problem, so getting them right from the interviewer and understanding them well will make the design of the rest of the system smooth and easy.

We’ll use the notational convention to identify each requirement with a unique label "Rn," where "R" is short for Requirement and "n" is a natural number.

## Requirement collection
R1: The purpose of this system is to enable multiplayer in a game of chess via an online platform.
```
multiplayer: A game that can be played against the CPU or an online opponent.
```

R2: The game will be played according to the official rules of an international chess game.

R3: Each player is randomly assigned the color—either black or white

R4: At the start of the game, each player will have eight pawns, two rooks, two bishops, two knights, one queen, and one king on the board.

R5: The player with the white pieces will make the first move.

R6: It is not possible for a player to retract or undo their move once it has been made.

R7: The system will keep a record of all moves made by both players.

R8: The game may end in a checkmate, forfeiture, stalemate (a draw), or resignation.

## International chess rules
The following table represents the basic rules of chess:


```
                    Rules for pieces
Piece                                        Rules

King                                         It can move one step in any direction.
                                             It cannot move to a box that might cause a check.


Queen                                        It can move horizontally, vertically, or diagonally unless it is blocked by a piece of the opponent.
                                             It cannot jump over the opponent's pieces.


Pawn                                         It can move one box forward.
                                             It is allowed to move two boxes forward if it is the first move by the player.
                                             It can move one box diagonally to kill the opponent's pawn.


Bishop                                       It can move only diagonally in any direction unless it is blocked by a piece of the opponent.
                                             It cannot jump over the opponent's piece.


Rook                                         It can move only horizontally or vertically unless it is blocked by a piece of the opponent.
                                             It cannot jump over the opponent's piece.


Knight                                       It can only move in an L-shape position by jumping two boxes horizontally or one box vertically.
                                             It can jump over other pieces.
```

The following table represents certain situations we might face while playing chess:

```
                    Rules for situations
Situation                                  Rules

Checkmate                          This is when a player's king is in check (can be captured by the opponent's pieces) and there is no possible escape for the piece.
                                   This situation decides the winner of the game.

Stalemate                          This is when a situation in which the player's king is not in check and no other move is possible.
                                   It draws the match.

Forfeiture                         If a player does not show up for the game, then the player is considered to have forfeited.

Resignation                        If a player is at a position in the game where they understand that the stronger opponent will win in case of any move and decides to quit, then they have resigned from the game.


Castling                           A player moves their king two boxes towards the rook on the same row.
                                   The rook is moved to the box the king passed over, which is next to the new position of the king.
                                   The king and rook should be at their original positions and should not have been moved before.
                                   No other piece should be between the king and the rook.
```
We've identified our requirements for the problem. In the next lesson, we will define different use cases for the online chess game design.
