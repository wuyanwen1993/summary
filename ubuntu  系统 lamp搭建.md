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
sudo apt-get install libapache2-mod-php
# php 记载 php-mysql 来链接mysql
sudo apt-get install php-mysql

```

## 主要文件位置（默认安装）

1. ubuntu 系统配置文件目录 /etc
2.  各组件配置文件位置
   - apache2  /etc/apache2
   - Mysql /etc/mysql
   - php /etc/php/7.2



## 虚拟主机配置

修改hosts文件 /etc/hosts 模拟DNS，设置域名指向主机

127.0.0.1 ceshi.com

虚拟主机配置文件位置 ： /etc/apache2/sites-available  在该文件夹下 增加 ceshi.com.cnf

打开cehsi.com.conf 文件， 增加 ServerName， 修改访问文档路径 ，具体设置如下：

![1542368138355](/home/mark/.config/Typora/typora-user-images/1542368138355.png)

切入到 sites-enabled 文件夹 建立软链接

![1542368005954](/home/mark/.config/Typora/typora-user-images/1542368005954.png)

重启apache2 service apache2 restart



## 安装phpmyadmin

sudo apt-get install phpmyadmin 

sudo ln -s /usr/share/phpmyadmin/  /var/www/pma





## 常见文件

Q： 怎么修改Apache/2.4.29 (Ubuntu) 的默认根目录？

Apache/2.4.29 (Ubuntu)  默认根目录在  /var/www/html



## 参考资料

https://www.jianshu.com/p/984f2ac52e29

