Pipes
=====

Rules
-----

(sourced from `puzzle-pipes.com <https://www.puzzle-pipes.com>`_)
* The goal is to rotate the tiles on the grid so all pipes are connected in a single group.
* Closed loops are not allowed.

Options
-------

* "Highlight errors" - *recommended on*
* "Animate rotation"
* "Invert rotation"
* "Long press for pin" - *recommended off*
* "Use Ctrl for pin" - *recommended on*
* (wrap) "Highlight wrap connectors"
* (wrap) "Show wrap tiles" - *recommended on*
* "Visualize flood"
* "Flood from current cell"
* "Rotate board"
* "Pin multiple tiles when dragging" - *recommended on*

Nick wrote the original guide which has inspired this one, it can be found `here <https://docs.google.com/document/d/1LU-BEMRuytWNwna_vpiTioyDCq60ai6hdmeS_TU3OmI/edit>`_.

Introduction
------------

Pipes is played on a square grid of tiles with 1 to 3 *half-edges* each: the bulb, with 1; the line, with 2; the turn, with 2; and the T, with 3.

|tilenames| 

If you counted the number of half-edges in an n by n board, you would find 2(n^2 - 1) half-edges (this is always true on the puzzleteam site, but not a necessity). Starting from any given tile, it takes 2 half-edges to connect to another tile, and by rule 1, the tile has to connect to every other tile, of which there are n^2 - 1. This means that none of the half-edges can be wasted: every pair is either connecting two tiles together, or empty. The rest of this guide will predominantly talk about edges, which are pairs of half-edges.

I refer to edges as "filled" if they connect two tiles together, and "empty" if they don't.

Basic Strategy
--------------

I will walk through an example solve on a 7 by 7 non-wrap board.
At the start, boards look like this:

|7by7step0|

Right now, the colors don't mean anything. The tile with the red circle is called the origin, and every tile connected to the origin is colored blue.

The first edges you can find on a non-wrap board are on the edge of the board. Since half-edges can't be wasted, there are empty edges all around it.

T and line tiles with an empty edge (in this case the edge of the board) are uniquely determined because they only have one orientation where the half-edges match. I've pinned them using CTRL-click. Pinning is very useful when learning basic strategy, but isn't required.
|7by7step1|
Although I've used all the empty edges on the border I can, the tiles I've solved give me more known edges. Since half-edges have to match, the edges of tiles I've solved transfer over to neighboring tiles.

I like to finish the border before going deeper into the center when I can. Bulb and line tiles with a filled edge are uniquely determined because they only have one orientation where the half-edges match. 
|7by7step2|
Turns are weirder to solve than the other tiles. If you look at all 4 ways to rotate a turn, whenever there's a filled edge on one side of it, there's an empty edge on the opposite side, but the other axis could flip either rway. So one edge won't do, you need 2 edges on different axes to fully solve it. This happens whenever the turn is in a corner (you can imagine the border to be all gray so that it looks like a corner).
|7by7step3|
More deductions can be made on the border.
|7by7step4|
When any tile is surrounded by 3 edges (the border counts as an empty edge), it can be solved.
|7by7step5|
Two more tiles will solve the border.
|7by7step6|
Lines are a special case: they can be oriented with just 1 edge, filled or empty. And when lines are next to eachother, the edges one give off determine the ones next to it (and so on), so they all share the same orientation. This solves a good number of tiles.
|7by7step7|
Which cascades:
|7by7step8| |7by7step9| |7by7step10| |7by7step11|
Which solves the puzzle.

All in all:
* Any tile with 3 known edges can be solved
* Ts can be solved with 1 empty edge
* Bulbs can be solved with 1 filled edge
* Lines can be solved with 1 of any edge
* Turns can be solved with 2 edges on different axes (in a corner)
* The border of a non-wrap board counts as an empty edge

More Strategy
-------------

The above often won't be enough to fully solve a board, but there is more logic.

**Half Fixed Turn**
The edges on opposite sides of a turn are always oppositely filled. So even if you don't have a turn fully solved, it can still give you one edge. Take for example this board:
|hard7by7step1|
This logic can be applied to the second turn on the top row. Because there's an empty edge on the top, there must be a filled edge on the bottom. This filled edge solves the line:
|hard7by7step2|
The logic can be applied again on the turn below the line. Since there's a filled edge on top of it, there must be an empty edge on the bottom. The empty edge solves the T.
|hard7by7step3|
That gives enough information to get to this state:
|hard7by7step4|
**Bulbs next to bulbs**
If 2 bulbs are next to eachother, there must be an empty edge between them. If there was a filled edge, they would connect to eachother, but not the rest of the board, which violates rule 1. This makes those bulbs walled in on 3 sides, which solves them and then the Ts.

