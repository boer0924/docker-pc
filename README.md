# Windows环境下运行Docker

### 再也不用Wnmp/Xammp/Wamp Server了...

## 1、下载安装Docker CE for Windows 或者 DockerToolbox
https://www.docker.com/docker-windows
https://www.docker.com/products/docker-toolbox

> **What’s in the Toolbox**
>
> - DOCKER ENGINE
> - COMPOSE
> - MACHINE
> - KITEMATIC

https://download.docker.com/win/stable/DockerToolbox.exe

https://download.docker.com/win/stable/InstallDocker.msi

## 2、配置国内Docker加速器

**右键->Settings->Daemon->Registry mirrors->Apply**

1. DaoCloud加速器
https://www.daocloud.io/mirror#accelerator-doc
2. 阿里云加速器
https://cr.console.aliyun.com/#/accelerator

## 3、配置本地磁盘映射

右键->Settings->Shared Drives->选择磁盘(打勾)->Apply

## 4、运行

```
git clone https://github.com/boer0924/docker-pc.git
cd docker-pc
docker-compose up -d
```

## 附录

```
# 一些常用命令
docker ps -a
docker images -a
docker rm <container_id>
docker rmi <image_id>
docker logs -f <container_id>
docker inspect <container_id>
docker exec -it <container_id> bash
docker-compose restart <services_tag>

......

```
