# Submodule - Git

## How to remove a Submodule

```sh
# assume we have submodule: app
mv app app-bak
git submodule deinit app
git rm app
git rm --cached app
mv app-bak app
```
