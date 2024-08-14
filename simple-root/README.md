run this command for create directory
```
mkdir -p /var/www/test
```

run this command for create file html
```
echo "<h1> hello masood </h1>" > /var/www/test/index.html
```

and you can write in config
```
server {
    listen 80;
    server_name malaketabaran.ir;
#    return 301 https://$host$request_uri;

    root /var/www/malaketabaran;

}
```
