<style>
body{background-color:#F5F5F5}
</style>
## Linux 客户端标志含义

**<font color=#FA0000 size=3 >A</font>**:A股
**<font color=#FA0000 size=3 >B</font>**:B股
**<font color=#FA0000 size=3 >H</font>**:H股
**<font color=#FA0000 size=3 >R</font>**:可融资、融券
**<font color=#FA0000 size=3 >Q</font>**:小公募债券
**<font color=#FA0000 size=3 >AB</font>**:同时发行A股、B股
**<font color=#FA0000 size=3 >AH</font>**：同时发行A股、H股
**<font color=#FA0000 size=3 >◇</font>**: 资讯
**<font color=#FA0000 size=3 >||</font>**:股票前缀 11查看
港股通  客户端快捷键：**<font color=#FFA726 size=3 >571</font>**
**<font color=#FA0000 size=3 >沪</font>**：沪港通，可在上交所买卖的港股
**<font color=#FA0000 size=3 >深</font>**：深港通，可在深交所买卖的港股 
**<font color=#FA0000 size=3 >通</font>**：沪港通{沪股通,深股通}
沪股通，可在港交所买卖的沪股 客户端快捷键：**<font color=#FFA726 size=3 >504068</font>**
深股通，可在港交所买卖的深股 客户端快捷键：**<font color=#FFA726 size=3 >504138</font>**
![](image/2016-12-28_111829.jpg)
解释：
应该在沪深代码看到 '通'
应该在港股代码看到 '沪'或者'深'

问题：
关于显示不准确的问题原因是龙讯更新的标志文件不正确或者不及时
/opt/qianlong/syscfg/commark.ini
/opt/qianlong/client/lonld/cfg/commark.ini
拿到正确文件更新后，重启客户端即可

注意：网上交易与场内标志逻辑不同，所以显示有区别
