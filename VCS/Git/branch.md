# Git Branch

## Parameters

```sh
-a                     # both local and remote
-l                     # local only
-r                     # remote only
--merged [<branch>]    # show branches are merged into <branch>, default is HEAD
--no-merged
```

## Command Samples

```sh
# show all branches (local & remote)
git branch -a

# show local branches
git branch -l

# show remote branches
git branch -r

# list remote branches which merged into master
git branch -r --merged master    

# list remote branches which merged into HEAD
git branch -r --merged

# list remote branches which is not merged
git branch -r --no-merged
```

## Remove branches

```sh
# remove local branch
git branch -D <branch_name>
git branch -D develop

# remove remote branch
git branch -D -r <remote_name>/<branch_name>
git branch -D -r origin/develop
```
