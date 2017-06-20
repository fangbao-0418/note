# Linux开启mysql远程连接的设置步骤

## GRANT命令创建远程连接mysql授权用户itlogger
```html
mysql -u root -p
mysql>GRANT ALL PRIVILEGES ON *.* TO itlogger@localhost IDENTIFIED BY ‘www.itlogger.com’ WITH GRANT OPTION;
mysql>GRANT ALL PRIVILEGES ON *.* TO itlogger@”%” IDENTIFIED BY ‘www.itlogger.com’ WITH GRANT OPTION;
第一句增加itlogger用户授权通过本地机（localhost)访问，密码“www.itlogger.com”。第二句则是授与itlogger用户从任何其它主机发起的访问（通配符％）。

```
## mysql数据库远程访问设置方法

```html
修改localhost
更改 "mysql" 数据库里的 "user" 表里的 "host" 项，从"localhost"改成"%"
mysql>use mysql;
mysql>update user set host = '%' where user = 'root';
mysql>select host, user from user;
mysql>FLUSH PRIVILEGES;
```

# 备注
* 参考地址[http://blog.csdn.net/sctq8888/article/details/7446906](http://blog.csdn.net/sctq8888/article/details/7446906)
