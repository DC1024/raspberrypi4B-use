由于树莓派默认是使用 SD 卡进行系统启动，但 SD 卡运行操作系统会导致寿命缩短。所以我们可以使用更靠谱一点的 U 盘甚至 SSD 来启动树莓派。

根据不同情况有不同的启动办法，分别是**基于你已经使用 SD 卡运行树莓派的情况下**和**没有给 SD 卡刷入系统的情况下**

## 基于你已经使用 SD 卡运行树莓派的情况下

我们先查看 bootloader 版本，版本更新日期需要大于 2020 年 8 月 20 日。

```text
vcgencmd bootloader_version
```

然后我们在树莓派内输入以下命令，进入树莓派设置

```text
sudo raspi-config
```

进入「Advanced Options」→「Boot Order」，选择「USB Boot」并回车确定

然后我们就可以关机，拔出 SD 卡，插入已经刷好系统的 USB 设备并启动树莓派

## 没有给 **SD 卡刷入系统的情况下**

我们使用「[Raspberry Pi Imager](https://link.zhihu.com/?target=https%3A//www.raspberrypi.org/software/)」，在「Operating System」下选择「CHOOSE OS」，找到「Misc utillity images」，选择「Bootloader」，选择「USB Boot」并刷入