# 创建软件包存放地址（个人习惯）
```
sudo mkdir /usr/local/software
```

# nginx 安装
## 安装依赖
```
apt-get install gcc automake autoconf make
```
### 安装 gcc g++ 的依赖库
```
sudo apt-get install build-essential
sudo apt-get install libtool
```
### 安装 pcre 依赖库 （http://www.pcre.org）
```
sudo apt-get update
sudo apt-get install libpcre3 libpcre3-dev
```
### 安装 zlib 依赖库 （http://www.zlib.net）
```
sudo apt-get install zlib1g-dev
```
### 安装 SSL 依赖库
```
sudo apt-get install openssl
```
## 正式安装 nginx
```
cd /usr/local/software
# 下载稳定版本
sudo wget http://nginx.org/download/nginx-1.14.2.tar.gz
# 解压
sudo tar -zxvf nginx-1.14.2.tar.gz
# 切入 解压目录
cd /usr/local/software/nginx-1.14.2
# 注意： 要切换到root用户来执行配置命令
# 配置，这样最后nginx的全部安装文件，包括配置文件，会安装到/usr/local/nginx目录中
./configure --prefix=/usr/local/nginx
make && make install
```

## 启动 nginx 并查看进程 
```
sudo /usr/local/nginx/sbin/nginx -c /usr/local/nginx/conf/nginx.conf
# 注意：-c 指定配置文件的路径，不加的话，nginx会自动加载默认路径的配置文件，可以通过-h查看帮助命令。
# 查看进程：
ps -ef | grep nginx
```

## 查看端口
```
su root
netstat -lntp
```
## 配置开机启动
```
sudo vim /etc/rc.local 
# 加入以下代码
/usr/local/nginx/sbin/nginx -c /usr/local/nginx/conf/nginx.conf &
```

## 加入环境变量
```
sudo vim /etc/profile
# 加入nginx 路径
/usr/local/nginx/sbin
```


# 安装mysql (为省时间，mysql采用 apt安装)
```
sudo apt install mysql-server
```

# 安装 php
## 安装依赖
apt-get install libxml2-dev gcc autoconf

## 获取源码并进行编译安装
直接从本地上传php源码，或者 wget 获取线上资源

```
sudo mkdir /usr/local/php
cd /usr/local/software
# 切换到 root 用户 执行以下操纵
wget https://www.php.net/distributions/php-7.2.16.tar.gz
tar -zxvf php-7.2.16.tar.gz
cd php-7.2.16
./configure --prefix=/usr/local/php --enable-fpm
注意： 要加上 --enable-fpm 静态安装上fpm
fpm为 fastCGI的进程管理器
make && make install
```

## 设置 php.ini
将源码的php.ini.development 文件复制到 /usr/local/php/lib 下面 并命名为php.ini 文件

修改 php.ini 的时区为国内时区（PRC）

## 加入环境变量
```
sudo vim /etc/profile
# 加入以下代码
/usr/local/php/bin
# 环境变量生效
source /etc/profile
```

## php-fpm (fastcgi 的进程管理器)
php-fpm 为独立运行 要对其进行配置

### php-fpm 配置
准备工作
```
cd /usr/local/php/etc
#将 php-fpm.conf.default 文件复制 为 php-fpm.conf
cp /usr/local/php/etc/php-fpm.conf.default /usr/local/php/etc/php-fpm.conf
# 切入 php-fpm.d文件夹
cd /usr/local/php/etc/php-fpm.d
# 将 www.conf.default 文件复制为 www.conf
sudo cp www.conf.default www.conf
```
正式配置
```
sudo vim /usr/local/php/etc/php-fpm.conf
# 去掉 pid (存储fpm进程id的文件) 的注释
sudo vim /usr/local/php/etc/php-fpm.d/www.conf
# 修改 user 和 group 组的用户为 nginx 的用户

```

## 启动 php-fpm
```
sudo /usr/local/php/sbin/php-fpm
```
## 查看端口号 确认php-fpm 已经启动
```
# 切换到 root 用户， 执行查看端口命令
netstat -lntp
```

## 通常重启方法
```
kill -USR2 `cat /usr/local/php/var/run/php-fpm.pid` 
```

## 配置开机启动
```
sudo vim /etc/rc.local
# 加入代码
/usr/local/php/sbin/php-fpm &
```

# nginx 的虚拟主机配置
在 nginx 配置中做详细讲解，这里不过多阐述

```
server {
         root /usr/local/nginx/html/shop;
         server_name shop.nginx.com;
 
         # pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000
         #
         location ~ \.php$ {
              fastcgi_pass   127.0.0.1:9000;
              fastcgi_index  index.php;
              fastcgi_param  SCRIPT_FILENAME  $document_root$fastcgi_script_name;
              include        fastcgi_params;
        }
         
         location / {
             index  index.html index.htm index.php;
         }   
         
    }
```