# Reboot-able USB

## Use command line to make

_Normally, Mac OS X install application will download to /Applications path directly._

```sh
sudo  \
  '/Applications/Install OS X El Capitan.app/Contents/Resources/createinstallmedia'  \
  --volume '/Volumes/<your_usb_drive>'  \
  --applicationpath '/Applications/Install OS X El Capitan.app'  \
  --nointeraction
```
