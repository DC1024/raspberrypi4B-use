# VuePress 环境搭建
> 我们这里使用 Docker 快速搭建 VuePress 环境
> 可以修改左侧的 8080 端口

`docker run -it -p 8080:8080 node:latest`
# 安装 VuePress
创建用于存放 VuePress 的文件夹，并进入该文件夹
`mkdir vuepress-starter && cd vuepress-starter`
使用 yarn 安装 VuePress 为本地依赖
`yarn add -D vuepress@next`
# 运行 VuePress
更新软件源并安装 Vim 和 Screen
`apt update && apt install vim -y && apt install screen`
将 package.json 文件修改为如下内容
```
{
  "scripts": {
    "docs:dev": "vuepress dev docs",
    "docs:build": "vuepress build docs"
  }
}
```
将默认的临时目录和缓存目录添加到  .gitignore 文件中
```
echo 'node_modules' >> .gitignore
echo '.temp' >> .gitignore
echo '.cache' >> .gitignore
```
写入 Hello VuePress
```
mkdir docs
echo '# Hello VuePress' > docs/README.md
```
创建一个 Screen
`screen -S vue`
运行 VuePress
`yarn docs:dev`
访问网站
`你的IP地址:左侧端口号`
> 由于我对 yarn 不甚了解，所以采用 Screen 的方式在后台运行 VuePress 。
> 如果有人知道如何使 VuePress 后台运行的方法，请评论区留言或联系我。