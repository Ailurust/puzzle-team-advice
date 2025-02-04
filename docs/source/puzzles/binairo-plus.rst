Binairo+
========

Rules
-----

(sourced from `puzzle-binairo.com <https://www.puzzle-binairo.com/binairo-plus-6x6-easy>`_)

* Binairo+ is played on a rectangular grid with no standard size.
* Some cells start out filled with black or white circles. The rest of the cells are empty. 
* The goal is to place circles in all cells in such a way that:

  1. Each row and each column must contain an equal number of white and black circles.
  2. More than two circles of the same color can't be adjacent.
  3. Two cells with a "=" sign between them should contain circles of the same type.
  4. Two cells with a "x" sign between them should contain circles of the opposite type.

Options
-------

* “Highlight 3 in a row of the same color”
* “Highlight more than allowed of the same color”
* “Highlight comparison errors”
* “Prominent errors”
* “Show counters” + “Count remaining”
* The "Squares" style can be helpful for spotting patterns.
* Setting a different default background color also helps.

Introduction
------------

As the name suggests, Binairo+ is essentially the same puzzle as normal Binairo, except the "no duplicate rows/columns"
rule is replaced with the "x" and "=" comparisons. This introduces some new logic, and eliminates a lot of the guesswork
that came with the duplicate rule. I highly recommend checking out the
`guide for normal Binairo <https://puzzle-team-advice.readthedocs.io/en/latest/puzzles/binairo.html>`_ before continuing
reading this one.

Basic Logic
-----------

The most trivial deductions are filling in an incomplete comparison, such as a black circle on an x with a white and blank
cell, or a black circle on an = with a black and blank cell (same applies for swapped colors). Another useful piece of
logic that might not be immediately obvious is that a = next to a filled cell in the same row/column must have the opposite
color on both ends, since it would otherwise form three of the same color in a row. Finding deductions like these quickly
is very important to speedsolving.

It's also common for chains of x's or ='s to appear, which can be especially rewarding. If you find a chain of x's, simply
alternate between colors until you reach the end. = chains are usually in the same row/column, and the same alternating
logic applies except with pairs of two of the same color rather than alternating one by one.

Advanced Logic
--------------

The same counter logic from normal Binairo also applies here, with the comparisons adding some further depth on where
certain colors are forced. Here's one example (rotated to fit the page better, counter is 1 black left and 3 white left):

.. image:: ../img/binairo-plus/xforce.png

Trying to apply the original counter logic doesn't help in this scenario, but since the x comparison requires one black cell
and one white cell, the empty cells outside of it can be colored white, since there will be 2 whites left regardless of how
the black and white in the x is placed. There are also some other cases of counter logic that have to do with multiple of
these comparisons in the same row/column. One example with x's is when a counter reads N | X (and vice versa) with a chain
of 2N cells being connected by x's, and the rest can be filled with the X color greater on the counter. On the other hand,
one example with ='s is that when a counter reads N | N+X (and vice versa), and every cell in the row/column is part of an
= comparison apart from X cells (usually this is one or two), the spare cells can be filled with the greater color.