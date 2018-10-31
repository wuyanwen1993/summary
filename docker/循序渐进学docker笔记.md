# 循序渐进学docker
## docker究竟是什么?
Docker 是一个开源的应用容器引擎 , 它 的应用以镜像(image)的形式发布,可以运行在任何装有Docker引擎的操作系统上面

## dokcer用来干什么?
- 如何快速的将一台机器的应用环境分享给其他机器使用,用于扩容和故障时服务转移-



## 基本命令

- 查询镜像
  - docker search <strig>
- 下载(拉取)镜像
  - docker pull  镜像全名(username/repositroy)	
- 创建并启动容器
  - docker run 命令用来创建和运行Docker容器
- 查看本地所有容器
  - docker ps -l
- 查看容器信息
  - docker ps  查看正在运行的容器
  - docker inspect  容器ID(前3-4个字符)  查看具体的容器

后台 挂起  docker run -d  通过 -d 参数设置进程后台挂起

docker exec  查看容器内部信息

docker stop 停止docker容器进程





##  制作docker镜像







