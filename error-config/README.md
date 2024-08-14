at first you must create file 404.html on this root /var/www/malaketabaran

```
server {
    listen 80;
    server_name malaketabaran.ir;
#    return 301 https://$host$request_uri;

    root /var/www/malaketabaran;
    error_page 404 /404.html;
    error_page 500 501 502 503 504 /50x.html
}
```
