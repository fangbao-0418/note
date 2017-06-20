# 一、配置防火墙，开启FTP服务器需要的端口
```
CentOS 7.0默认使用的是firewall作为防火墙，这里改为iptables防火墙。

1、关闭firewall：

systemctl stop firewalld.service #停止firewall

systemctl disable firewalld.service #禁止firewall开机启动

2、安装iptables防火墙

yum install iptables-services #安装

vi /etc/sysconfig/iptables #编辑防火墙配置文件

...
...
...
```

# 备注
* CentOS 7.0安装配置vsftp服务器参考地址[http://www.linuxidc.com/Linux/2016-09/135636.htm](http://www.linuxidc.com/Linux/2016-09/135636.htm)
