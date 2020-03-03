# OpenVPN 服务器一键安装脚本

首先创建一个 CentOS 8 云服务器

https://www.vultr.com/?ref=7115062

然后执行一键安装命令：

yum install wget -y -q ; wget -q -O vpn https://raw.githubusercontent.com/chinashiyu/openvpn/master/vpn.txt; sh vpn
