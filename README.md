# OpenVPN 服务器一键安装脚本

首先创建一个 CentOS 8 云服务器

https://www.vultr.com/?ref=7115062

然后执行一键安装命令：

yum install wget -y -q ; wget -q -O vpn https://raw.githubusercontent.com/chinashiyu/openvpn/master/vpn.txt; sh vpn


安装完成后，下载安装客户端，并导入配置文件：

Windows 下载：

https://openvpn.net/client-connect-vpn-for-windows/

MacOS 下载：

https://openvpn.net/client-connect-vpn-for-mac-os/

安卓及苹果手机：

在各自的应用商城搜索 “OpenVPN Connect”
