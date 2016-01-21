# Mac OS Screenshot

## Build-in screenshot
In Mac OS, we have two build-in screenshot shortcuts:
- `<Cmd>` + `<Shift>` + `3`    // capture full screen
- `<Cmd>` + `<Shift>` + `4`    // capture user defined area

### Defined a different place to save screenshots

By default, screenshots will be saved into `~/Desktop/`

#### You can change to a new place:
```sh
defaults write com.apple.screencapture location <new_path>
killall SystemUIServer
```

#### Check this config by:
```sh
defaults read com.apple.screencapture location
```
_No output means it's default value `~/Desktop/`_
