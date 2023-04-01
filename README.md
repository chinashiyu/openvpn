# OpenVPN 服务器一键安装脚本


## 购买云服务器

* 有很多种的云服务商
    * Vultr
    * 搬瓦工
    * 阿里云
    * 腾讯云

### Vultr

购买一个 5 美元的 CentOS 8 云服务器

购买地址 https://www.vultr.com/?ref=7115062


### 搬瓦工

<https://bandwagonhost.com/>


## openvpn安装配置

> 备注部分服务器无法直接执行一键安装，可能需要一些补充的配置

然后执行一键安装命令：

yum install wget -y -q ; wget -q -O vpn https://raw.githubusercontent.com/chinashiyu/openvpn/master/vpn.txt; sh vpn


### 搬瓦工服务器

修改服务器firewalld配置，开放ssh端口，不然可能会导致ssh连接不成功。导致后面无法成功

* 查看ssh对应的端口

```
cat /etc/ssh/sshd_config | grep Port
```

比如我的输出为, 这个28825就是端口号

```
#GatewayPorts no
Port 28825
```

* 然后修改 `/etc/firewalld/zones/public.xml`成下面这个样，一般用vi

```
<?xml version="1.0" encoding="utf-8"?>
<zone>
  <short>Public</short>
  <description>For use in public areas. You do not trust the other computers on networks to not harm your computer. Only selected incoming connections are accepted.</description>
  <service name="ssh"/>
  <service name="dhcpv6-client"/>
  <service name="cockpit"/>
  <port port="28825" protocol="tcp"/>
</zone>
```

之后再用上面的一件安装命令就好了

### 腾讯云等其他云服务商

像阿里云，腾讯云服务商，得在云服务商的管理平台上，手动设置防火墙规则。可以把所有TCP端口都打开就行了。




## 客户端使用

安装完成后，下载安装客户端，并导入配置文件：

Windows 下载：

https://openvpn.net/client-connect-vpn-for-windows/

MacOS 下载：

https://openvpn.net/client-connect-vpn-for-mac-os/

安卓及苹果手机：

在各自的应用商城搜索 “OpenVPN Connect”
