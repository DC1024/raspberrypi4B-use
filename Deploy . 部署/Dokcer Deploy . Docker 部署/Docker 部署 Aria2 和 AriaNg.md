> 我们这次使用 Docker 部署，请先安装 Docker

# 在命令行中输入以下命令，部署 Aria2
#### 需要修改的值
* $UID | 请将值修改为用户及用户组编号，如 1000 等
* TOKEN | 自定义密码
* $PWD | 请将值修改为对应的文件存放路径
#### 可以修改的值
* 端口映射
```
docker run -d \
  --name aria2-pro \
  --restart unless-stopped \
  --log-opt max-size=1m \
  -e PUID=$UID \
  -e PGID=$GID \
  -e UMASK_SET=022 \
  -e RPC_SECRET=<TOKEN> \
  -e RPC_PORT=6800 \
  -p 6800:6800 \
  -e LISTEN_PORT=6888 \
  -p 6888:6888 \
  -p 6888:6888/udp \
  -v $PWD/aria2-config:/config \
  -v $PWD/aria2-downloads:/downloads \
  p3terx/aria2-pro
```
# 在命令行中输入以下命令，部署 AriaNG
#### 可以修改的值
* 端口映射
```
docker run -d \
  --name ariang \
  --log-opt max-size=1m \
  --restart unless-stopped \
  -p 6880:6880 \
  p3terx/ariang
```