# Git Global Config

## Personal info

```sh
git config --global user.name [your_name]
git config --global user.email [your_email]
```

## Git Push

```sh
# Old style
git config --global push.default matching

# New style
git config --global push.default simple
```

## Global ignore

1. Create global ignore file

  `~/.gitignore_global`

2. Add this file to git global config
```sh
git config --global core.excludesfile ~/.gitignore_global
```
