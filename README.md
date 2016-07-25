# enjoySerfingLife
Make your internet serfing time be enjoyable~!
1. 解决用PC版百度网盘下载视频时的窘境！
神器：aria2
第一步：安装Aria2
 https://github.com/tatsuhiro-t/aria2/releases/download/release-1.19.3/aria2-1.19.3-osx-darwin.dmg
 安装目录在 /usr/local/aria2 下
第二步： 下载Aria2所需文件
 参考：http://aria2c.com/usage.html 或 http://aria2.sourceforge.net/manual/en/html/aria2c.html
-----------------------------------------------------------------------------------
# Basic Options
dir=/Users/baidu/Downloads
input-file=/Applications/aria2c/session.dat
log=/Applications/aria2c/aria2.log
max-concurrent-downloads=15
max-connection-per-server=15
check-integrity=true
continue=true
# BitTorrent/Metalink Options
bt-enable-lpd=true
bt-max-open-files=16
bt-max-peers=8
dht-file-path=/opt/var/aria2/dht.dat
dht-file-path6=/opt/var/aria2/dht6.dat
dht-listen-port=6801
#enable-dht6=true
listen-port=6801
max-overall-upload-limit=0K
seed-ratio=0
# RPC Options
enable-rpc=true
rpc-allow-origin-all=true
rpc-listen-all=true
rpc-listen-port=6800
#rpc-secret=123456
#rpc-secure=true
# Advanced Options
daemon=true
disable-ipv6=true
#enable-mmap=true
force-save=true
file-allocation=none
log-level=warn
max-overall-download-limit=0K
save-session=/Applications/aria2c/session.dat
always-resume=true
split=10
min-split-size=10M
-----------------------------------------------------------------------------------
 复制以上的内容到新建的aria2.conf文件中
 dir=/Users/baidu/Downloads（第二行）的baidu是根目录的名字
 根目录下输入mkdir ~/.aria2生成隐形文件夹
 cp xxx/aria2.conf ~/.aria2，将改好的config文件放到这个隐形文件夹中，方便每次启动aria2c的时候不用每次手动输入配置文件的位置

第三步：运行Aria2
 命令行输入
 aria2c
 ps aux|grep aria2c
 出现如下说明设置好了！
----------------------------------------------------------------------------------------------------
MacBook-Pro:.aria2 evachen7878$ ps aux|grep aria2c
evachen7878     37781   0.0  0.0  2453272    804 s008  S+    3:40下午   0:00.01 grep aria2c
evachen7878     37779   0.0  0.0  2463712   1000   ??  Ss    3:40下午   0:00.00 aria2c
----------------------------------------------------------------------------------------------------

第四步：
神器GUI：http://ziahamza.github.io/webui-aria2/
百度盘：chrome中下载BaiduExporter: 
https://chrome.google.com/webstore/detail/baiduexporter/mjaenbjdjmgolhoafkohbhhbaiedbkno

然后直接打开网盘
导出下载出现ARIA2 RPC，先设置
User-agent需要设置为： netdisk;5.2.7;PC;PC-Windows;6.2.9200;WindowsBaiduYunGuanJia
referer 设置为：http://pan.baidu.com/disk/home
下载的时候点击这个就会在GUI中展现下载

第五步：
把 /usr/local/aria2/bin/aria2c 这个文件拖入到开机启动项实现开机启动，否则就要每次重复第三步



 
