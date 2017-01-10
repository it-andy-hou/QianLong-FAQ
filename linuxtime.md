# linux修改时间以及修改时区

在类UNIX系统中，日期被存储为一个整数，其大小为自世界标准时间（UTC）
## 查看时间
```
date
```

## 修改时间
```
date -s   //设置当前时间，只有root权限才能设置，其他只能查看
date -s 20120523   //设置成20120523，这样会把具体时间设置成空00:00:00
date -s 01:01:01   //设置具体时间，不会对日期做更改
date -s "01:01:01 2012-05-23"   //这样可以设置全部时间
date -s "01:01:01 20120523"   //这样可以设置全部时间
date -s "2012-05-23 01:01:01"   //这样可以设置全部时间
date -s "20120523 01:01:01"   //这样可以设置全部时间

hwclock -w     //将当前时间和日期写入BIOS，避免重启后失效
```

## 查看时区
```
date -R
```
会显示"Thu, 28 Jul 2016 09:16:38 +0800"

## Centos 7.2 / Redhat 7.0 修改时区方法

使用下面的命令来更改时区为 Asia/Shanghai
```
timedatectl set-timezone Asia/Shanghai
```
时区就修改完成了
<!-- 
```
tzselect
```
显示如下
```
Please identify a location so that time zone rules can be set correctly.
Please select a continent or ocean.
 1) Africa
 2) Americas
 3) Antarctica
 4) Arctic Ocean
 5) Asia
 6) Atlantic Ocean
 7) Australia
 8) Europe
 9) Indian Ocean
10) Pacific Ocean
11) none - I want to specify the time zone using the Posix TZ format.
#5    //输入5 按回车
```
会显示如下
```
Please select a country.
 1) Afghanistan           18) Israel                35) Palestine
 2) Armenia               19) Japan                 36) Philippines
 3) Azerbaijan            20) Jordan                37) Qatar
 4) Bahrain               21) Kazakhstan            38) Russia
 5) Bangladesh            22) Korea (North)         39) Saudi Arabia
 6) Bhutan                23) Korea (South)         40) Singapore
 7) Brunei                24) Kuwait                41) Sri Lanka
 8) Cambodia              25) Kyrgyzstan            42) Syria
 9) China                 26) Laos                  43) Taiwan
10) Cyprus                27) Lebanon               44) Tajikistan
11) East Timor            28) Macau                 45) Thailand
12) Georgia               29) Malaysia              46) Turkmenistan
13) Hong Kong             30) Mongolia              47) United Arab Emirates
14) India                 31) Myanmar (Burma)       48) Uzbekistan
15) Indonesia             32) Nepal                 49) Vietnam
16) Iran                  33) Oman                  50) Yemen
17) Iraq                  34) Pakistan
#?9   //输入9 按回车
```
会显示
```
Please select one of the following time zone regions.
1) Beijing Time
2) Xinjiang Time
#?1      //输入1按回车   这步会因为系统版本略有不同，但是都选beijing时间就好了

```
```
The following information has been given:

        China
        Beijing Time

Therefore TZ='Asia/Shanghai' will be used.
Local time is now:      Thu Jul 28 09:52:20 CST 2016.
Universal Time is now:  Thu Jul 28 01:52:20 UTC 2016.
Is the above information OK?
1) Yes
2) No
#?1    //输入1按回车
```
 -->


