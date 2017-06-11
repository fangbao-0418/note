# <center>Centos7-minimal安装完成后需要完成的几件事情</center>
## 一：调通网络
### 1.修改网卡名称

```
#cd /etc/sysconfig/network-scripts/
#mv ifcfg-eno16777736 ifcfg-eth0
#vi ifcfg-eth0
```

<pre>
将NAME/DEVICE修改为eth0
#vi /etc/default/grub
在变量GRUBCMDLINELINUX中加入net.ifnames=0 biosdevname=0
#grub2-mkconfig -o /boot/grub2/grub.cfg
#vi /etc/udev/rules.d/70-persistent-net.rules
SUBSYSTEM==”net”,ACTION==”add”,DRIVERS==”?“,ATTR{address}==”您的网卡MAC地址”,ATTR｛type｝==”1” ,KERNEL==”eth“,NAME=”eth0”
#reboot
</pre>

## 二：安装必要工具
```
#yum install epel-release
#yum install yum-axelget
#yum update
#reboot
#yum install gcc
#yum install gcc-c++
#yum install make
#yum install gdb
#yum install cmake
#yum install git
#yum install vim
#yum install clang
#yum install clang-analyzer
#yum install ntpdate -y
#ntpdate time.windows.com && hwclock -w
```
