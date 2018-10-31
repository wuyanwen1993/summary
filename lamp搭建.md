## 安装方式

都采用源码编译安装的方式,之所以采用源码编译安装的方式,主要是为了自定义安装路径



## apahce2 源码编译安装

要编译编译安装apache,必须安装ARP,ARP-Util,PCER,gcc-c++等包

- 首先安装 gcc 或者 gcc-c++

- 

- 设置开机启动

  - 

- 设置守护进程的方式启动




参考:  

[官方安装文档](http://httpd.apache.org/docs/2.4/install.html)

[linux下apache2安装流程](https://www.cnblogs.com/wcwnina/p/8029156.html)



## php源码编译安装

ubantu 源码编译安装

- 安装依赖包

  `sudo apt-get install autoconf build-essential curl libtool \
    libssl-dev libcurl4-openssl-dev libxml2-dev libreadline7 \
    libreadline-dev libzip-dev libzip4 nginx openssl \
    pkg-config zlib1g-dev ibapache2-mod-php`

- 建立安装目录

  `mkdir /usr/local/php`

- 下载php源码文件

- 解压源码文件,并 cd入源码文件夹

- 进行安装设定

  `./configure --prefix=/usr/local/php \
  ​    --enable-mysqlnd \
  ​    --with-pdo-mysql \
  ​    --with-pdo-mysql=mysqlnd \
  ​    --enable-bcmath \
  ​    --enable-fpm \
  ​    --with-fpm-user=www-data \
  ​    --with-fpm-group=www-data \
  ​    --enable-mbstring \
  ​    --enable-phpdbg \
  ​    --enable-shmop \
  ​    --enable-sockets \
  ​    --enable-sysvmsg \
  ​    --enable-sysvsem \
  ​    --enable-sysvshm \
  ​    --enable-zip \
  ​    --with-libzip=/usr/lib/x86_64-linux-gnu \
  ​    --with-zlib \
  ​    --with-curl \
  ​    --with-pear \
  ​    --with-openssl \
  ​    --enable-pcntl \
  ​    --with-readline`

- 