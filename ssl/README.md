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
