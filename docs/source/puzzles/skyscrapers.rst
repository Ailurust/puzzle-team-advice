Skyscrapers
===========

Rules
-----

(sourced from `puzzle-skyscrapers.com <https://www.puzzle-skyscrapers.com>`_)

* The objective is to place skyscrapers in all cells on the grid according to the rules:
  1. The height of the skyscrapers is from 1 to the size of the grid i.e. 1 to 4 for a 4x4 puzzle.
  2. You cannot have two skyscrapers with the same height on the same row or column.
  3. The numbers on the sides of the grid indicate how many skyscrapers would you see if you look in the direction of the arrow.
* Place numbers in each cell to indicate the height of the skyscrapers.

Options
-------

* “Highlight condition errors”
* “Highlight duplicates (errors)”
* “Highlight wrong notes (errors)”
* "Highlight same numbers"
* “Auto load pencil notes”
* "Auto remove notes"
* “Show number buttons” + “Gray out completed numbers”
* The "Squares" style can be helpful for spotting patterns.
* Setting a different default background color also helps.

*(adapted from qqwref's doc, with additional info by beatrixwashere)*

Introduction
------------

Skyscrapers is basically sudoku but without boxes and with additional constraints. On easy mode all constraints are shown,
but on other difficulties there are just enough to solve the puzzle. Unfortunately, when a constraint is violated it will
only show up as an error when you fill in the entire row/column, so sometimes when guessing, errors can lurk in the puzzle
for a while before you notice. The problem is that these constraints are actually really hard to get your head around,
which is why the regular difficulties cap out at 6x6.

Methodology
-----------

There are two obvious constraints: a 1 means the highest possible number is right next to the edge, and a constraint
equal to the puzzle size means the entire row/column is in order, ascending starting from the constraint. For the rest
of the constraints, you can eliminate some of the largest numbers from near the constraint. For instance, if there is a
4 constraint on a 6x6 puzzle, the first three squares can’t be 6, the first two can’t be 5, and the first one can’t be 4.
Also, on a 2 constraint on any puzzle size, the second square can’t be the second largest possible number.

The largest numbers usually matter the most. In a 2 constraint on a 6x6 puzzle, for instance, the first number must be
larger than any other number between it and the 6, which specifically means that the 5 is either on the first square or
after the 6. There is also some possible logic when two constraints affect the same row; if they add up to the size of
the puzzle plus one, then they tell you where the largest number is, and on either side of it the numbers must be in
decreasing order.

Because the largest numbers are the most important, you will probably start by looking for hidden singles on the largest
numbers. Naked pairs and triples pop up too. However, unless you have a perfect handle on the way the constraints work,
there’s going to be plenty of guessing on the harder difficulties.

The approach for easy puzzles is usually pretty simple. Most placements of the largest number are usually given without
requiring in depth logic, and can be placed right off the bat. From there, the comparisons can directly eliminate some of
the other large numbers, so can the outside for where this can be applied. From there, a couple naked pairs tend to be
needed for progression, along with a better look at some of the constraints, but past that the solution is clear. Other
difficulties can also utilize this approach, with normal puzzles requiring much more focus on techniques such as intersection
removal, as well as a better understanding of the constraints, and hard tends to require some bifurication as mentioned before.

.. note::

   The Sudoku page is not yet completed, which provides some context for understanding the logic behind this puzzle.
   When it is completed, it will be linked appropriately within this page.