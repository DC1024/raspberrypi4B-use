# 什么是 RSSHUB
> RSSHub 是一个开源、简单易用、易于扩展的 RSS 生成器，可以给任何奇奇怪怪的内容生成 RSS 订阅源。RSSHub 借助于开源社区的力量快速发展中，目前已适配数百家网站的上千项内容——[介绍 | RSSHub](https://docs.rsshub.app/)

# 如何部署
>我们需要先安装 Docker Compose ，安装方法参考这篇文章


[[树莓派安装 Docker-Compose]]
进入主机终端：
安装 wget
`sudo apt-get install wget`
下载 RSSHUB 的 docker-compose 文件
`wget https://raw.githubusercontent.com/DIYgod/RSSHub/master/docker-compose.yml`
创建数据库卷
`docker volume create redis-data`
通过 docker-compose 文件启动
`docker-compose up -d`
然后访问`IP:1200`来检查 RSSHUB 是否部署成功