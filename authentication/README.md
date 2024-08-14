add this config on nginx 
```
server {
    listen 80;
    server_name malaketabaran.ir;

    location /admin.html {
        auth_basic      "Login Required";
        auth_basic_user_file /etc/nginx/sites-available/config/.htpasswd;
    }
    root /var/www/malaketabaran;
    error_page 404 /404.html;
}
```

and you can set config password on this way
```
htpasswd -c /etc/nginx/sites-available/config/.htpasswd admin
```

after that you can curl or on browser send request
```
curl -u user:password localhost/admin.html

```
