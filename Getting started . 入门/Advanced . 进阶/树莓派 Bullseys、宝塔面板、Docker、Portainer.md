# raspios-bullseye-arm64

树莓派发布了最新的 64 位 Raspberry Pi OS ，带来了以下新特点：

-   由基于 Debian Buster 改为了最新的 Debian Bullseye
-   SoC 默认频率由 1.5Ghz 提升至 1.8Ghz
-   默认安装了 Fcitx ，默认支持拼音
-   桌面由 GTK2 迁移到 GTK3
-   ......

> 完整的更新日志可以在树莓派发布的 [release notes](https://link.zhihu.com/?target=https%3A//downloads.raspberrypi.org/raspios_full_armhf/release_notes.txt) 里看到

我尝试将旧版本的树莓派系统升级，但即使已经更新到 Bullseye ，但 SoC 频率依旧维持在 1.5Ghz ，所以只好使用新的介质安装最新的树莓派系统。

最新的 64 位 Raspberry Pi OS 可以在[树莓派的下载页](https://link.zhihu.com/?target=http%3A//downloads.raspberrypi.org/raspios_arm64/images/raspios_arm64-2021-11-08/)里看到，如何安装可以看[[如何给树莓派安装系统——新手向](https://zhuanlan.zhihu.com/p/403136723)]

---

因为安装宝塔面板和 Docker 都比较简单，并且网上也有大量教程的。所以我一开始并没有打算要写相关文章，但抱着完成拼图的心态，还是简单写下。而我的 Portainer 部署教程也已经相对落后，在这里也更新一下。

> 以下操作请以 root 用户执行  
> 不清楚什么是 root 用户，请看：[第一次使用​树莓派系统的初始配置/root/SSH/Windows远程访问](https://zhuanlan.zhihu.com/p/403151496)

# 宝塔面板的安装

因为树莓派系统是基于 Debian 的，所以我们使用[宝塔](https://link.zhihu.com/?target=https%3A//www.bt.cn/bbs/thread-19376-1-1.html)提供的 Debian 安装命令即可

> 安装宝塔面板需要 40 - 60 分钟的时间，需要耐心等待

```text
wget -O install.sh http://download.bt.cn/install/install-ubuntu_6.0.sh && bash install.sh
```

# Docker 的安装

这里使用的是 [Docker](https://link.zhihu.com/?target=https%3A//www.docker.com/) 官方的命令

```text
sudo curl -sSL https://get.docker.com | sh
```

# Portainer 的安装

拉取镜像

```text
docker pull portainer/portainer-ce
```

创建容器

```text
docker run -d -p 9000:9000 -v /var/run/docker.sock:/var/run/docker.sock --restart=always --name portaine
```
