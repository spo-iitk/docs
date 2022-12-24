---
title : nginx.conf
layout : default
nav_order: 8
---

# nginx.conf

- we use nginx web server to serve our application
- it listens on the `port 80` and then uses reverse proxy to redirect various page routes to different servers hosting different microservices.

```nginx
server{
    listen 80 default_server;
    server_name _;

    proxy_set_header Host $host;
    proxy_set_header X-Forwarded-For $remote_addr;

    location / {
        proxy_pass http://localhost:3470;
    }
    location /api/ras {
        proxy_pass http://localhost:3470;
    }
    location /api/auth {
        proxy_pass http://localhost:3475;
    }
    location /api/student {
        proxy_pass http://localhost:3480;
    }
    location /api/company {
        proxy_pass http://localhost:3485;
    }
    location /api/admin/rc {
        proxy_pass http://localhost:3490;
    }
    location /api/admin/application/rc {
        proxy_pass http://localhost:3492;
    }
    location /api/admin/company {
        proxy_pass http://localhost:3495;
    }
    location /api/admin/student {
        proxy_pass http://localhost:3500;
    }
}
```
the commands like :
```nginx
location / {
        proxy_pass http://localhost:3470;
    }
```
- see when route is `location /` and then redirect them to a given port by `proxy_pass <url>`