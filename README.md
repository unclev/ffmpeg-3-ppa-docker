# ffmpeg docker image with ffmpeg-3 PPA version
====
__Disclaimer__: This is 5 minute quick solition. You may consider using for eg. [FFMPEG for Docker](https://github.com/jrottenberg/ffmpeg) instead.

## Building
```bash
docker build -t unclev/ffmpeg3 .
```
or with custom user:group IDs (1001:1001 for eg.)
```bash
docker build --build-arg PUID=1001 --build-arg PGID=1001 -t unclev/ffmpeg3 .
```

## *producer* user
ffmpeg within the container is run in the name of a *producer* user with uid:gid as specified with the build args (1000:1000) by default.

## Bash alias
```bash
alias ffmpeg3='docker run --rm -v "$(pwd):/home/producer" unclev/ffmpeg3 ffmpeg'
```
