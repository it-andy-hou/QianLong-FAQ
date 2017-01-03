# 钱龙程序延期

## Novell 延期
用    途：适用网络版并口或者usb口软件狗用户的日期延长

延期文件：

延期程序： upgrade.exe

辅助文件1  rtm.exe

辅助文件2：Dpmi16bi.ovl

密码文件1：ml××××.ql4(×××× 代表客户编号)

密码文件2：ml××××.ql6(期货用户、双龙用户、委托用户需要）

说明文件:  readme.txt

### 步    骤：
![](http://7xlgx2.com1.z0.glb.clouddn.com/yanqi.gif)

一、DOS无盘站上操作：

 1.将延长年限目录“upgrade”拷贝至novell服务器上任一盘符下

 2.确认延期目录中已有上述延期文件、且对应客户编号和软件狗上标识一致

 2.在插有软件狗的无盘站上运行延期程序

   a.若ml45所在盘符为F盘，可直接运行upgrade.exe

   b.若ml45所在盘符不是F盘，则运行upgrade.exe /P=X:\ml45(X为ml45所在盘符）

   如每一步均提示“OK”表示使用年限延长成功(总共5个ok)

二、windows工作站上操作：

 1.确认windos工作站上已经安装并口驱动

 2.将延长年限目录“upgrade”拷贝至windows工作站上任一盘符下

 3.确认延长年限目录中已有上述延期文件、且对应客户编号和软件狗上标识一致

 4.在插有软件狗的windows工作站上运行延期程序

   a.若ml45所在盘符为F盘，可直接运行upgrade.exe

   b.若ml45所在盘符不是F盘，则运行upgrade.exe /P=X:\ml45(X为ml45所在盘符）

   如每一步均提示“OK”表示使用年限延长成功(总共5个ok)

验证延期与否：

 1.到ML45\SYSTEM目录下执行MANAGER.EXE，在主界面按下“ALT+H”弹出产品信息框，查看钱龙到期日是否已延长。

 2.若是DOS转码机重新启动转码机程序，初始化后再启动任何一台工作站查看动态分析系统。如转换机上的到期日已经延长，并且动态分析系统右下角有时间显示，则安装成功。

 若是windows转码机重新开启转码机程序进行初始化，可正常开启且“基本信息”界面到期日已延长，则延期成功

---------------

## Novell故障处理
#### 1、使用UPGRADE做延期时第一步或第四步提示“T_Lock not found!”或者“upgrade t-lock error！”。多次更换无盘站无效。

A．将并口狗插入windows 有盘站上，并拷贝服务器映射盘符内的ml45\system\driver目录下的BKDRIVER.RAR至windows本机解压缩，执行解压后的setup.exe，完成并口狗驱动安装后，cmd命令行下进行upgrade延期。

#### 2、使用UPGRADE做延期时第二步报错“Target path error！”，提示无法找到文件路径。

A.当前ML45的路径非F盘，重新UPGRADE并指定ML45路径，例如upgrade.exe /p=z:\ml45。

B.ML45\SYSCFG目录下不存在MLDATA.QL4文件或文件已损坏，请先拷贝一个MLDATA.QL4文件至该目录下再做UPGRADE。

#### 3、使用UPGRADE做延期时第三步报错“Copy ql4 file error！”，提示无法拷贝文件。

A.upgrade目录下存在多个ml*.ql4文件，清除多余的ml*.ql4文件后重做upgrade。

B.ML45\SYSCFG目录下的mldata.ql4文件被设定为只读，改为存档后重新upgrade。

C.当前用户没有足够的操作权限，请重新赋权后做延期。

------------------

## linux 延期
密码文件1：ml××××.ql4

密码文件2：ml××××.ql6

1、 将两个授权文件重命名为 mldata.ql4 mldata.ql6 (区分大小写，要小写)

2、 将两个改名后的文件通过ssh工具上传到opt/qianlong/right/目录下

然后执行赋权命令
```
chmod -R 777 /opt/qianlong
chown -R qianlong:qianlong /opt/qianlong
```
3、验证延期是否成功 重启转码机后在系统状态里的转码状态查看日期是否延长。
