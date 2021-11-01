之前写了一篇如何「[使用Docker在服务器上搭建ASF挂卡](https://zhuanlan.zhihu.com/p/399544075)」的文章，但这篇文章对使用 ARM 架构的树莓派不太适用，因此重写一篇。

## 创建容器

首先创建一个 Docker 容器，可以是任何 Linux 发行版，我这里使用的是 debian 。然后映射容器 1242 端口。

## 准备工作

```text
apt update
apt-get install sudo
apt-get install wget
apt-get install unzip
```

## 安装 .NET Core SDK

> 下载源地址：[.NET Downloads (Linux, macOS, and Windows) (microsoft.com)](https://link.zhihu.com/?target=https%3A//dotnet.microsoft.com/download/dotnet%3Futm_source%3Dgetdotnetcorecli%26utm_medium%3Dreferral)

```text
wget https://download.visualstudio.microsoft.com/download/pr/70bdb5a9-34cc-4f28-aa33-15535f73b593/7d31d53187c8937206bcc3b117b88978/dotnet-sdk-5.0.400-linux-arm.tar.gz
```

对下载到的文件进行重命名

```text
cp 下载文件的文件名 dotnet.tar.gz
```

然后进行以下操作

```text
sudo apt-get install curl libunwind8 gettext
sudo mkdir -p /opt/dotnet
sudo tar zxf dotnet.tar.gz -C /opt/dotnet
sudo ln -s /opt/dotnet/dotnet /usr/local/bin
```

查看 .NET Core SDK 是否安装成功

```text
dotnet --info
```

## ASF 的下载与配置

先下载 ASF-generic

最新版本在这里查看：[Releases · JustArchiNET/ArchiSteamFarm (github.com)](https://link.zhihu.com/?target=https%3A//github.com/JustArchiNET/ArchiSteamFarm/releases)

```text
wget https://github.com/JustArchiNET/ArchiSteamFarm/releases/download/5.1.3.5/ASF-generic.zip
```

解压

```text
unzip 下载文件的文件名
```

**然后查看「[使用Docker在服务器上搭建ASF挂卡](https://zhuanlan.zhihu.com/p/399544075)」文章，从「创建挂卡用户配置文件」部分开始看到结尾，然后再看下面的内容**

**结尾上篇文章的内容，我们需要作出几个修改的点。**

-   **由于没有设置容器变量，ASF 的配置文件需要上传到容器**
-   **由于我们使用的是树莓派，ascf 我们需要下载 ARM V7 版本**
-   **建议使用 screen ，将 asf 和 ascf 两个程序分别运行在不同的 screen 里**

将 [ArchiSteamFarm.sh](https://link.zhihu.com/?target=http%3A//archisteamfarm.sh/) 设置为可执行文件

```text
chmod +x ArchiSteamFarm.sh
```

运行 ArchiSteamFarm.sh

```text
./ArchiSteamFarm.sh
```