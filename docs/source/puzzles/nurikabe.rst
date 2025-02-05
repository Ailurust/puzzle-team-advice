Nurikabe
========

Rules
-----

(sourced from `puzzle-nurikabe.com <https://www.puzzle-nurikabe.com>`_)

* You have a grid of squares; some cells of the grid start containing numbers.
* The goal is to determine whether each of the cells of the grid is "black" or "white"
  (Islands in the Stream calls these "water" and "land" respectively).
* The black cells form "the nurikabe" (Islands in the Stream calls it "the stream"):
  they must all be orthogonally contiguous (form a single polyomino),
  number-free, and contain no 2x2 or larger solid rectangles (Islands in the Stream calls such illegal blocks "pools").
* The white cells form "islands" (which is where Islands in the Stream got its name):
  each number n must be part of an n-omino composed only of white cells.
* All white cells must belong to exactly one island; islands must have exactly one numbered cell.

Options
-------

* “Gray out completed numbers”
* “Highlight wrong numbers”
* “Highlight isolated blacks and 2x2 pools”

Introduction
------------

*(this and the next two sections of this page are sourced from qqwref's doc)*

Being fast involves a lot of intuition, from knowing what kind of shapes the puzzle generator likes, to feeling whether
a section is dense (so the islands should be closely packed and may contain 2x2 squares) or spare (so the islands should
be as far apart and placed so as to get near all possible walls), to being able to see how to fix a solution that’s almost
correct. At high speed you shouldn’t logically deduce the squares one by one, or mark the islands with dots, but instead
just see how the islands should look and draw the black squares around them.

Connectivity
------------

Each island has to have the specified number of white squares, and the islands can’t touch, so if you ever see two islands
that are diagonally touching or orthogonally 2 squares apart you can place a black square between them. If an island needs
more squares but only has one way to expand, add the squares there. All black squares also have to be touching, so whenever
a chunk of black cells only has one way to expand, add another square there. You can hold shift and hover over a black area
to see it, and if you block off a black area from the rest of the puzzle with dots it will get highlighted in red.

Complex Logic
-------------

I know two slightly more complex bits of logic. The first is that any square that cannot be reached by any island (that is,
it’s too far away from any of the number clues) is black, and this in combination with the no-2x2 rule will often give you a
square that is required to be white, and often can only possibly be linked to one of the clues. If it’s a straight line to
the clue, that’s a lot of squares for free. The other is that if a clue (or the only way for an island to expand) is only
open in two adjacent directions, then the square diagonally touching it in the open direction can’t be from another island,
and if there is only one remaining cell in the island (such as if the clue is a 2 in a corner), that diagonally touching
square must be black.

Prefilling
----------

Another useful strategy is to start off by immediately filling all empty cells with a black square, similar to the technique
on Hitori. From here, you can carve out the shapes of each island until you solve the puzzle. If you get something wrong,
just keep making small fixes until you eventually reach the correct solution. This relies much further on intuition, and
knowing what the generator tends to use goes a long way.