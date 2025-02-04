Chess Puzzles
=============

Rules
-----

(sourced from `puzzle-chess.com <https://www.puzzle-chess.com>`_)

* Pieces move as standard chess pieces.
* You can perform only capture moves.
* Your goal is to end up with one single piece on the board.
* **Ranger:** You are allowed to capture the king.
* **Solo:** Pieces can only move twice, and you are NOT allowed to capture the king. The king must be the final piece on the board.
* **Melee:** White moves first, and each color alternates turns.

Options
-------

Using a different board theme color may be useful for differentiating each mode.

Introduction
------------

Like the word puzzles, these are considered an outlier compared to the rest of the logic puzzles. However, this can have
some interesting solutions based off of intuition, and practice is still very important here.

Technique
---------

The fastest approach to solving these puzzles is to see the solution from square one, since it is difficult to make moves
that are guaranteed, and each move is dependent on the results of the past ones. Checkpoints and undos are extremely useful
here, since they allow you to try out different paths without losing too much time if you mess up. Larger sizes are more
difficult in the sense that there's more you have to work with, but it's still possible to fluke a good single or even
small average without much experience if you can find the solution quickly.

Using circles and arrows can be a bit of a slowdown, but there are still some cases where they are useful. Placing a circle
on pieces that are unable to move can help with narrowing down the path a bit. Additionally, arrows can be useful for
pieces that have a very limited amount of moves available.

If you're trying out paths, it's important to be able to tell when you hit a dead end, and reach a state where solving the
puzzle is impossible. Using a depth-first search approach can sometimes be helpful, but is ultimately slower most of the
time, and it's better to practice getting the correct solutions without resorting to bruteforcing.