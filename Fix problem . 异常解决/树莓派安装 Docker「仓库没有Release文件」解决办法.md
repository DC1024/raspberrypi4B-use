这个问题是我在「Ubuntu 安装 Docker 并运行 CentOS」中，执行「添加软件仓库」操作后的「更新 apt 包索引」中出现的。  

我们先 cd 进入以下目录

> cd /etc/apt/sources.list.d

使用 ls 查看该目录，看看有没有 docker.list

> ls

![](https://pic4.zhimg.com/80/v2-930d79b25aa7022b74e08107311a9e2f_720w.jpg)

对 docker.list 进行更名

> sudo mv docker.list docker.list.bak

此时再尝试，更新成功

```text
sudo apt-get update
```

![](https://pic3.zhimg.com/80/v2-6d6ab71d838bf858bdc879fed8c8d44a_720w.jpg)