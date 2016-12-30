# 补数据教程

## 补数据需求 **<font color=#87CEFA size=3 >(可以理解为官方只支持补日线数据)</font>**
**<font color=#996600 size=3 > 补当日或者前几日 分时／实时 数据</font>** 推荐使用 **方法四、方法二**
**<font color=#996600 size=3 > 补当日k线数据</font>** 推荐使用 **方法三、方法四、方法二**
**<font color=#996600 size=3 > 补当日分钟线、月线、全息资料</font>** 推荐使用 **方法四、方法二**
**<font color=#996600 size=3 > 补个股或市场区间k线</font>** 推荐使用 **方法一、方法四、方法二**
**<font color=#996600 size=3 > 补历史全部资料</font>** 推荐使用 **方法四、方法二** 和 **方法五**
**<font color=#996600 size=3 > 补龙讯F10、权息资料</font>** 推荐使用 **方法五**

## 关于补数据的方法

#### 方法一、rt服务器下载
**rt服务器地址 电信线路1: 122.226.188.39  |  电信线路2: 61.174.50.181   |  联通线路: 101.64.236.181 **
**<font color=#ff9900 size=2 >  ⚠ rt服务器只能补日线！</font>**
```
说明：关于rt服务器指的就是daydown下载工具所连接的服务器ip，Novell与Linux通用。
```
#### 方法二、Novell与Linux互相拷贝 **<font color=#cc3300 size=4 >Novell与Linux 沪深期货数据通用（ 港股通、股转不通用 ）</font>**
**<font color=#ff9900 size=2 >⚠ Novell向Linux拷贝数据，注意要转换小写！ </font>**  | 转小写批处理： [微云](http://share.weiyun.com/10acfe290b54c23e783e1b0edf2ee920)/[百度云](http://pan.baidu.com/s/1mhHwsoK)
```
使用方法：将批处理放到需要转换大小写文件夹的同目录，直接执行即可，会将通目录和子目录一并转换小写。
```
#### 方法三、官网下载 [linux wmanager补数据方法](Lwmamager.md)
**<font color=#ff9900 size=2 >  ⚠ 官方只能补日线！当日k线17点更新 使用wmanager工具</font>**
下载地址 http://www.qianlong.com.cn/soft/download_data.aspx

#### 方法四、其他营业部、其他服务器拷贝

#### 方法五、龙讯F10官网下载
**<font color=#ff9900 size=2 >  ⚠ 每周五更新 信龙官网 [xlinfo.cn](http://www.xlinfo.cn/)   首页>技术支持>数据下载</font>**

----------

## Linux 数据对应目录

### 补分时（实时）数据
```
当日（实时）分时

上海分时数据位置opt/qianlong/sysdata/realtime/shase/除文件夹以外的其他文件

深圳分时数据位置opt/qianlong/sysdata/realtime/sznse/除文件夹以外的其他文件

港股通分时数据位置opt/qianlong/sysdata/realtime/hk2sh/除文件夹以外的其他文件

期货分时数据位置opt/qianlong/sysdata/realtime/cnfol/除文件夹以外的其他文件

股份转让分时数据位置opt/qianlong/sysdata/realtime/neeq/除文件夹以外的其他文件

--------------
前几天的分时

上海日线位置opt/qianlong/sysdata/realtime/shase/年月日.dat 的文件夹

深圳日线位置opt/qianlong/sysdata/realtime/sznse/年月日.dat 的文件夹

港股通日线位置opt/qianlong/sysdata/realtime/hk2sh/年月日.dat 的文件夹

期货日线位置opt/qianlong/sysdata/realtime/cnfol/年月日.dat 的文件夹

股份转让日线位置opt/qianlong/sysdata/realtime/年月日.dat 的文件夹
```


