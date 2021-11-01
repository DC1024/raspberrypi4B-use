前置工作

> apt update  
> apt-get install sudo

运行 Docker 安装脚本

> sudo curl -sSL [https://get.docker.com](https://link.zhihu.com/?target=https%3A//get.docker.com) | sh

部署 Portainer

> docker pull portainer/portainer  
> docker volume create portainer_data  
> docker run -d -p 9000:9000 --name portainer --restart always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer

最后访问 IP:9000 即可