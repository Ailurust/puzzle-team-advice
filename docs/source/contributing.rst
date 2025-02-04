Contributing
============

This page covers how you can make changes to the documentation.
You're also welcome to ask me to change something through the Discord server,
but here I'm focusing on how you can edit it yourself.

Workflow
--------

1. Create a GitHub account if you don't already have one.
2. Fork `this repository <https://github.com/beatrixwashere/puzzle-team-advice>`_
   using the button in the top right.
3. Once you're done modifying the source, create a pull request.
   For now, simply merge into the main branch.
   Read the Docs also has a feature where you can see what the docs look like with the changes.
4. I check GitHub relatively often and will probably see the pull request at some point,
   but you're also welcome to let me know you made it.
5. After I've reviewed the changes, I'll merge it into the main branch,
   and the changes will appear once the automated build is done.
   As of right now, I'm the only one with permission to merge, but if anyone else is willing to
   help with uploading appropriate changes then please contact me.

Thanks for being willing to help out! If you have any questions about this process, again just ask me.

Structure
---------

The project structure is relatively simple, and you can ignore everything outside of ``docs/source``. The documentation
uses ``.rst`` files for its pages, and you can find a guide to the formatting techniques
`here <https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html>`_. This page, as well as the index and
getting started pages, are in the root of the source folder (ignore ``conf.py``). Pages for each puzzle are stored in
the ``puzzles`` folder, and are visible on the sidebar in the site by being listed in the index toctree. Images for the
guides are stored in the ``img`` folder, with separate subfolders for each puzzle.

Conduct
-------

This project follows the Contributor Covenant, which can be found in the root of this repository, as well as
`here <https://www.contributor-covenant.org/>`_. Aside from that, please provide credit when you're adding content that
isn't your own, and do not propose contributions to the wiki that paint other users in a negative light.