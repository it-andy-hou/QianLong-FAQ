# Centos 7.2 系统DHCP服务问题

**问题描述:**

少量无盘站启动没问题，多台或者同时启动多台无盘站存在无法进去，拿不到IP地址的情况。无盘站dhcp获取地址与网页管理看到的地址不同，或存在IP地址+1的情况。

**<font color=#A52A2A>注意:此问题只存在Centos7.2系统上, Linux 6.2、Linux 7.0无这个问题</font>**
查看系统系统版本命令<code>cat /etc/redhat-release</code>

**解决办法：**

升级脚本下载地址

百度云地址：http://pan.baidu.com/s/1c1CWHos

**升级方法：**

1. 下载后会会得到一个**ql_fixed_dhcpd_20160930.tar.gz**的升级包，将文件通过ssh工具上传到/opt目录下
2. 执行命令进行解压和赋权操作

```
cd /opt/
tar -zxvf ql_fixed_dhcpd_20160930.tar.gz
chmod -R 777 ql_fixed_dhcpd_20160930.sh
sh ql_fixed_dhcpd_20160930.sh
```
执行完命令后会如下显示
<div class="daima" style="background-color:#000000 ">
<font color=#FFFFFF>
Extracting...
<font color=#FFD700>update.sh</font> <font color=#008000>is updating...</font>
cleaning system...
Upgrading software...
Preparing...　　　　　　　　　　　　　　################################# [100%]
Updating / installing...
　　1:dhcp-libs-12:4.2.5-43.el7.centos　################################# [ 13%]
　　2:dhcp-common-12:4.2.5-43.el7.cento################################# [ 25%]
　　3:dhclient-12:4.2.5-43.el7.centos　################################# [ 38%]
　　4:dhcp-12:4.2.5-43.el7.centos　　　################################# [ 50%]
Cleaning up / removing...
　　5:dhcp-12:4.2.5-42.el7.centos　　　################################# [ 63%]
　　6:dhclient-12:4.2.5-42.el7.centos　################################# [ 75%]
　　7:dhcp-common-12:4.2.5-42.el7.cento################################# [ 88%]
　　8:dhcp-libs-12:4.2.5-42.el7.centos　################################# [100%]
patching dhcpd.conf...
fixing permission...
restart dhcpd service.
Upgrade success!
<font color=#008000> Upgrade success!</font>
</font>
</div>

Upgrade success! 表示升级成功

**验证方法：**

重启客户端查看IP地址即可。
