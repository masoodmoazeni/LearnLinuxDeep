for rewrite and remove extension file in nginx


```
server {
    listen 80;
    listen 443 ssl;
    server_name malaketabaran.ir;
#    return 301 https://$host$request_uri;

    ssl_certificate     /etc/nginx/ssl/public.pem;
    ssl_certificate_key /etc/nginx/ssl/private.key;

    location / {
         try_files $uri $uri/ @extensionless-html;
         index index.html index.htm index.php;
    }

    location @extensionless-html {
        if (!-e $request_filename.html) {
            rewrite ^(.*)$ $1.html last;
        }
    }

    location /admin2 {
        auth_basic      "Login Required";
        auth_basic_user_file /etc/nginx/site-available/config/.htpasswd;
    }

    root /var/www/malaketabaran;
    error_page 404 /404.html;
}
```
