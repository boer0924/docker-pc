## 1、下载安装DockerToolbox
https://www.docker.com/products/docker-toolbox

> **What’s in the Toolbox**
>
> - DOCKER ENGINE
> - COMPOSE
> - MACHINE
> - KITEMATIC

https://download.docker.com/win/stable/DockerToolbox.exe

## 2、配置国内Docker加速器
1. DaoCloud加速器
https://www.daocloud.io/mirror#accelerator-doc
2. 阿里云加速器
https://cr.console.aliyun.com/#/accelerator

## 3、Deploy a Docker Registry
https://docs.docker.com/registry/insecure/#deploying-a-plain-http-registry

https://docs.docker.com/registry/recipes/nginx/

```
mkdir -p certs && openssl req \
    -newkey rsa:4096 -nodes -sha256 -keyout certs/domain.key \
    -x509 -days 365 -out certs/domain.crt

openssl genrsa -out client.key 4096
openssl req -new -x509 -text -key client.key -out client.cert
```
>
> Instruct every docker daemon to trust that certificate.
> This is done by copying the domain.crt file to /etc/docker/certs.d/myregistrydomain.com:5000/ca.crt.
>

## 4、Deploy Service

### MySQL
https://hub.docker.com/_/mysql/
```
docker logs some-mysql 查看日志
docker exec some-mysql sh -c 'exec mysqldump --all-databases -uroot -p"$MYSQL_ROOT_PASSWORD"' > /some/path/on/your/host/all-databases.sql 备份数据
```

### Memcached
https://hub.docker.com/_/memcached/

### Redis
https://hub.docker.com/_/redis/

### PHP
https://hub.docker.com/_/php/

Imagick GD区别
https://www.sitepoint.com/imagick-vs-gd/

### Nginx
https://hub.docker.com/_/nginx/

