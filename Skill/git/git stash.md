git-stash - Stash the changes in a dirty working directory away

Syntax:
```
$ git stash
```

Remove a single stashed state from the stash list and apply it on top of the current working tree state, i.e., do the inverse operation of `git stash push`. The working directory must match the index.

Applying the state can fail with conflicts; in this case, it is not removed from the stash list. You need to resolve the conflicts by hand and call `git stash drop` manually afterwards.
```
$ git stash pop
```