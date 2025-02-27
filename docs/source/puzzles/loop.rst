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

*(parts of this document are sourced from qqwref's doc)*

Terminology
------------

In the interest of effective communication, let's take a moment to establish the terminology I'll be using in this guide.

|ico13|

In the above image, the highlighted dot is "shared" between the x and the y. The line "belongs to" y, and is "pointing at" x.

|ico14|

Here, the line is "exiting" from the y via the highlighted dot, and "entering" the x via that dot. To explain this, we need to
look at our first piece of logic.


Basic Loop Logic
-----------------

Because any line segment in the puzzle must be part of the same closed loop, we know that dots must have either zero or two
lines. Three or four lines would result in a cross, and one line would cause a break in the loop. 

.. image:: ../img/loop/loop1.png

Thus, any time you draw a line connected to a dot, you will at some point need to add another line to that same dot. Thinking
about this in terms of entering and exiting a dot will help us identify some patterns.

Any line that enters a point must be able to exit it, so looking for dead-ends can show us where to place Xs. 

|ico15| |ico16|

Most of the examples in this guide come are presented using ghost lines mode, but I've included some penpa+ examples as well.
The dead-end in both images is the same, because we are unable to place lines around the 0s, the dots that they share have only
one eligible direction to place a line. If we were to place a line in this spot, it would enter but have no way to exit, so we 
know that the remaining direction is an X as well.

|ico17| |ico18|

In addition, we can think of dots around the border of the puzzle as having Xs in the directions we can't see. As a result, we
can place a few more Xs using the same logic. Ghost lines mode makes this quite clear, since we can see that a line in those
spots would not have anywhere to go. Since the edges of the puzzle are more constrained, they're a good place to start a solve.


Corners
-------

Using the same idea as above, we can make some quick deductions about the corners of the puzzle. We will also start to look at
the properties of each number and how they differ.

|ico19| |ico20| |ico21| |ico22|

A 2 or 3 in the corner of the puzzle give us some lines that we can place immediately. This logic follows from the loop properties
we discussed earlier, in combination with the properties of 2s and 3s. Each clue has a number of possible configurations. 1s and 3s
have four each, while 2s have six. 0s only have one. 

.. image:: ../img/loop/loop9.png

Let's take a moment to try each possible 3 configuration in a corner, and see what we can learn. 

|ico25| |ico26| |ico27| |ico28| |ico29|

It is helpful to think of both the number of lines around a clue as well as the number of blank sides. Consider that a 
3 will only have one open edge. In the first and second images, where the blank spaces are touching the corner dot, we
end up with a line that has nowhere to go (a dot with only one line). This means that our blank side cannot be either
side that touches that dot. As a result, we know that those sides will be lines. In fact, any time you see a 3 with one
corner blocked like this, you can place these lines. 

|ico30| |ico31| |ico32|

As you might have guessed, a line entering a "corner" dot like this will have to exit on the same cell, forming an "L"
shape. Let's try to apply this now to a 2 in a corner. Out of the 6 possible configurations for a 2, we can immediately
rule out the parallel line options, since they would leave us with a line that has nowhere to go. Out of the remaining
configurations, there are two valid options for a given corner cell, depending on it's location.

|ico33| |ico34| |ico35|

Although no lines from these cases overlap, we can still place some which we know must result from either layout. This
sort of "flip-flop" that we get from 2s has a wide range of uses, which we will revisit later.

With these basic patterns under your belt, you should be able to complete this `example puzzle <https://swaroopg92.github.io/penpa-edit/#m=solve&p=vZRNb6M8EMfvfArksw8EQptyy9NN9tKn+9ZVVVkocojboJiQNbCNiNLP3pkhWWqg0u5hVw6j4Yc9Hnvmn+JHJY3iIYxgwj0+guH7E3rGHv7O4y4ttYpctZfZTitX5/nOHfFpVa5zE7ky1ZWpCs4TLYsiTdxCp+VaGZ1uN66ptCr4p/mcP0pdKEecYsaOYD7jbASPz+KXevYi8CWInUP9NTrUi0jER15/b91J636LDmBvowPzRywSzGOQOyyPIZjfBQECCP0LjBEELQg8BJDNGYQ9cNFZEl52goaTzrbhlQUg3REl/UB2TtYnewdn4nVA9gNZj2xI9obmzMjek70mOyZ7QXMu8VYcR/hNEXGEv+dBGeDCWZHrRVGZR5koFlGhOLFtlS2VsRAWHyprz0uftrlRg58QqtUTwNJU1vRlblYYvOXPUmtrcdOiFkpSk2gblSa13qUx+bNFMlmuLbCUJbR0sU53diS1Le0ESmkfX25kZ7esPfHRYXtGjwjgdsfYy1dRPeX1x6afzu3O6y/QzP9H9Qx7WTDoEio1tZQP7qx17+k7etenlvPAvz354D6A29zK4qYhnyNR33GG+/xHq9FlWf4TEqVl9J7k2RKOItiby2i+FNUq31TnDsfenb6fbtCmi26TLnp/K13spv1QplfxsamA90f/If9AmvuTxnIzKDPAA0oDOqioE29EZfOegHDDvoaADsgIaFdJgPpiAtjTE7B3JIVRu6rCrLrCwq162sKt3spLxM4r&a=NZDNDcYwCEN3yTmHGL6fZpaq+69ROxgpEi8uvIje9zN1BtaaWJgY07zNzMD74Q85zV8y74fZi6tYvbBHFWFm7VnNRTPn4m+mJ/zWYTuVhZ2qYadqdk5fdk5f/sx0pP3q7R59d765ilYr3DWooh1H/SCd5wU=>`_.

3s
---

3s can often give us lines at a glance, especially when they appear together. First, let's take the corner 3 we looked at
previously. We know we where two of the lines will be, but this also gives us information about the dot in the open corner
of the cell.

|ico43| |ico44| |ico45|

Wherever we place the last line to complete the 3, we will be left with a line exiting via the green dot. Put another way,
there will need to be a line entering the 3 via that dot.

As it turns out, we could make this deduction in reverse as well. When we know a 3 has a line entering from one corner, we
can place lines forming the L-shape on the opposite corner. A 3 cell will have only one open edge. If this open edge is not
touching the corner with the incoming line, then you will end up with three lines on that dot, which is not allowed. This 
means that one of the edges touching that corner must be open, and since we only have one open edge, the edges which don't
touch that dot must have lines. Additionally, since we know that the other line on this dot will belong to the 3, the last 
available direction will be an X.

|ico46| |ico47| |ico48| |ico49|

We can also think about this in terms of lines entering cells. A 3 has two corners with two lines each and two corners with 
one line each (touching the open edge). If a line is entering a 3 square, it must enter one of the corners with one line,
therefore the opposite corner of the 3 has two lines. 


This brings us to a common pattern, diagonally adjacent 3s. We know that the shared dot must have two lines, since there are
no possible 3 configurations that involve dots with no lines. If we let both lines on this shared dot belong to only one of
the 3s, the other would be left with zero on that dot, eliminating all possible 3 configurations. Thus, we know that a line 
will enter one 3 and exit the other on this dot. It is helpful to think of the 3s here in the same way that we thought of the
line in the previous example. Each 3 acts as an incoming line to the other 3, meaning the opposite corners must be lines.

|ico50| |ico51| |ico52|

In general, we must avoid having a corner pointing into a 3, since we would then be able to place at most two lines out of three.


Another common 3 pattern, which is often helpful when beginning a solve, is orthogonally adjacent 3s. If we leave the edge shared
by both 3s empty, we will end up with an isolated loop, so we know that line must be marked. If we leave the edges on a given end
(parallel to that middle line) of the group empty, the other 3 will not have enough spaces for all it's edges. Thus, we can mark 
these lines as well. 

|ico53| |ico55| |ico54|

This pattern can extend over any number of orthogonally adjacent 3s. We can mark the lines we know and come back later once we have
more information. Once any of the uncertain edges are determined, all of the 3s in the group can be solved, since there are only two
valid configurations.

|ico56| |ico57| |ico58| |ico59|


1s
---
A 1 will be surrounded by one line and three Xs. If the line connects to a dot shared with a 0, you will not be able to add
the second line (remember, a dot must have either zero or two lines) to that dot without overloading the 1. 

|ico1| |ico2| |ico3|

To rephrase, a 1 has one line, but this also means that two of the corners will have two X’s each, so if for instance
a 1 is diagonally next to a 0, the two edges next to the 0 must be X’s because they can’t both be lines. 


2s
----

In any of the possible 2 configurations, you will end up with lines exiting on two opposite corners. What this means to
us is that when we have a line that definitely enters a 2, we know that the 2 will have a line exiting on the opposite
corner. If it didn't, you would end up with either too many or too few lines on the cell. In the image below, we can see
that the green dot has exactly one line entering it from the partially completed 2. As a result, there will be exactly
one line exiting from the blue dot.

|ico36| |ico37|

|ico38| |ico39|

If we tried the configurations that would not result in a line exiting the blue dot, we can see that either option will
break the top 2. It would either be forced to have too many lines (since otherwise we have a dead end), or have no space
for it's second line. We will revisit this later, but this knowledge lets us place two Xs on the diagonally adjacent 1.

|ico40|

What you may have noticed in the above image is that we could make the same deduction about the 1 if it had been directly
next to the first 2. As it turns out, diagonally adjacent 2s essentially propagate their corners through to the end of 
the chain. We could have any number of 2s between the initial 2 and the 1, and we would still be able to place those Xs!

A common instance of this type of propagation is an L-shaped corner pointing at a chain of 2s.

|ico41| |ico42|



.. note::

   This section is under construction. See the
   `Contributing page <https://puzzle-team-advice.readthedocs.io/en/latest/contributing.html>`_ to learn how to contribute.


.. |ico1| image:: ../img/loop/loop2.png
   :class: no-scaled-link
   :width: 30%
.. |ico2| image:: ../img/loop/loop3.png
   :class: no-scaled-link
   :width: 30%
.. |ico3| image:: ../img/loop/loop4.png
   :class: no-scaled-link
   :width: 30%

.. |ico13| image:: ../img/loop/loop21.png
   :class: no-scaled-link


.. |ico14| image:: ../img/loop/loop22.png
   :class: no-scaled-link

.. |ico15| image:: ../img/loop/loop23.png
   :class: no-scaled-link
   :width: 45%
.. |ico16| image:: ../img/loop/loop24.png
   :class: no-scaled-link
   :width: 45%

.. |ico17| image:: ../img/loop/loop25.png
   :class: no-scaled-link
   :width: 45%
.. |ico18| image:: ../img/loop/loop26.png
   :class: no-scaled-link
   :width: 45%

.. |ico19| image:: ../img/loop/loop27.png
   :class: no-scaled-link
   :width: 22%
.. |ico20| image:: ../img/loop/loop28.png
   :class: no-scaled-link
   :width: 22%
.. |ico21| image:: ../img/loop/loop29.png
   :class: no-scaled-link
   :width: 22%
.. |ico22| image:: ../img/loop/loop30.png
   :class: no-scaled-link
   :width: 22%

.. |ico23| image:: ../img/loop/loop31.png
   :class: no-scaled-link
   :width: 45%
.. |ico24| image:: ../img/loop/loop32.png
   :class: no-scaled-link
   :width: 45%

.. |ico25| image:: ../img/loop/loop33.png
   :class: no-scaled-link
   :width: 18%
.. |ico26| image:: ../img/loop/loop34.png
   :class: no-scaled-link
   :width: 18%
.. |ico27| image:: ../img/loop/loop35.png
   :class: no-scaled-link
   :width: 18%
.. |ico28| image:: ../img/loop/loop36.png
   :class: no-scaled-link
   :width: 18%
.. |ico29| image:: ../img/loop/loop37.png
   :class: no-scaled-link
   :width: 18%

.. |ico30| image:: ../img/loop/loop42.png
   :class: no-scaled-link
   :width: 30%
.. |ico31| image:: ../img/loop/loop44.png
   :class: no-scaled-link
   :width: 30%
.. |ico32| image:: ../img/loop/loop43.png
   :class: no-scaled-link
   :width: 30%

.. |ico33| image:: ../img/loop/loop48.png
   :class: no-scaled-link
   :width: 30%
.. |ico34| image:: ../img/loop/loop49.png
   :class: no-scaled-link
   :width: 30%
.. |ico35| image:: ../img/loop/loop50.png
   :class: no-scaled-link
   :width: 30%

.. |ico36| image:: ../img/loop/loop51.png
   :class: no-scaled-link
   :width: 45%
.. |ico37| image:: ../img/loop/loop52.png
   :class: no-scaled-link
   :width: 45%

.. |ico38| image:: ../img/loop/loop53.png
   :class: no-scaled-link
   :width: 45%
.. |ico39| image:: ../img/loop/loop54.png
   :class: no-scaled-link
   :width: 45%

.. |ico40| image:: ../img/loop/loop55.png
   :class: no-scaled-link

.. |ico41| image:: ../img/loop/loop56.png
   :class: no-scaled-link
   :width: 45%
.. |ico42| image:: ../img/loop/loop57.png
   :class: no-scaled-link
   :width: 45%

.. |ico43| image:: ../img/loop/loop58.png
   :class: no-scaled-link
   :width: 30%
.. |ico44| image:: ../img/loop/loop59.png
   :class: no-scaled-link
   :width: 30%
.. |ico45| image:: ../img/loop/loop60.png
   :class: no-scaled-link
   :width: 30%

.. |ico46| image:: ../img/loop/loop61.png
   :class: no-scaled-link
   :width: 18%
.. |ico47| image:: ../img/loop/loop62.png
   :class: no-scaled-link
   :width: 18%
.. |ico48| image:: ../img/loop/loop63.png
   :class: no-scaled-link
   :width: 18%
.. |ico49| image:: ../img/loop/loop64.png
   :class: no-scaled-link
   :width: 18%

.. |ico50| image:: ../img/loop/loop65.png
   :class: no-scaled-link
   :width: 30%
.. |ico51| image:: ../img/loop/loop66.png
   :class: no-scaled-link
   :width: 30%
.. |ico52| image:: ../img/loop/loop67.png
   :class: no-scaled-link
   :width: 30%

.. |ico53| image:: ../img/loop/loop68.png
   :class: no-scaled-link
   :width: 30%
.. |ico54| image:: ../img/loop/loop69.png
   :class: no-scaled-link
   :width: 30%
.. |ico55| image:: ../img/loop/loop70.png
   :class: no-scaled-link
   :width: 30%

.. |ico56| image:: ../img/loop/loop71.png
   :class: no-scaled-link
   :width: 18%
.. |ico57| image:: ../img/loop/loop72.png
   :class: no-scaled-link
   :width: 18%
.. |ico58| image:: ../img/loop/loop73.png
   :class: no-scaled-link
   :width: 18%
.. |ico59| image:: ../img/loop/loop74.png
   :class: no-scaled-link
   :width: 18%