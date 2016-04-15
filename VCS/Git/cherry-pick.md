# Git - Cherry-Pick


## Issue solution

### `CHERRY_PICK_HEAD` error

```
fatal: You have not concluded your cherry-pick (CHERRY_PICK_HEAD exists).
Please, commit your changes before you merge.
```

It will be resolved by:

```sh
git cherry-pick --abort
```
