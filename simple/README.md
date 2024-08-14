```
server {
    listen 80;
    server_name malaketabaran.ir;

    location / {
        add_header Content-Type text/plain;
        return 200 "this is simple page";
    }
}
```
