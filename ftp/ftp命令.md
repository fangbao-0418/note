# 如何在命令行中使用ftp命令上传和下载文件

## 建立 FTP 连接

```
ftp domain.com

ftp 192.168.0.1

ftp user@ftpdomain.com
```

## 使用 FTP 下载文件

```
在下载一个文件之前，我们首先需要使用lcd命令设定本地接受目录位置。
lcd /home/user/yourdirectoryname
如果你不指定下载目录，文件将会下载到你登录 FTP 时候的工作目录。

现在，我们可以使用命令 get 来下载文件，比如：
get file
文件会保存在使用lcd命令设置的目录位置。

下载多个文件可以使用通配符及 mget命令。例如，下面这个例子我打算下载所有以 .xls 结尾的文件。
mget *.xls

```

## 使用 FTP 上传文件

```
使用 put命令上传文件：
put file
当文件不再当前本地目录下的时候，可以使用绝对路径：
put /path/file
同样，可以上传多个文件：
mput *.xls
```

## 关闭 FTP 连接

```
完成FTP工作后，为了安全起见需要关闭连接。有三个命令可以关闭连接：
bye
exit
quit
```

## 备注
更多命令参考：[http://jingyan.baidu.com/article/b2c186c8ee1116c46ef6ffc8.html](http://jingyan.baidu.com/article/b2c186c8ee1116c46ef6ffc8.html)
