# 新股代码看不到

## 原因

首先要知道新股代码一般是早上，行情库才刷新到行情库里的，钱龙转码机在初始化的时候去读库文件或者流数据，如果**初始化的时候库里没有新股代码**，那行情开始即使行情库刷新，库里有新股客户端也是不会显示的。

Linux存在问题，可能因为点对点程序开晚了，或者点对点程序故障导致**fjy年月日.txt**没能即使传入服务器上，初始化没有读到库文件，所以没有新股代码。

### 上海
转码show2003新股在**show2003.dbf**里。

转码fast行情库的新股在**fjy年月日.txt**里。

### 深圳

转码sjshq.dnf新股就在**sjshq.dnf**里。

深圳新一代的话，数据是以流模式，新股数据就在流数据里。

## Linux解决方法

**1.如果是刚开盘的时候发现的，可以考虑重新初始化来解决。（如果介意拉直线可以考虑方法2）**

重新初始化会让之前的分时数据拉直线，客户端会断开连接，这点需要知道。

**重新初始化步骤**：打开web管理页面→停掉L2DCD转码机→停掉服务平台（客户端会断开）

→L2DCD转码机下拉菜单选择对应市场重新初始化→开启转码机→开启服务平台


**2.如果发现时间已经是在盘中了，那就只能等到中午去解决。**

中午去找其他营业部拷贝一份对应的实时文件即可。

实时数据路径

上海：opt/qianlong/sysdata/realtime/shase/

深圳：opt/qianlong/sysdata/realtime/sznse/

**步骤**：停掉L2DCD转码机→停掉服务平台（客户端会断开）→将实时文件通过ssh工具上传到对应目录→赋权→开启转码机→开启服务平台

替换完成要赋权，赋权命令如下
```
chmod -R 777 /opt/qianlong
chown -R qianlong:qianlong /opt/qianlong
```

## Novell解决方法

**1.如果是刚开盘的时候发现的，可以考虑重新初始化来解决。（如果介意拉直线可以考虑方法2）**

Novell重新初始化方法：

方法一、

转码机L2DCD桌面快捷方式→右键属性→目标一栏最后加```/isha```→确定→重开转码机 （上海重做初始化）

转码机L2DCD桌面快捷方式→右键属性→目标一栏最后加```/iszn```→确定→重开转码机 （深圳重做初始化）

方法二、

**<font color=#ff9900 size=3 >  ⚠ 删除对应市场分时数据！</font>**

上海分时数据位置ml45/sysdata/realtime/shase/除文件夹以外的其他文件

深圳分时数据位置ml45/sysdata/realtime/sznse/除文件夹以外的其他文件