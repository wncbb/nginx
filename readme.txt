1. install nginx
./configure --with-pcre=<the dir of pcre-8.37> --with-openssl=<the dir of openssl-1.0.2g> --with-zlib=<the dir of zlib-1.2.8>
make
sudo make install

2. edit hosts, so we can use domain name
change: /etc/hosts
add 127.0.0.1 node.todd.com

3. edit nginx conf
change: /usr/local/nginx/conf/nginx.conf
add below in http:
server{
  listen 80;
  server_name node.todd.com;
  location / {
    proxy_pass http://127.0.0.1:3000;
  }
}





