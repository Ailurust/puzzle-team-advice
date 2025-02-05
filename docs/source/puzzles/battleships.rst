Battleships
===========

Rules
-----

(sourced from `puzzle-battleships.com <https://www.puzzle-battleships.com>`_)

* You have to find the location of the battleships hidden in the grid. Some battleships may be partially revealed.
* A battleship is a straight line of consecutive black cells.
* The number of the battleships from each size is shown in the legend below the grid.
* Two battleships cannot touch each other (even diagonally).
* The numbers outside the grid show the number of cells occupied by battleships on that row/column.

Options
-------

* "Highlight errors"
* “Highlight completed”
* “Show counters” + “Count remaining”
* “Show ship helper on the right”
* “Auto place water on ship corners”

Technique and Logic
-------------------

*(the remainder of this page is sourced from qqwref's doc)*

Start by handling the givens: a circle (1-segment ship) needs water all around it,
a D shape (ship end) needs one ship segment on the square side and water on the circle side,
and a square (ship middle) needs one ship segment on either left and right or up and down.
You can almost always immediately tell what to do with the squares from the counters, but if not, just skip that one.

Then, click on all the grayed out counters to clear those rows/columns. If you notice one of these later,
you can also click on it to fill it with water, or just fill it in manually. Also, if at any time you see a
row or column with exactly as many blank squares as remaining ship segments, you can fill them all in with ship
segments (but you always have to do that manually).

The last thing to know is to start from the largest ships that are still needed, and figure out where to place them.
For instance, on a 10x10 puzzle, you can continue by locating all places where a 4-segment ship could fit - either a
series of four empty cells, or an unfinished ship that has enough extra segments in its row/column to add up to
length four. Next, look for two places for a 3-segment ship. The ship helper saves time by telling you exactly how much
you need to look for.

Hard Puzzle Technique
---------------------

On harder puzzles you may have to guess where to place the largest ships, and there is some technique to making good guesses,
like knowing that placing a ship of size N will fill a stretch of N+2 squares with water on the two adjacent rows/columns
(which might make it impossible to fill them). Related to that, the only way to fit 2 segments in a 2x2 region is with a
2-segment ship. Also, if one type of ship is completely used up, you can use that to your advantage. For instance, if the
2-segment ships are used, then whenever you see 2 segments in a row with one end blocked off, you can add a third one
to the other end. And if the 1-segment ships are used, then any blank square completely surrounded by water must also
be water.