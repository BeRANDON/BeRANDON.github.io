2016-01-06-Galaxy-Note5-Manual-Guide.md
===

@(_blog)[Manual, HardDevices]

- **Usage Background** ：I only have bought two new smart-phones (including old cell-phones) in my life. The former one is G7 by HTC which is also the 'Yearly King of Smart-Phone' in 2011. Galaxy Note 5 is considered as the most beautiful one of Note Serial by April,2015. I chose it because its high quality screen, S-Pen, dual sim-card, finger-print sensor and samsung brand. The most different feature between android phone & iPhone is the flexibility of system control. User (specially the hacker) can customise his own android phone if he know how to cross-complied or surf smart-phone forum frequently.  
- **Dynamic Principle** ：With this guide, one should easily build the whole working status of Galaxy Note5 from a raw status. This principle requires reader not to treat Note5 as a secret stable hard device, but as a temporary working hardware terminal. ***All the personal data should be backup and store in cloud, while all build-up scripts should be written and stored completely.***
- **Keep Developing** : The hidden facility of android and Note5 are wait for discovered and developed. Keep working and developing to improve your own productivity. Remember the reason why you buy a such expensive phone, not just for entertainment, not just for parade, but for self-improvement. 

-------------------

[TOC]

## 刷系统

`Source List:`
> 1. 下载[Odin_3.10](http://pan.baidu.com/s/1kT85EBX)：windows平台下三星特用刷机软件。可自行google最新版本下载。
> 2. 下载[Samsung Smart-phone  Drive]()：微软平台的三星手机驱动。刷机工作还是windows平台的天下，手机驱动针对微软平台的较多。
> 3.  下载[N9200ZCU2AOL9_5.1.1_ALL_CHC.7z](http://pan.baidu.com/s/1nu1K26l)，为国行五件套，解救砖机特用。
> 4. 下载[N9200_TGY_N9200ZHU2AOKA](http://pan.baidu.com/s/1LxZUA)，港版救砖五件套，好处就是google play都是杠杠的；可是国行系统也有[一些不错特性](http://bbs.gfan.com/android-8064088-1-1.html)，如中国节假日，通话录音，静音拍照，而且比港版要精简。
> 5. 下载[Note5-SM-N9200_Android_5.1.1_ZCU2AOK6_Kernel-Official（ROOT2.56）_By_MaLong.tar (提取码yvid)](http://bbs.gfan.com/android-8131310-1-1.html)，这是我唯一刷成功的MaLong版本的Root内核（利用Odin的BL刷入即可）。

### 刷三星原厂系统

> 如果刷的是国行或港版的官方系统，就不需要刷BootLoader或Root。
> 一般来说，三星手机可以用多种方法刷机，推荐Odin线刷。
> 如果是型号N9200，即大陆或香港型号，可以下载国行五件套或港版五件套来刷机。
 
失败刷系统连接：
* 国外一个网站[Samsung Mobile Firmware for N9200](http://www.sammobile.com/firmwares/database/SM-N9200/)专门放着三星的刷机固件，可是没有对应的BootLoader等五件套，并未刷成功过。
* (http://www.galaxyrom.com/2015/12/4998.html)


### BootLoader 解锁

据说，港版和大陆版的Note5都把BootLoader上锁了，因此需要使用三星自带的`Crom Service`来进行解锁。`切记要在三星市场里下载官网Crom Service Apk，不要在网上下载。`个人经验，一开始刷不成功；换了一个网络之后才成功的（原来的是教育网）。

### Root 

Note5 有不同的型号，大陆和港版的都是N9200，台湾，欧美，日韩的都不一样。而xda论坛上的多是针对非N9200版本的刷机教程。有一位[越南geek](http://forum.xda-developers.com/note5/development/dev-pre-root-firmware-twrp-testing-t3183877)在github上发展了一个Root Chain，里面有针对N9200的编译版本，可惜我并未成功安装。

> 截止`12.Jan.2016`，我所使用的所有国内，国外一键刷机软件都root失败，估计是因为相对kernel固件没有发布。唯一显示成功的还是国外的[OneClickRoot](https://www.search4roots.com/how-to-root-samsung-note-5/)，可是要收费；不尝试。决定手动root。

失败的root教程如下，但可以借鉴：
* http://www.skyneel.com/2016/01/root-samsung-galaxy-note-5-sm-n9200.html
* http://www.smartphoneclinics.com/root-tutorial-samsung-galaxy-note-5-sm-n9200/
* 

### [多用户](http://forum.xda-developers.com/note5/general/mod-enable-multi-user-mode-note-5-t3225662)：

前提条件：手机系统Root成功，安装Terminal或者RootExploer来编辑`/system/build.prop`文件，写入如下代码（实践得出，四行代码都需要）

```
#Enable MultiUser Support
fw.power_user_switcher=1
fw.show_hidden_users=1
fw.show_multiuserui=1
fw.max_users=10
```

其中，show_hidden_users如果缺失，就无法在系统设置界面显示；而max_users就是最多用户数量吧，设置为3~7就可以了。

`其中，华为Mate有一个访客模式，可以依靠指纹进入不同的系统用户。而这一点是Note5无法做到的；期待大神打造；毕竟当初选用指纹识别手机，其中重要作用就是多用户办公。`

## 系统使用技巧

> 使用技巧Tips，用google搜索即可，youtube也有很多视频。

### 文件传输管理

数据线和OTG存储盘的传输固然是好，可是如果没有携带软件，可怎么办。

1. 局域网传输
小米文件管理apk很不错，可以通过无线局域网，FTP共享文件夹，进行文件的传输或者编辑。在Google Play上有个`File 文件大师`也可以实现类似FTP功能。  
一般来说蓝牙文件传输，以及苹果系统的AirDrop其实更先进。暂时没时间进行研究。

2. 互联网传输
利用通用的云服务即可，如微信，QQ文件传输；如google drive，dropbox同步服务等。

### 省电模式

减少亮度，空闲模式下关闭网络等。

### 超级省电模式

变成黑白模式，多种服务能删减就删减。

### 私密模式

可以把想隐藏的照片等隐藏起来。

## 软件介绍

### Termux

`pro:` 安装量10万；和音量键组成不同快捷键输入；
`con:` 

### Chrome

`pro:` Pre-installed  
`con:` Totally different services form desktop version

## Outlook Suggestion

Since my galaxy note5 is colored as champange-golden, therefore, I suggest you use the following pictures from app `Zedge`.
![Alt text](./Gold_lines_Abstract-wallpaper-10541542.jpg)
![Alt text](./Winter-wallpaper-10805825.jpg)
![Alt text](./Mixed_Blue-wallpaper-10736455.jpg)
 