### 补历史数据
```
日线

上海日线位置opt/qianlong/sysdata/history/shase/day

深圳日线位置opt/qianlong/sysdata/history/sznse/day

港股通日线位置opt/qianlong/sysdata/history/hk2sh/kday

期货日线位置opt/qianlong/sysdata/history/cnfol/day

股份转让日线位置opt/qianlong/sysdata/history/neeq/day

-------------
月线

港股通月线位置opt/qianlong/sysdata/history/hk2sh/kmon

股份转让月线位置opt/qianlong/sysdata/history/kmon

-------------
分钟线

上海一分钟线位置opt/qianlong/sysdata/history/shase/1mn

上海五分钟线位置opt/qianlong/sysdata/history/shase/min

深圳一分钟线位置opt/qianlong/sysdata/history/sznse/1mn

深圳五分钟线位置opt/qianlong/sysdata/history/sznse/min

港股通一分钟线位置opt/qianlong/sysdata/history/hk2sh/kmn1

港股通十五分钟线位置opt/qianlong/sysdata/history/hk2sh/km15

期货一分钟线位置opt/qianlong/sysdata/history/cnfol/1mn

期货五分钟线位置opt/qianlong/sysdata/history/cnfol/min

股份转让一分钟线位置opt/qianlong/sysdata/history/kmn1

股份转让十五分钟线位置opt/qianlong/sysdata/history/km15
```
-------------
全息资料
```
上海日线位置opt/qianlong/sysdata/history/shase/weight

深圳日线位置opt/qianlong/sysdata/history/sznse/weight

港股通日线位置opt/qianlong/sysdata/history/hk2sh/weight

期货日线位置opt/qianlong/sysdata/history/cnfol/weight

股份转让日线位置opt/qianlong/sysdata/history/neeq/weight
```

**Linux操作系统下，以上所有文件操作请使用qianlong用户执行，操作完成后无需执行赋权命令！**

-------------

## Novell 数据对应目录

### 补分时（实时）数据
```
当日（实时）分时

上海分时数据位置ml45/sysdata/realtime/shase/除文件夹以外的其他文件

深圳分时数据位置ml45/sysdata/realtime/sznse/除文件夹以外的其他文件

港股通分时数据位置ml45/sysdata/realtime/hk2sh/除文件夹以外的其他文件

期货分时数据位置ml45/sysdata/realtime/cnfol/除文件夹以外的其他文件

股份转让分时数据位置ml45/sysdata/realtime/neeq/除文件夹以外的其他文件

--------------
前几天的分时

上海日线位置ml45/sysdata/realtime/shase/年月日.dat 的文件夹

深圳日线位置ml45/sysdata/realtime/sznse/年月日.dat 的文件夹

港股通日线位置ml45/sysdata/realtime/hk2sh/年月日.dat 的文件夹

期货日线位置ml45/sysdata/realtime/cnfol/年月日.dat 的文件夹

股份转让日线位置ml45/sysdata/realtime/年月日.dat 的文件夹
```

### 补历史数据
```
日线

上海日线位置ml45/sysdata/history/shase/day

深圳日线位置ml45/sysdata/history/sznse/day

港股通日线位置ml45/sysdata/history/hk2sh/day

期货日线位置ml45/sysdata/history/cnfol/day

股份转让日线位置ml45/sysdata/history/neeq/day

-------------
月线

港股通月线位置ml45/sysdata/history/hk2sh/kmon

股份转让月线位置ml45/sysdata/history/kmon

-------------
分钟线

上海一分钟线位置ml45/sysdata/history/shase/1mn

上海五分钟线位置ml45/sysdata/history/shase/min

深圳一分钟线位置ml45/sysdata/history/sznse/1mn

深圳五分钟线位置ml45/sysdata/history/sznse/min

港股通一分钟线位置ml45/sysdata/history/hk2sh/kmn1

港股通十五分钟线位置ml45/sysdata/history/hk2sh/km15

期货一分钟线位置ml45/sysdata/history/cnfol/1mn

期货五分钟线位置ml45/sysdata/history/cnfol/min

股份转让一分钟线位置ml45/sysdata/history/kmn1

股份转让十五分钟线位置ml45/sysdata/history/km15
```
-------------
权息资料  
```
上海日线位置ml45/sysdata/realtime/shase/weight

深圳日线位置ml45/sysdata/realtime/sznse/weight

港股通日线位置ml45/sysdata/history/hk2sh/weight

期货日线位置ml45/sysdata/history/cnfol/weight

股份转让日线位置ml45/sysdata/history/neeq/weight
```

## 龙讯F10

### linux 龙讯F10

 信龙官网 [xlinfo.cn](http://www.xlinfo.cn/)  **首页>技术支持>数据下载**

|历史咨询| 下载地址|备注|
| ------ |:----------:|:----------:|
|LINUX版龙讯C系列F10完整历史数据|[下载](http://www.xlinfo.cn/server/server10.html)|(每周五更新)|
|龙讯权息weight历史数据包|[下载](http://www.xlinfo.cn/server/server10.html)|(每周五更新)|
