# Locale - Vagrant trouble shooting

## dpkg-reconfigure

<hr>
Problem:

`dpkg-reconfigure: unable to re-open stdin: No file or directory`

Solution:

_Add these definition before provision code_

```sh
export LANGUAGE=en_US.UTF-8
export LANG=en_US.UTF-8
export LC_ALL=en_US.UTF-8
locale-gen en_US.UTF-8
dpkg-reconfigure locales
```
<hr>
