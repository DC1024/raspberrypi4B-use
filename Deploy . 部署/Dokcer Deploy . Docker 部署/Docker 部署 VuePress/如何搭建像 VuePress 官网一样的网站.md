# 开篇
首先，[VuePress](https://v2.vuepress.vuejs.org/zh/) 这个网站是在 [Github](https://github.com/vuepress/vuepress-next) 上开源的，我们可以直接查看它的首页源代码。
![](http://image.dcchen.top/www/wwwroot/easyImages/image20212021/10/18/brkwly.png)
# 首页
这个首页可以分为两个区域，首页区和代码区，我这里去除代码区，只保留首页区，并将里面的描述改为注释。
你可以使用并修改以下文件，将文件内容替换 VuePress 中的 `README.md` 文件
```
---
home: true
title: <该页面的标题>
heroImage: <主页LOGO文件地址>
actions:
  - text: <主按键中的文本介绍>
    link: <要跳转到的链接>
    type: primary
  - text: <次要按键中的文本介绍>
    link: <要跳转到的链接>
    type: secondary
features:
  - title: <特色功能标题1>
    details: <特色功能具体介绍1>
  - title: <特色功能标题2>
    details: <特色功能具体介绍1>
  - title: <特色功能标题3>
    details: <特色功能具体介绍1>
  - title: <特色功能标题4>
    details: <特色功能具体介绍1>
  - title: <特色功能标题5>
    details: <特色功能具体介绍1>
  - title: <特色功能标题6>
    details: <特色功能具体介绍1>
footer: 页脚
---
```
# 单个导航与导航组
```
    navbar: [
      // 单个导航栏
    {
        text: '导航栏显示名称',
        link: '跳转链接',
    },

       // 单个导航组
    {
        text: '导航组显示名称',
        children: ['链接1', '链接2'],
    },
    ],
```
# 侧栏
```
	// 两种侧栏二选一，根据个人需求选择
	// md 文件标题将显示为侧栏显示标题

	// 全页面显示同一个侧栏
    sidebar: [
      // 侧栏
      // 字符串 - 页面文件路径
      '页面文件路径1',
      '页面文件路径2',
    ],
	
	// 不同子路径下的页面会使用不同的侧边栏
    sidebar: {
      '指定子路径使用以下代码定义的侧边栏': [
        {
          text: '自定义该侧栏的标题',
          children: ['页面文件路径1', '页面文件路径2','页面文件路径3'],
        },
      ],
    },
```
# 个人修改后效果
![](http://image.dcchen.top/www/wwwroot/easyImages/image20212021/10/19/fd5ynp.png)
