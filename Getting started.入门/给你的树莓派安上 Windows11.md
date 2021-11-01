## 下载 Windows 11
我们打开「UUP dump」，搜索「Windows 11 ARM」 ，选择一个版本下载，建议下载到空闲空间大于 8G 的分区
> 选择语言，版本等这些过程就不截图演示了

![](https://pic4.zhimg.com/80/v2-c4039f9ea46b3a01cf32f0d43ddbc8b3_720w.jpg)
下载以后解压，运行 uup_download_windows.cmd 文件，然后程序会自动下载镜像
> Linux 系统运行 uup_download_linux.sh 文件  
> MacOS 系统运行 uup_download_macos.sh 文件  
> 你也可以在这个链接下载镜像，但不能保证是最新版  

![](https://pic1.zhimg.com/80/v2-ebb2824fbf23e01b5dc7630c5af9f3f8_720w.jpg)
## 写入镜像
将你的 SD 卡插入到电脑
> 也可以是U盘，或者SSD，不过这些设备不适用于这篇教程

然后下载「Windows on Raspberry」，解压并使用
选择正确的存储器和正确的树莓派
![](https://pic2.zhimg.com/80/v2-b1ae226348641ede47648211583ebed5_720w.jpg)
选择之前下载好的镜像，并选择要安装的 Windows 版本
![](https://pic4.zhimg.com/80/v2-9ae18579364d2a4a4efecdb194ecb663_720w.jpg)
> 驱动程序选择「使用服务器上提供的最新驱动程序包」
> UEFI 固件选择「使用服务器上提供的最新固件」
> 配置页面可以直接点击「下一步」
> 最后执行安装

![](https://pic3.zhimg.com/80/v2-6425c343666dfe2c6578fba67f432d8a_720w.jpg)
然后我们就可以弹出 SD 卡，将 SD 卡插入到树莓派上并开机了
## 配置
我们还可以对系统进行设置，以更好地体验 Windows 11
> 由于我没有采集卡，所以以下截图来自这个文章

在显示树莓派图标时，按下 ESC 键进入设置
![](https://pic4.zhimg.com/80/v2-c3be2a58de9fcb4980af6e238e4b306b_720w.jpg)
在「Device Manager」中，选择「Select Raspberry Pi Configuration」，进入「Select Advanced Configuration」。将「Limit RAM to 3 GB」设置为「Disabled」，并按下 F10 保存。
![](https://pic3.zhimg.com/80/v2-198457d0429ac4272e200a36fca6798e_720w.jpg)
回到 「Select Raspberry Pi Configuration」，选择「Display Configuration」，设置分辨率，并按下 F10 保存。
![](https://pic3.zhimg.com/80/v2-93caa4735132821e0b2702206a5959ba_720w.jpg)
> 并且我们需要在 BIOS 里设置启动顺序，否则树莓派默认从网络启动，需要等十几分钟
> 或者你也可以在树莓派界面显示时按下回车键以进入 Boot 界面

最后退出设置并重启以进入 Windows 11
