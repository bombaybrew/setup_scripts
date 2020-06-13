## Setup
```
$ docker volume create --opt type=none --opt device=/srv/volume/ghost ghost_volume

$ docker run -d --name brew_ghost -p <port>:2368 -v /srv/volume/ghost:/var/lib/ghost/content ghost:alpine
```
