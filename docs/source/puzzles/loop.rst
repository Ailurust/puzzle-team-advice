Loop (Slither Link)
===================

Rules
-----

(sourced from `puzzle-loop.com <https://www.puzzle-loop.com>`_)

* You have to draw lines between the dots to form a single loop without crossings or branches.
* The numbers in each cell indicate how many lines surround it.

Options
-------

* “Auto cross the sides of completed numbers”
* “Gray out completed numbers”
* “Highlight wrong numbers”
* "Highlight wrong moves"
* "Draw continuous line"
* "Ghost lines mode" - *Visual change, blank spaces instead of Xs. This is up to preference.*

Basic Logic
-----------

*(the remainder of this page is from qqwref's doc, adapted by ailurus)*

Slither Link is a very complex and deep puzzle. Fortunately, the generator on Puzzle Team (the same one as Simon Tatham,
as far as I know) is relatively simple. This means that the puzzles here are always solvable without guessing, and the 
number of patterns are relatively limited. Marking X’s makes things easier, so going fast, especially on normal, will
mean using as few X’s as possible.

Because any line segment must be part of the single closed loop, we know that dots must have either zero or two lines.
Three or four lines would result in a cross, and one line would cause a break in the loop. 
.. image:: ../img/loop/loop1.png

The next most obvious logic is looking at a single number at a time. A 0 has four X’s and they will all be automatically
marked, so that’s a good place to start. A 1 obviously has one line, but this also means that two of the corners will
have two X’s each, so if for instance a 1 is diagonally next to a 0, the two edges next to the 0 must be X’s because they
can’t both be lines. 
|ico1| |ico2| |ico3|

To rephrase, a 1 will be surrounded by one line and three Xs. If the line connects to the dot shared with the 0, you will
not be able to add the second line to that dot without overloading the 1. 

A 2 has two lines, which are either in a = shape (one line exiting each corner) or an L shape (one line exiting two 
opposite corners, no lines exiting the other two corners).

A 3 has two corners with two lines each and two corners with one line each, so if a line is entering a 3 square, it must
enter one of the corners with one line and therefore the opposite corner of the 3 has two lines.
|ico4| |ico5|

Alternatively, consider that a 3 will only have one open edge. If this open edge is not touching the corner with the
existing edge, then you will end up with three lines on that dot. This means that one of the edges touching that corner
must be open, and since we only have one open edge, the edges which don't touch that dot must have lines. Since we know
that the other line on this dot will belong to the 3, the last available direction will be an X.

.. |ico1| image:: ../img/loop/loop2.png
   :class: no-scaled-link
   :width: 30%
.. |ico2| image:: ../img/loop/loop3.png
   :class: no-scaled-link
   :width: 30%
.. |ico3| image:: ../img/loop/loop4.png
   :class: no-scaled-link
   :width: 30%

.. |ico5| image:: ../img/loop/loop7.png
   :class: no-scaled-link
   :width: 45%
.. |ico4| image:: ../img/loop/loop6.png
   :class: no-scaled-link
   :width: 45%
