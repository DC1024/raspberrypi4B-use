# 服务器是什么？
当说到服务器的时候，你可能想到的是这种庞然大物
![](http://image.dcchen.top/www/wwwroot/easyImages/image20212021/09/20/finidh.png)
但其实，这种小设备也是服务器
![](http://image.dcchen.top/www/wwwroot/easyImages/image20212021/09/20/fjdz98.png)
就我个人的理解，只要是为其它设备或人提供服务的设备，就能称作服务器。
# 我的服务器
我用的服务器是 RPI4B ，也就是树莓派，如果你不了解什么是树莓派的话，可以看看[[树莓派是什么？怎么入坑？全指南！]]
如果你想自己接触服务器领域，可以看看云服务器或者尝试在自己的手机上搭建网站。当对服务器有一定理解再考虑是否购入专业设备。
# 我用服务器做了什么？
#### 环境搭建
所谓环境，就是支撑服务的软件。比如我要搭建一个网站，我就需要安装 Nginx ，如果这个网站需要数据库或者需要 PHP 的支持，我还得安上 MySQL 和 PHP 。这样网站才能运行。
* LNMP
LNMP 即 Linux+Nginx+MySQL+PHP，安装好 LNMP 也就是搭建好了网站环境。通过 LNMP 我们可以搭建各式各样的网站。
* Docker
Docker是一个虚拟环境容器，你可以使用镜像创建容器，快速搭建服务

#### 我通过 LNMP 和 Docker 做了什么
我的服务，有些是独立的服务，但也有些服务是为了其它应用更好的使用。
* 基于 LNMP 使用 WordPress 搭建了一个博客
* 基于 Docker ，通过 Ubuntu 镜像搭建了 ASF Steam 服务
* 基于 Docker ，通过 Ubuntu 镜像搭建了 Minecraft 服务器
* 基于 Docker ，通过 searxng 镜像搭建了一个聚合搜索引擎
* 基于 Docker ，通过 Portainer 镜像搭建了一个 Docker 管理面板
* 基于 Docker ，通过 HomeAssistant 镜像搭建了家庭智能家居管理系统
* 基于 Docker ，通过 frpc 镜像搭建了多个服务于服务器服务的内网映射服务
* 基于 LNMP 使用 TinyTinyRSS 搭建了一个 RSS 系统；通过 Docker 搭建 RSSHUB 提高信息获取能力；通过 Docker 搭建 WallaBag 加强收集能力
* 基于 LNMP 使用简单图床搭建了一个图床服务；基于 Docker ，通过 NextCloud 镜像搭建了同步云服务。图床服务用于存储 Obsidian 中的图片，同步云用于在不同设备上同步 Obsidian 文件。

#### 服务器性能
在服务器上搭建了这么多服务，自然性能也是要被消耗的。这些服务加起来，吃得最厉害的就是内存了。
我的 8G 树莓派，在同时运行以上服务以后，内存使用 4.8G ，占比 63% 。
