---
title: Getting yourself tangled in `git` branches
publish_date: Dec 19th, 2017
tags:
  - git
  - linux
  - shell
---

# Deleting a `git` branch ... What could really go wrong :)

Have you ever deleted the `remote` of the branch you've got checked out? And then deleted the corresponding
local branch (that you've still got checked out)?

If you've answered with Yes to at least one of the one question above, then I encourage you to read further. Alternatively, you may still proceed at your own caution - might save you some troubles down the line :)

Now `git` believes that `HEAD` doesn't exist and your current branch has no commits, but stages all files that were associated with the branch as new files. Wunderbah[^wunderbah]! Just wunderbah! How do you get out of that Houdini?!? Can you reset to `HEAD` or `HEAD^`. Nein! Further - as if it's not a big enough fun already - depending on how different your branch was to any other, it may not let you checkout anything else.

Okay, time for solutions! You could opt for performing `git rm -f` on everything that had been staged. At that point, an actual branch can be checked out again. Alternatively, invoking `git reflog` followed by `git checkout` of the commit hash of the head of the old branch should do the job.
If you want to play fancy, you can re-create the branch, make a commit, checkout another branch, and delete the originally intended branch.

That's about it! Have lots of fun in `git`land and see you soon!

[^wunderbah]: For the non-German speaking among you, _wunderbah_ means _wonderful_.