Shadowsocks libev版一键安装脚本

本脚本适用环境：
系统支持：CentOS、Debian/Ubuntu
内存要求：≥128M
日期：2018 年 02 月 07 日

关于本脚本：
一键安装 libev 版的 Shadowsocks 最新版本。该版本的特点是内存占用小（600k左右），低 CPU 消耗，甚至可以安装在基于 OpenWRT 的路由器上。

默认配置：
服务器端口：自己设定（如不设定，默认从 9000-19999 之间随机生成）
密码：自己设定（如不设定，默认为teddysun.com）
加密方式：自己设定（如不设定，默认为 aes-256-gcm）

Shadowsocks for Windows 客户端下载：
https://github.com/shadowsocks/shadowsocks-windows/releases

使用方法：
使用root用户登录，运行以下命令：
适用于 CentOS 系统

wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-libev.sh
chmod +x shadowsocks-libev.sh
./shadowsocks-libev.sh 2>&1 | tee shadowsocks-libev.log
适用于 Debian/Ubuntu 系统

wget --no-check-certificate https://raw.githubusercontent.com/teddysun/shadowsocks_install/master/shadowsocks-libev-debian.sh
chmod +x shadowsocks-libev-debian.sh
./shadowsocks-libev-debian.sh 2>&1 | tee shadowsocks-libev-debian.log
安装完成后，脚本提示如下：

Congratulations, Shadowsocks-libev server install completed!
Your Server IP        :your_server_ip
Your Server Port      :your_server_port
Your Password         :your_password
Your Encryption Method:your_encryption_method

Welcome to visit:http://teddysun.com/357.html
Enjoy it!
卸载方法：
使用 root 用户登录，运行以下命令：
适用于 CentOS 系统

./shadowsocks-libev.sh uninstall
适用于 Debian/Ubuntu 系统

./shadowsocks-libev-debian.sh uninstall
安装完成后即已后台启动 Shadowsocks-libev。
本脚本安装完成后，会自动将 Shadowsocks-libev 加入开机自启动。

使用命令：
启动：/etc/init.d/shadowsocks start
停止：/etc/init.d/shadowsocks stop
重启：/etc/init.d/shadowsocks restart
查看状态：/etc/init.d/shadowsocks status

更新日志：
2018 年 02 月 07 日：
1、修改：将默认端口从 8989 改为从 9000-19999 之间随机生成。
2017 年 07 月 22 日：
1、修正：默认加密方式从 aes-256-cfb 改为 aes-256-gcm（官方原版客户端支持该加密方式）；
2、新增：安装时可选 16 种加密方式的其中之一。如下所示：

aes-256-gcm
aes-192-gcm
aes-128-gcm
aes-256-ctr
aes-192-ctr
aes-128-ctr
aes-256-cfb
aes-192-cfb
aes-128-cfb
camellia-128-cfb
camellia-192-cfb
camellia-256-cfb
chacha20-ietf-poly1305
chacha20-ietf
chacha20
rc4-md5
