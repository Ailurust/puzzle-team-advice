Aquarium
========

Rules
-----

*(sourced from `puzzle-aquarium.com <https://www.puzzle-aquarium.com>`_)*

* The puzzle is played on a rectangular grid divided into blocks called "aquariums"
* You have to "fill" the aquariums with water up to a certain level or leave it empty.
* The water level in each aquarium is one and the same across its full width.
* The numbers outside the grid show the number of filled cells horizontally and vertically.

Options
-------

* "Highlight errors"
* "Auto flood water and air"
* "Highlight completed"
* "Show counters" + "Count remaining"
* "Thicker black borders" (recommended for visibility)

Introduction
------------

*(the remainder of this page is sourced from qqwref's doc)*

Aquarium is the rare puzzle where rows and columns don’t behave the same way.
This isn’t too difficult by itself, but it is something to be aware of.
The auto flood option is also really meaningful here, as it speeds up solves a lot,
but also means that misclicks often need to be undone with Ctrl+Z rather than just clicked again.

Basic Logic
-----------

The logic for rows is based around each region being a certain size, either all filled or all not filled,
and the choice of regions having to add up to the number on the left.
You can X out any regions that are bigger than the remaining number of cells, and flood any regions that are
bigger than the remaining number of X’s (this isn’t shown in the counters, but the total number of X’s
in the row will be the puzzle size minus the number on the left). If the areas aren’t all small,
you can also solve some rows with math, like how the only way to make 4 from areas of size 1, 2, and 3 is 1 + 3.
Parity can also be relevant if almost all the empty areas in a row are even. For instance, if the sum is 7 and
the areas have size 1, 2, 2, 4, and 4, the 1 must be flooded or else an odd sum can’t be made. Don’t forget that
areas aren’t necessarily continuous along a given row, so an area that looks small may actually contribute a
larger amount to the row.

Because row logic tends to be more powerful than column logic, for smaller/easier puzzles it’s good to start by
focusing on rows only, and only look at columns later. I like to start at the top row, because if there is useful logic
there then the water will flood downwards and save clicks. Starting from the bottom row can be fast too on some puzzles.
Remember that due to the flooding mechanic, after making a deduction, nearby rows are good places to look next.

The logic for columns is based around each region flooding from bottom up. If a region has more unsolved vertical space
than the remaining amount of water, you can add X’s to the top, and if it has more unsolved vertical space than the
remaining amount of X’s, you can add water to the bottom. Columns with clues close to 0 or close to the size
of the puzzle are the most valuable here, because most regions will be pretty small in vertical size. Because a single
unit of water can be added or subtracted, there’s no parity or math logic like with the rows, although it’s still true
that areas aren’t necessarily continuous along a column.

Advanced Logic
--------------

There is some more advanced and specialized logic involving two neighboring rows or columns.
For rows, most areas of water in the top row will flow into the bottom, and most areas of X will affect the top.
Sometimes this can let you rule out certain combinations, like it may not be possible for two specific areas
in the top row to have water at the same time. Typically this is useful when the top row has more water. For columns,
if most empty areas in the columns span both of them, then consider the areas that only affect one column,
and the difference between the amount of remaining water on each column. You may be able to decide that all
or none of the unbalanced regions on one side can be used, although it’s something you have to think through rather
than a firm rule.

15x15 Hard Tips
---------------

Recently mtanzer did a stream explaining some tips for Aquarium 15x15-hard, which is notoriously difficult,
and this enabled me to finish an average of 12 and get a decent single solve. Here’s a summary of what I learned:

* If a column needs water in almost all of the empty space, fill it in completely to see if it breaks nearby columns.
* When you click a row/column clue to X out the rest of that row/column, watch where the X’s get placed because
  those columns/rows may be important for the next step.
* 15x15-hard puzzles vary wildly in difficulty. If you want a good single or maybe a short average,
  reset until you find a puzzle that looks easy, and guess heavily if you get stuck. If you can’t do it quickly,
  move on. If you’re doing an average, expect 5-minute-long and hour-long puzzles.
* Everyone has to guess, and maybe even do nested guesses. Try to find guesses that strike a balance between giving
  a lot of immediate deductions, and still being useful if the guess turns out to be wrong. Use checkpoints
  so you can keep track of where you guessed.
* If you’re going for an average and mess up, start the puzzle over - the knowledge you gained about which rows/columns
  to look at will save you a lot of time getting back to where you were.
