you can see list module in nginx 

```
nginx -V 2>&1 | tr -- - '\n' | grep _module
```
