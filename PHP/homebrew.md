# Homebrew PHP

## Install

```sh
brew install php56
brew link php56
```

## Install with `pear` and `phpcs`

```sh
# Install php56 with parameter '--with-pear'
brew install php56 --with-pear
brew link php56
pear install PHP_CodeSniffer
brew unlink php56 && brew link php56
```
