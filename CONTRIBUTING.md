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
4. Add a non-spoiler hint to the `meta/hints` branch. This hint should
   be aimed at players who are stuck and need a little bit of an extra
   push. Use the existing hint files as examples.
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

1. Create the branch `xxxxxxx/master` off the initial commit, where 
   `xxxxxxx` is the new level code. The initial commit is tagged with 
   `init`, so the easiest way to create this branch is
   `git checkout -b xxxxxxx/master init`.
2. Add a `README.md` file with the level number and your clue. Follow 
   the format of previous levels.
3. If it is a bit of a stretch to get from the clue to the next step 
   (this is subjective), add a small hint in a `HINT` file.
4. If your level requires use of anything other than file contents 
   (e.g. commits, logs, etc.), create level branches.
   - The branch name should be `xxxxxxx/yyyyyyy`, where `xxxxxxx` is 
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

### Level codes

Level codes are ideally 12 characters or less and are composed only of
lowercase alphanumeric characters. This is not a hard rule, and indeed
there are some codes that break this rule, but there is usually little
reason to break it.

The codes printed by this command are taken and cannot be reused:

    $ git branch -r | cut -f 2 -d / | sort -u

Additionally, the following codes are reserved and should be used
appropriately:
- cthulhu: name of the game; reserved for future use
- meta: used for project administration branches
- scratch: used for player branches
- tmp: used for temporary branches created by scripts
