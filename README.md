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
ip http


server {
        listen       80;
        listen       [::]:80;
        server_name  _;  #没有域名
        location / {
                proxy_pass http://localhost:9184;  #File Browser服务部署的地址
                proxy_set_header Host $host;
                proxy_set_header X-Real-IP $remote_addr;
                proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        }
    }


域名 http


server {
        listen       80;
        listen       [::]:80;
        server_name  file.datablog.top;  #填写服务的域名即可
        location / {
                proxy_pass http://localhost:9184;  #File Browser服务部署的地址
                proxy_set_header Host $host;
                proxy_set_header X-Real-IP $remote_addr;
                proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        }
        # 如果需要全局使用https，请启用下面的配置
        #  return 301 https://file.datablog.top$request_uri;
    }


域名 https

server {
        listen       443 ssl http2;
        listen       [::]:443 ssl http2;
        server_name  file.datablog.top; #使用的域名

        ssl_certificate "file.pem"; # ssl的公钥地址 
        ssl_certificate_key "file.key"; # ssl的私钥地址
        ssl_session_cache shared:SSL:1m;
        ssl_session_timeout  10m;
        ssl_ciphers ECDHE-RSA-AES128-GCM-SHA256:ECDHE:ECDH:AES:HIGH:!NULL:!aNULL:!MD5:!ADH:!RC4;
        ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
        ssl_prefer_server_ciphers on;

        location / {
                proxy_pass http://localhost:9184; #代理的服务地址
                proxy_set_header Host $host;
                proxy_set_header X-Real-IP $remote_addr;
                proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
        }
    }


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
