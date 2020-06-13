## setup
```
$ sudo yum install epel-release
# sudo amazon-linux-extras install epel

$ sudo yum install nginx
$ sudo nginx -v
nginx version: nginx/1.16.1

$ sudo systemctl start nginx
$ sudo systemctl stop nginx
$ sudo systemctl restart nginx
```

## nginx.conf
```
server {
    listen 80;
    server_name example.com;
    return 301 https://$host$request_uri;
}

server {
  server_name example.com, www.example.com;

  location /hooks/ {
      proxy_set_header Host $host;
      proxy_pass http://127.0.0.1:<port>/hooks/;
  }

  location /location_2/ {
      proxy_pass http://127.0.0.1:<port>/;
      proxy_read_timeout 1000s;
      proxy_set_header Connection "";
      proxy_set_header X-Forwarded-Proto $scheme;
      proxy_set_header Host <example.com>/<location_2>;
  }
}
```

## reload / verify
```
$ cd /etc/nginx/conf.d
$ sudo /etc/init.d/nginx reload

$ sudo systemctl start nginx
$ sudo systemctl sstop nginx
$ pgrep nginx
$ ss -tlpn | grep :80
```

## logs
```
$ cd /var/log/nginx/
$ tail -f access.log
$ tail -f error.log
```
