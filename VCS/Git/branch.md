# Git Branch

## Check branches

```sh
# show all branches (local & remote)
git branch -a

# show local branches
git branch -l

# show remote branches
git branch -rf
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
