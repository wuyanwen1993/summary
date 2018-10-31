## ubuntu  系统 lamp搭建

### 安装apache 

```
sudo apt-get install apache2
apache2 -v
## 查看是否加载了libphp7.so,如果没有 要注意后续安装 libapache2-mod-php7.0
cat /etc/apache2/mods-enabled/php7.load 
```

### 安装mysql

```
sudo apt-get install mysql-server mysql-client
## 确认是否安装成功
service mysql status
```

## 安装PHP

```
sudo apt-get install php
## 确认php版本
php -v
## 安装拓展模块
# apache 加载 libapache2-mod-php 来加载php模块
sudo apt-get install libapache2-mode-php
# php 记载 php-mysql 来链接mysql
sudo apt-get install php-mysql

```



