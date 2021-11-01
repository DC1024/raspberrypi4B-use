# 前言
我[之前搭建 TTRSS](https://zhuanlan.zhihu.com/p/104680709) 时，还是基于网站源码方式搭建的，但是现在 TTRSS 已经不推荐使用网站源码搭建了，而是推荐使用 Docker 方式搭建。
![](http://image.dcchen.top/www/wwwroot/easyImages/image20212021/10/18/wctoqk.png)
但是官方提供的 Docker 镜像并不支持 ARM 架构，而树莓派恰好采用的就是 ARM 架构的处理器。
幸运的是有不少第三方的 TTRSS 镜像支持 ARM 可供我们使用。我们这次采用 [@Henry Wang](https://github.com/HenryQW)制作的 [Docker 镜像](https://ttrss.henry.wang/zh/)
![](http://image.dcchen.top/www/wwwroot/easyImages/image20212021/10/18/xh82uz.png)
# 搭建部分
#### 准备工作
想要通过 Docker 方式搭建 TTRSS，你首先需要安装 [Docker](https://shumeipai.nxez.com/2019/05/20/how-to-install-docker-on-your-raspberry-pi.html) 和 [Docker-Compose](https://zhuanlan.zhihu.com/p/405062212)
如果你没有安装 vim ，请使用以下指令安装
```
\\ 基于 apt 包管理器
apt update && apt install vim -y
```
#### 创建 docker-compose 文件
创建并进入一个用于保存文件的文件夹
```
mkdir ttrss && cd ttrss
```
使用以下命令创建并编辑 docker-compose 文件
```
vim docker-compose.yml
```
将该 [Github](https://github.com/HenryQW/Awesome-TTRSS/blob/main/docker-compose.yml) 链接中的内容复制粘贴进入 docker-compose 文件
#### 修改 docker-compose 文件
docker-compose 文件中必须修改的内容有：
> 不进行修改必定无法成功部署，请务必修改
```
\\ 修改 http://localhost:181/ 为部署成功后，准备访问 TTRSS 的网址
- SELF_URL_PATH=http://localhost:181/
```
docker-compose 文件中可以修改的内容有：
> 如果你不清楚这些内容的含义，可以不进行修改直接跳转到下一步
```
\\ 修改 181 以自定义 TTRSS 的访问端口
- 181:80

\\ 修改 ~ 以自定义数据库文件存放路径
- ~/postgres/data/:/var/lib/postgresql/data

\\ 修改 ttrss 以自定义数据库连接密码
- DB_PASS=ttrss

\\ 修改 ttrss 以自定义数据库密码
- POSTGRES_PASSWORD=ttrss

\\ DB_PASS 与 POSTGRES_PASSWORD 必须相同
```
#### 开始部署
使用以下命令开始部署，并等待部署完成
```
docker-compose up -d
```
当看到四个绿色的 `done` 时，表示部署成功
![](http://image.dcchen.top/www/wwwroot/easyImages/image20212021/10/18/yu36hc.png)
# 访问 TTRSS
在浏览器地址栏中，输入我们之前在 docker-compose 文件里修改的网址，回车访问。
使用账户：`admin` 密码：`password` 登录系统，并修改默认密码。
![](http://image.dcchen.top/www/wwwroot/easyImages/image20212021/10/18/yvwccc.png)