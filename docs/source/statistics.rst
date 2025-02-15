Statistics
==========

Introduction
------------

The site features a ranking system based on your placements in each puzzle, which is present on the statistics page,
the hall of fame pages, and after each solve if the stats card is shown. Although these are accessible to anyone,
an account is required in order to save your own statistics, which is highly recommended.

Terminology
-----------

* personal best (single): best time for one solve
* mean of 3 (mo3): best mean of three solves in a row
* average of 5 (ao5): best average of five solves, with the fastest and slowest solves dropped
* average of 12 (ao12): best average of twelve solves, with the fastest and slowest solves dropped

Hall of Fame
------------

The leaderboards are predominantly featured on the hall of fame pages, which cover every difficulty of every puzzle.
These have a full leaderboard for personal best times, monthly, weekly, and daily leaderboards for personal bests,
and the top 10 placements for each average. Additionally, after each solve, there's an option to submit to the hall
of fame, which places your time on the timed leaderboards, with only include the top 20 times submitted. The other
leaderboards automatically apply your times.

There is one more leaderboard on the hall of fame, which features the top three programmatic solver times. As the
name suggests. this option is available to those who create programs to automatically solve the puzzles on the site,
and it makes a space for these times to be featured. In the interest of preventing these times from entering the
main leaderboards, the exact process for this is not public, but here are some tips to guide you in the right direction:

* An HTTP request can be used to get the puzzle; use the ``api_token`` cookie to stay logged in.
* Use an HTTP POST request to get the puzzle; for more details, see the Network tab of Chrome's dev tools, or the equivalent for your browser.
* Parse the HTML to get the ``task``, solve the puzzle, and post the solution with an HTTP POST request (again, see the Network tab for details).
* Make sure to nclude the ``robot=1`` parameter when you're submitting the solution. There's also the option on the site to create a robot account.

Point System
------------

The overall rankings are based off a point system, with the ranks being determined by who has the most points.
Points are gained separately for every personal best, mean of 3, average of 5, and average of 12,
which applies to every difficulty of every puzzle. Points are correlated with where you place on each leaderboard
in terms of time, and is calculated by the formula ``score = log10(number of players / player rank)``. The points
for each category are added up for the final placement for that difficulty, the overalls for each difficulty are
added up for the final puzzle placement, and those are added up for the overall placement across every single puzzle.