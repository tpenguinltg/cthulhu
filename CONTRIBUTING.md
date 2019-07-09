Contributing Guidelines
=======================

**If you have not reached the last published level, don't read this 
yet! Go finish the game first.**

Thank you for your interest in contributing to Cthulhu! I hope you 
enjoyed it as much as I did making it. Due to the unusual nature of the 
repo, the processes for contributing are different from most other 
repos.

Adding a level
--------------

1. Obtain the code for the new level. Don't cheat; do this by playing 
   through the levels so you get a feel for what has already been done
   and what your new level should look like.
2. Fork this repo.
3. Create your level and push all of your level's branches. See 
   "Designing a level" for guidelines.
4. Add a non-spoiler hint to the `hints` directory in the `master`
   branch. This hint should be aimed at players who are stuck and need a
   little bit of an extra push. Use the existing hint files as examples.
5. Update the `latest` file on the `master` branch with your new level 
   number.
6. Create a pull request on this repo's `master` branch. List the next
   level code, any false level codes that your level has, and all level
   branches. Optionally add some additional notes, but don't provide a
   solution. Use the pull request template provided to help you.
7. Keep your fork available until your pull request is closed.
8. Be prepared to update your level in case your level needs work or 
   another level is accepted before yours. `git branch -m` is your
   friend.

Pull requests will be handled roughly in the order that they are made, 
but don't assume that a pull request will be accepted when making your 
level. If you do base your level on a pending pull request, base it on 
their fork and master commit, make it clear that you based it on a pull 
request, and be extra prepared to change things.

Designing a level
-----------------

1. Create the branch `game/xxxxxxx/master` off the initial commit, where 
   `xxxxxxx` is the new level code. The initial commit is tagged with 
   `init`, so the easiest way to create this branch is
   `git checkout -b game/xxxxxxx/master init`.
2. Add a `README.md` file with the level number and your clue. Follow 
   the format of previous levels.
3. If it is a bit of a stretch to get from the clue to the next step 
   (this is subjective), add a small hint in a `HINT` file.
4. If your level requires use of anything other than file contents 
   (e.g. commits, logs, etc.), create level branches. The log and
   commits of the level master must not be significant.
   - The branch name should be `game/xxxxxxx/yyyyyyy`, where `xxxxxxx` is 
     the level code and `yyyyyyy` is the name of the branch, which can
     be anything.
   - Create the branch off the initial commit, just like the level 
     master.
   - If the branch has a README, you do not have to add the level 
     number to it.

Tips:
- The focus of the level should be about using Git features to solve a 
  puzzle, not simply solving a riddle.
- If your level has multiple possible answers, consider adding false
  levels. The `README.md` for a false level should not have a level
  number and should clearly indicate that this is not the right way to
  go. Don't add too many, though, as this restricts the selection for
  later levels.
- Avoid repeating the exact same techniques as previous levels (i.e. if
  a previous level requires you to check out a branch then look at a
  file to get the next code, don't make a level that only requires you
  to check out a branch and look at a file). Combining techniques is
  fine, but be creative.
- Wrap text files (including the README and hints file) to 72 columns on
  spaces; doing this makes it easier to read the file in a terminal.

### Level codes

Level codes are ideally 12 characters or less and are composed only of
lowercase alphanumeric characters. This is not a hard rule, and indeed
there are some codes that break this rule, but there is usually little
reason to break it.

Previous level codes cannot be reused, including codes for false levels.
This command prints all the level codes on an up-to-date copy:

    $ git branch -r --list 'origin/game/*' | cut -f 3 -d / | sort -u

This command fetches the list from the remote repository:

    $ git ls-remote origin | grep 'refs/heads/game/' | cut -f 4 -d / | sort -u

Consider using a random word from the dictionary or a randomly generated
password for your code.

The following will list ten random 7-letter words from the Unix system
dictionary:

    $ grep '^[a-z]\{7\}$' /usr/share/dict/words | shuf | head -10

The following will generate ten random 7-character phonetic passwords
(pwgen must be installed):

    $ pwgen -A0 7 10

Branch prefixes
---------------

This project uses a number of branch prefixes to organize this repo's 
numerous branches.

Prefix  | Purpose
------- | -------
cthulhu | (Reserved)
game    | Levels
meta    | Project administration
scratch | Player-created branches
tmp     | Temporary branches created by scripts
