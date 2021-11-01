# 提要
提到自建引擎，大家可能会想到「Searx」，但「Searx」的 Docker 镜像无法在树莓派上使用。
而且我在查找「Searx」镜像的时候发现了一个有意思的项目：「Searxng」
# Searxng 是什么
大家看到「Searxng」的第一反应，可能会认为「Searxng」是打擦边球，蹭「Searxng」热度的一个玩意儿。但其实「Searxng」对类似问题有相似的回复。这里机翻一下，原文可看：[ What's the difference between searx and searxng?](https://github.com/searxng/searxng/issues/46)
> 首先 asciimoo 是 SearX 的作者。  第二个 dalf 是在 SearX 上长期维护大部分代码的开发人员。他想在 Searx 的核心中引入新的有趣功能，但 asciimoo 与 dalf 没有相同的愿景，因此 dalf 离开了 SearX 项目并开始了自己的分支。  与 SearX 不同，SearXNG 将在未来几个月内发生很大的变化，因为 dalf 可以自由地引入他想要的任何更改。也许@dalf 可以提供与原始 SearX 相比 SearXNG 将具有什么样的新功能。

# 如何通过 Docker 部署 Searxng
> 我们可以通过以下命令进行部署。部署过程中如果遇到疑问可以查看「Searxng」的文档：[Docker installation — Searx Documentation](https://searxng.github.io/searxng/admin/installation-docker.html#installation-docker)

创建一个存放「Searxng」文件的文件夹
`mkdir searxng`
进入文件夹
`cd searxng/`
拉取「Searxng」镜像
`docker pull searxng/searxng`
创建「Searxng」容器
>`${PORT}` 修改为想要映射的端口
 `${PWD}` 修改为之前创建的文件夹的路径
 `$PORT` 修改为 `${PORT}` 设置的端口

`
 docker run --rm \
            -d -p ${PORT}:8080 \
            -v "${PWD}/searx:/etc/searx" \
            -e "BASE_URL=http://localhost:$PORT/" \
            -e "INSTANCE_NAME=my-instance" \
            searxng/searxng
`
容器创建完成以后，我们通过 `IP:PORT` 访问「Searxng」