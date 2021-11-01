在安装 Docker-Compose 的时候，可能会提示如下报错。这是因为 Docker-Compose 需要版本大于 3.5 的 python ，然而树莓派预装的 python 版本为 2.7 ，所以我们需要对 python 进行升级。

```text
pyrsistent requires Python '>=3.5' but the running Python is 2.7.16
```

安装 python3

```text
sudo apt install python3
```

自动清理 python2.7 的依赖

```text
sudo apt autoremove
```

删除掉 python2.7 的软链接

```text
sudo rm /usr/bin/python
```

创建一个新的软链接指向刚刚安装的 python3，代码中的 3.7 根据 python 版本变化而变化

```text
sudo ln -s /usr/bin/python3.7 /usr/bin/python
```

检查当前 python 版本

```text
python -V
```