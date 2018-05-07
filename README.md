Cthulhu
=======

Welcome to Cthulhu! Inspired by [Notpron][], Cthulhu is a puzzle game 
in a Git repository; it uses the whole repository, not just the files 
within it.

[Notpron]: http://notpron.org/notpron/

Requirements
------------

The first few levels will be playable through GitHub, but you will need 
a local copy of the repo to manipulate for the rest. Obtaining a local 
copy is the first task of Level 0.

To make use of that local copy, you will also need to install [Git][].

Knowledge of how to use Git is not required; you can learn as you go.

[Git]: https://git-scm.com/downloads

How to play
-----------

Cthulhu proceeds in levels. Each level has an associated level code, 
and your goal for each level is to find the code for the next level.

The starting point for each level is the branch `game/xxxxxxx/master`,
where `xxxxxxx` is the level's code. If the level requires you to switch
to a branch (e.g. `feat`), that branch will be prefixed with the level
code (i.e. `game/xxxxxxx/feat`).

Each level has a `README.md` file that contains the clue. Start there.

If a level branch has nothing in it (not even a README), then the level 
is not yet finished. See the Updates section below.

Searching man pages and the Internet for Git techniques is allowed and 
encouraged, but resist the temptation to cheat! As David Münnich said 
in the Notpron hints, "It's easy to find cheats on the internet, but 
from the moment of your first cheating on, the whole fun is gone, stay 
strong!"

Updates
-------

This game is a work in progress and new levels will be published. To 
get these new levels, run `git pull --rebase` in the last level you 
encountered.

* * *

Level 0
=======

Clone the repo.

Check out the next level: `levelone`

Hint
----

If you don't know how to do something, look it up! You will probably be 
able to find everything you need on the [Git website][gitdoc].

[gitdoc]: https://git-scm.com/doc
