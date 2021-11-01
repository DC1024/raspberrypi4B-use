## Wallabag是什么？
Wallabag 是一个可以让用户自行搭建的网页，Wallabag 可以用于收藏文章，也就是“稍后阅读”。而且 Wallabag 可以将收藏的文章通过 RSS 发布，这样我就可以通过我的 RSS 系统来同步获取，堪称利器。
## 怎么使用 Docker 安装 Wallabag
由于 Wallabag 官方并没有推出 ARM 架构的 Docker 镜像，我们需要使用第三方构建的 Wallabag 镜像，如 [ugeek/wallabag](https://hub.docker.com/r/ugeek/wallabag) 。

我们在终端使用以下命令来创建容器，其中可以修改的代码有：
`-p 90:80`
> 修改端口映射


`http://192.168.0.1:90`
>将 IP 地址改为服务器 IP 地址。端口号与端口映射端口号对应


完整代码如下：
`
docker run --name wallabag  -p 90:80 -v $HOME/docker/wallabag/data:/var/www/wallabag/data -v $HOME/docker/wallabag/images:/var/www/wallabag/web/assets/images -e SYMFONY__ENV__DOMAIN_NAME=http://192.168.1.100:90 ugeek/wallabag:arm
`
## 创建容器中可能出现的问题
使用 Docker 创建 Wallabag 容器，可能会出现如下警告：
![](http://image.dcchen.top/www/wwwroot/easyImages/image2021/09/11/phpu7b.png)
使用==第三方镜像 + arm 主机==或使用==官方镜像 + amd64 主机==，均会出现该警告，原因未知。但 Wallabag 服务正常。
## 访问 Wallabag 并登录
容器搭建完成以后，访问`IP:你设置的 端口号`以进入 Wallabag。
用户注册服务此时不可用，使用默认用户名密码登录
> 用户名：wallabag / 密码：wallabag
***
[[如何在浏览器上使用 Wallabag]]
#Docker #Walllabag #树莓派 #RSS