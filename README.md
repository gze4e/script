# 懒人专用一键脚本

Filebrowser.sh
======

- 脚本说明: Filebrowser 一键安装脚本
- 系统支持: CentOS6+ / Debian7+ / Ubuntu14+
- 使用方法: https://github.com/filebrowser/filebrowser

### 下载安装:
``` bash
bash <(curl -L -s https://raw.githubusercontent.com/gze4e/script/master/Filebrowser.sh)
```



修改配置
配置文件在：/etc/filebrowser/filebrowser.json



Nginx 代理设置
https://blog.csdn.net/yimagudao/article/details/89461523


服务管理命令
状态：systemctl status filebrowser
启动：systemctl start filebrowser
停止：systemctl stop filebrowser
重启：systemctl restart filebrowser
开机启动：systemctl enable filebrowser

重置密码
忘记密码后直接删除Filebrowser 的数据库，然后重启 Filebrowser 即可,然后用户名跟密码又是 admin。



gocc.sh
======

- 脚本说明: GoCC 一键安装脚本
- 系统支持: Linux/Unix
- 使用方法: https://github.com/liuzl/gocc

### 下载安装:
``` bash
wget --no-check-certificate --no-cache https://raw.githubusercontent.com/gze4e/script/master/gocc.sh
chmod +x gocc.sh
sudo ./gocc.sh
```
