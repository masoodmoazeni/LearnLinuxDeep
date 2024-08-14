fir youm can create directory for ssl keys

```
mkdir /etc/nginx/ssl
```

and then create ssl file public and private with this command
```
openssl req -x509 -nodes -days 365 \
-newkey rsa:2048 \
-keyout /etc/nginx/ssl/private.key \
-out /etc/nginx/ssl/public.pem
```

and toy can edit config file
```
server {
    listen 80;
    listen 443 ssl;
    server_name malaketabaran.ir;
#    return 301 https://$host$request_uri;

    ssl_certificate     /etc/nginx/ssl/public.pem;
    ssl_certificate_key /etc/nginx/ssl/private.key;
    location /admin2.html {
        auth_basic      "Login Required";
        auth_basic_user_file /etc/nginx/site-available/config/.htpasswd;
    }
    root /var/www/malaketabaran;
    error_page 404 /404.html;
}
```
