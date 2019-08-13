# nginx.conf
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

# setup
```
cd /etc/nginx/conf.d
sudo /etc/init.d/nginx reload
```
