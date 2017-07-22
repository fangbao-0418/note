
进入 /etc/ssh 目录，编辑 sshd_config，打开以下三个配置的注释：

```
RSAAuthentication yes
PubkeyAuthentication yes
AuthorizedKeysFile .ssh/authorized_keys
```

保存并重启 sshd 服务：
```
systemctl restart sshd
```

生成ssh密钥
```
$ ssh-keygen -t rsa -C “haiyan.xu.vip@gmail.com”
按3个回车，密码为空。
```

将客户端公钥导入服务器端 /home/git/.ssh/authorized_keys 文件
```
ssh git@192.168.56.101 'cat >> .ssh/authorized_keys' < ~/.ssh/id_rsa.pub
```

git push同步部署到服务器
```
vim /home/gitrepo/xxx.git/hooks/post-receive
#!/bin/sh
git --work-tree=/home/www/bbs checkout -f
```
