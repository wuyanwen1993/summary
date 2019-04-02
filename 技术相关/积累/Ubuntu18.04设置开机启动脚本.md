ubuntu-18.04不能像ubuntu14一样通过编辑rc.local来设置开机启动脚本，通过下列简单设置后，可以使rc.local重新发挥作用。
1. 建立 rc.local.service 文件
```
sudo vim /etc/systemd/system/rc-local.service
```

2. 将下面内容复制到 rc.local.service 文件
```
[Unit]
Description=/etc/rc.local Compatibility
ConditionPathExists=/etc/rc.local
 
[Service]
Type=forking
ExecStart=/etc/rc.local start
TimeoutSec=0
StandardOutput=tty
RemainAfterExit=yes
SysVStartPriority=99
 
[Install]
WantedBy=multi-user.target
```
3. 创建文件 rc.local
```
sudo vim /etc/rc.local
```
4.将下列内容复制进rc.local文件
```
#!/bin/sh -e
#
# rc.local
#
# This script is executed at the end of each multiuser runlevel.
# Make sure that the script will "exit 0" on success or any other
# value on error.
#
# In order to enable or disable this script just change the execution
# bits.
#
# By default this script does nothing.
echo "看到这行字，说明添加自启动脚本成功。" > /usr/local/test.log
exit 0
```
5.给rc.local加上权限
```
sudo chmod +x /etc/rc.local
```
6.将下列内容复制进rc.local文件
```
sudo systemctl enable rc-local
```
7.启动服务并检查状态
```
sudo systemctl start rc-local.service
sudo systemctl status rc-local.service
```
8.重启并检查test.log 文件是否存在，如果存在说明开机脚本设定成功
```
cat /usr/local/test.log　
```

# 参考资料
[ubuntu18.04 设置开机启动脚本](http://www.cnblogs.com/airdot/p/9688530.html)