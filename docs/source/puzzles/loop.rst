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


Each clue has a number of possible configurations. 1s and 3s have four each, while 2s have six. 0s only have one.

.. image:: ../img/loop/loop9.png


It is helpful to think of both the number of lines around a clue as well as the number of blank sides. Consider that a 
3 will only have one open edge. If this open edge is not touching the corner with the existing edge, then you will end
up with three lines on that dot. This means that one of the edges touching that corner must be open, and since we only
have one open edge, the edges which don't touch that dot must have lines. Since we know that the other line on this dot
will belong to the 3, the last available direction will be an X.

|ico4| |ico5|

We can also think about this in terms of lines entering cells. A 3 has two corners with two lines each and two corners
with one line each, so if a line is entering a 3 square, it must enter one of the corners with one line and therefore
the opposite corner of the 3 has two lines.

We can flip this idea around as well. Consider a 3 for which you have already deduced two lines forming a corner. What 
can we say about the dot opposite this corner? We know that it will have one line belonging to the 3, which means that
it will have one more line, which cannot belong to the 3. This brings us to a common pattern, diagonally adjacent 3s.

|ico6| |ico7|

It is helpful to think of the 3s here in the same way that we thought of the line in the previous example. Each 3 acts
as an incoming line to the other 3, meaning the opposite corners must be lines.


A 1 will be surrounded by one line and three Xs. If the line connects to a dot shared with a 0, you will not be able to add
the second line (remember, a dot must have either zero or two lines) to that dot without overloading the 1. 


 |ico1| |ico2| |ico3|

To rephrase, a 1 has one line, but this also means that two of the corners will have two X’s each, so if for instance
a 1 is diagonally next to a 0, the two edges next to the 0 must be X’s because they can’t both be lines. 




Finally, let's look at 2s. A 2 has two lines, which are either in a = shape (one line exiting each corner) or an L shape
(one line exiting two opposite corners, no lines exiting the other two corners).


A common pattern you will encounter with 2s is the propagation of the L shape. When a 2 is diagonally next to a bend, it
will have the opposite corner filled. A string of diagonal 2s will often fall into this pattern. 






.. |ico1| image:: ../img/loop/loop2.png
   :class: no-scaled-link
   :width: 25%
.. |ico2| image:: ../img/loop/loop3.png
   :class: no-scaled-link
   :width: 25%
.. |ico3| image:: ../img/loop/loop4.png
   :class: no-scaled-link
   :width: 25%

.. |ico5| image:: ../img/loop/loop7.png
   :class: no-scaled-link
   :width: 45%
.. |ico4| image:: ../img/loop/loop6.png
   :class: no-scaled-link
   :width: 45%

.. |ico6| image:: ../img/loop/loop13.png
   :class: no-scaled-link
   :width: 45%
.. |ico7| image:: ../img/loop/loop14.png
   :class: no-scaled-link
   :width: 45%