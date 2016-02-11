# Stop Windows 10 Upgrade Notification

## 1. Open `regedit`

- Press `<Win>+ <r>` to open run command
- Input `regedit` and press `<Enter>`

## 2. Go to the path which contains the key

- Path: `HKLM\SOFTWARE\Policies\Microsoft\Windows\WindowsUpdate`
- Key: `DisableOSUpgrade`
- Set `Dword` to `1`. Create if it is not exist.
