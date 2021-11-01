之前写过一篇如何在 Docker 安装 Home Assistant 的教程，但是这个方法面对树莓派貌似并不适用，哪怕 Home Assistant 的 Docker 镜像支持 ARMVv7 架构。

于是在树莓派上利用 Docker 安装 Home Assistant ，我们需要一些其他方法。

## 使用 Docker 方法安装 HomeAssistant

可以修改以下代码：

-p 8123:8123 
>定义端口映射

-v /opt/homeassistant:/config \ 
> 修改代码中的 /opt/homeassistant ，定义 HomeAssistant 配置文件保存位置

```text
docker run -d \
  --name homeassistant \
  -p 8123:8123 \
  --privileged \
  --restart=unless-stopped \
  -e TZ=Asia/Shanghai \
  -v /opt/homeassistant:/config \
  --network=bridge \
  ghcr.io/home-assistant/raspberrypi4-homeassistant:stable
```

## 使用 Docker-Comper 方法安装 HomeAssistant

首先我们需要安装 Docker-Comper ，请参考「[树莓派安装 Docker-Compose](https://zhuanlan.zhihu.com/p/405062212)」

然后我们在主机上，在任意位置创建一个 homeassistant 文件夹，并在文件夹内创建一个 docker-compose.yml 文件。可参考以下代码

```text
mkdir homeassistant 
cd homeassistant
vim docker-compose.yml
```

然后将以下内容写入文件并保存退出。该代码可能随着 Home Assistant 的更新而更新，所以若出现问题时，请参考「[官网内容](https://link.zhihu.com/?target=https%3A//www.home-assistant.io/installation/raspberrypi)」中的 DOCKER COMPOSE 章节中的 Raspberry pi 4 部分

```text
version: '3'
services:
  homeassistant:
    container_name: homeassistant
    image: "ghcr.io/home-assistant/raspberrypi4-homeassistant:stable"
    volumes:
      - /PATH_TO_YOUR_CONFIG:/config
      - /etc/localtime:/etc/localtime:ro
    restart: unless-stopped
    privileged: true
    network_mode: host
```

然后我们使用以下命令创建容器。创建成功以后就可以通过「IP:8123」访问 Home Assistant

```text
docker-compose up -d
```
***
#HomeAssistant #Docker #DockerComper #树莓派