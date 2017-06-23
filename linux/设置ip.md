# 设置ip

### 配置文件

```bash
vi /etc/sysconfig/network-scripts/ifcfg-eth0
DEVICE=etho // 设备名称
TYPE-Ethernet // 网络类型
ONBOOT=yes // 开机自动启动
BOOTPROTO=static // 静态ip(static) 动态ip(dhcp)
DNS1=192.168.1.1 // DNS
IPADDR=192.168.1.133 // ip
METMASK=255.255.255.0 // 子网掩码
GETEWAY=192.168.1.1 // 网关
```

### 重启网络服务

``
service network restart或/etc/init.d/network restart
``

### 其他
```
---修改ip地址---
即时生效:
# ifconfig eth0 192.168.1.155 netmask 255.255.255.0
重启生效:
修改/etc/sysconfig/network-scripts/ifcfg-eth0

---修改default gateway---
即时生效:
# route add default gw 192.168.1.1
重启生效:
修改/etc/sysconfig/network-scripts/ifcfg-eth0

---修改dns---
修改/etc/resolv.conf
修改后即时生效，重启同样有效

---修改host name---
即时生效:
# hostname test1
重启生效:
修改/etc/sysconfig/network

```
