![](http://image.dcchen.top/www/wwwroot/easyImages/image20212021/10/20/jq15o.png)
# 开篇
我首先必须得说，是 [Vue](https://v3.cn.vuejs.org/) 的官网，让我萌生了使用这种风格来搭建一个服务网站或者产品类网站，所以我顺藤摸瓜找到了 [VuePress](https://v2.vuepress.vuejs.org/zh/)。
怎么[部署 VuePress](https://sspai.com/post/69404) 和[编写网页](https://sspai.com/post/69405)都可以点击进入相关文章查看。 这里主要和大家分享我使用 VuePress 一段时间以后的感受。

# 易部署
VuePress 有很多种部署方式，且部署简单~~(对我而言)~~。我认为最方便的是使用 Docker 部署 VuePress，但如果没有一定的 Docker 使用基础，上手还是有一定难度。但大体依旧很简单，拉取创建 node 镜像容器，然后按照快速上手文档照输一遍指令就好。
# 易上手
不同于以往使用 HTML、CSS、JavaScript 来编写网页，VuePress 使用 Markdown 语言来编写网页。
如果你不知道什么是 Markdown ，你可以访问 [Markdown](https://daringfireball.net/projects/markdown/) 的官网看看。
简单来说， Markdown 就是通过一些简单的语法来实现通用的样式。
得益于 Markdown 语言的简单易用，使用 Markdown 编写网页比使用传统方式要简单得多，所以 VuePress 很适合新手使用。
# 实时更新
在启动 VuePress 站点以后，你可以直接修改网页文件，然后在 VuePress 站点中实时看到修改所产生的变化。
当然了，如果你的网页修改出错，VuePress 会出错停止，这时候将错误部分修改，再重启 VuePress 即可。
# 文档详细
作为第一次接触 VuePress 的小白，我这次搭建网站参考了 VuePress 官网的[帮助文档](https://v2.vuepress.vuejs.org/zh/guide/#%E5%AE%83%E6%98%AF%E5%A6%82%E4%BD%95%E5%B7%A5%E4%BD%9C%E7%9A%84)和 [Github 仓库](https://github.com/vuepress/vuepress-next)，基本没有使用过搜索引擎来解决问题~~(就算搜了也不如官方文档好用)~~。
个人认为官方文档的优秀程度很大程度决定着新用户的使用体验，所以 VuePress 的文档值得点赞。