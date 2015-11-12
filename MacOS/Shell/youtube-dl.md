# YouTube-dl



## Install

### Mac

```sh
brew install youtube-dl
```

### Apt-get

```sh
sudo apt-get install -y youtube-dl
```



## How to use

### Basic

```sh
youtube-dl <VIDEO_URL>
```

### List all available formats & resolutions

```sh
youtube-dl -F <VIDEO_URL>
```

### Choose one format to download

```sh
youtube-dl -f <format_id> <VIDEO_URL>
```

### List subtitles

```sh
youtube-dl --list-subs <VIDEO_URL>
```

### Download all subtitles only

```sh
youtube-dl --all-subs --skip-download <VIDEO_URL>
```

### Download list

```sh
youtube-dl -cit <LIST_URL>
```
