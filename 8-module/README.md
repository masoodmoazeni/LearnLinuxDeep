you can see list module in nginx 

```
nginx -V 2>&1 | tr -- - '\n' | grep _module
```

install modsecurity nginx
1-
```
sudo apt-get install bison build-essential ca-certificates curl dh-autoreconf doxygen flex gawk git iputils-ping libcurl4-gnutls-dev libexpat1-dev libgeoip-dev liblmdb-dev libpcre3-dev libpcre++-dev libssl-dev libtool libxml2 libxml2-dev libyajl-dev locales liblua5.3-dev pkg-config wget zlib1g-dev libxslt1-dev libgd-dev
```
2-
```
cd /opt && sudo git clone https://github.com/SpiderLabs/ModSecurity
```
3-
```
sudo git submodule init
sudo git submodule update
```
4-
```
sudo ./build.sh
sudo ./configure
sudo make
make install
```
5- you can see article on this page
```
https://medium.com/codelogicx/securing-nginx-server-using-modsecurity-oswaf-7ba79906d84c
```