**Loops**
|loop7by7step1|
3 of the edges of a loop are already pinned:
|loop7by7step2|
So by rule 2, the last edge must be empty
|loop7by7step3|
Which pins the Ts next to it.
|loop7by7step4|
This type of loop with 2 pinned Ts, called the square, is quite common. But loops can come in many different shapes and sizes.
As a side note, the "no loops" rule can technically be deduced from the fact that you can't waste any half-edges.

Various Patterns
----------------

**Flower Patch**
|flowerpatch|
Bulbs can't be connected directly to other bulbs, so if one's next to 3 others, it faces outwards.

**Garden**
|garden|
If an area of tiles is surrounded by bulbs (or known empty edges) except for one opening, any path to connect tiles inside it to tiles outside it must go through that opening. The opening must be filled.

**Barbell**
|barbell|
If a line (or chain of lines) is in-between two bulbs, it can't connect them together.

**Corner Loop**
|cornerloop|
At least one of the edges of any potential loop has to be empty. If you consider a small loop around a corner, and you already have 2 filled edges, there's at least one empty edge in the tile diagonally outwards from the corner. "At least one empty edge" is enough to deduce that the rest of the edges of a T are all filled. These 2 edges can form another corner to continue chaining the pattern.

**2x2**
|2by2|
This arrangement of tiles guarantees 6 edges. There are variations on it, but they are much less common.
(The line will be in one of two rotations, which fixes a bulb, which fixes the T, which fixes the other bulb, so the whole system only has two rotations. In all cases those edges persist)

**Row/Column Parity**
|parityexample|
Lines and turns can connect multiple edges horizontally or vertically. In small wrap sizes, they sometimes connect one edge of a tile to the opposite edge of that tile by wrapping around the entire board. If that tile is a T or a bulb, you can solve for 2 edges on it.
* If there are an even number of turns and the piece is a T, the edges are parallel to the row/column, and filled.
* If there are an odd number of turns and the piece is a T, the edges are perpendicular to the row/column, and filled.
* If there are an even number of turns and the piece is a bulb, the edges are parallel to the row/column, and empty.
* If there are an odd number of turns and the piece is a bulb, the edges are perpendicular to the row/column, and empty.

.. |tilenames| img:: ../img/pipes/tilenames.png
   :class: no-scaled-link
.. |7by7step0| img:: ../img/pipes/7by7step0.png
   :class: no-scaled-link
.. |7by7step1| img:: ../img/pipes/7by7step1.png
   :class: no-scaled-link
.. |7by7step2| img:: ../img/pipes/7by7step2.png
   :class: no-scaled-link
.. |7by7step3| img:: ../img/pipes/7by7step3.png
   :class: no-scaled-link
.. |7by7step4| img:: ../img/pipes/7by7step4.png
   :class: no-scaled-link
.. |7by7step5| img:: ../img/pipes/7by7step5.png
   :class: no-scaled-link
.. |7by7step6| img:: ../img/pipes/7by7step6.png
   :class: no-scaled-link
.. |7by7step7| img:: ../img/pipes/7by7step7.png
   :class: no-scaled-link
.. |7by7step8| img:: ../img/pipes/7by7step8.png
   :class: no-scaled-link
.. |7by7step9| img:: ../img/pipes/7by7step9.png
   :class: no-scaled-link
.. |7by7step10| img:: ../img/pipes/7by7step10.png
   :class: no-scaled-link
.. |7by7step11| img:: ../img/pipes/7by7step11.png
   :class: no-scaled-link
.. |hard7by7step1| img:: ../img/pipes/hard7by7step1.png
   :class: no-scaled-link
.. |hard7by7step2| img:: ../img/pipes/hard7by7step2.png
   :class: no-scaled-link
.. |hard7by7step3| img:: ../img/pipes/hard7by7step3.png
   :class: no-scaled-link
.. |hard7by7step4| img:: ../img/pipes/hard7by7step4.png
   :class: no-scaled-link
.. |loop7by7step1| img:: ../img/pipes/loop7by7step1.png
   :class: no-scaled-link
.. |loop7by7step2| img:: ../img/pipes/loop7by7step2.png
   :class: no-scaled-link
.. |loop7by7step3| img:: ../img/pipes/loop7by7step3.png
   :class: no-scaled-link
.. |loop7by7step4| img:: ../img/pipes/loop7by7step4.png
   :class: no-scaled-link
.. |flowerpatch| img:: ../img/pipes/flowerpatch.png
   :class: no-scaled-link
.. |garden| img:: ../img/pipes/garden.png
   :class: no-scaled-link
.. |barbell| img:: ../img/pipes/barbell.png
   :class: no-scaled-link
.. |cornerloop| img:: ../img/pipes/cornerloop.png
   :class: no-scaled-link
.. |2by2| img:: ../img/pipes/2by2.png
   :class: no-scaled-link
.. |parityexample| img:: ../img/pipes/parityexample.png
   :class: no-scaled-link
