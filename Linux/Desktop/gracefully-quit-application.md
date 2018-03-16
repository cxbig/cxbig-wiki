# Gracefully quit application

## To-Do

- Install `wmctrl`
- Setup custom shortcut

## Install

```sh
sudo apt install -y wmctrl
```

## Setup custom shortcut

1. Open `Settings` -> `Devices` -> `Keyboard`
2. Add new shortcut with command

	```
	wmctrl -c :ACTIVE:
	```