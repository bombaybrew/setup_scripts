## Setup
```
$ docker volume create --opt type=none --opt device=/srv/volume/ghost ghost_volume

$ docker run -d --name brew_ghost -p <port>:2368 -v /srv/volume/ghost:/var/lib/ghost/content ghost:alpine

$ docker exec -it brew_ghost sh

# Inside Ghost docker
$$ ghost config url https://<yourDomain>.com
$$ ghost restart
```

## Issues
### Too many redirects - updating ghost config url causes this error. Update nginx config to fix this
- https://github.com/TryGhost/Ghost/issues/2796
- https://github.com/TryGhost/Ghost/issues/4370
```
server {
        listen                          443 ssl spdy;

        location / {
            proxy_pass              http://localhost:8080;
            proxy_set_header        X-Real-IP $remote_addr;
            proxy_set_header        X-Forwarded-For $proxy_add_x_forwarded_for;
            proxy_set_header        X-Forwarded-Proto https;
            proxy_set_header        Host $http_host;
            proxy_intercept_errors  on;
        }
}
```

