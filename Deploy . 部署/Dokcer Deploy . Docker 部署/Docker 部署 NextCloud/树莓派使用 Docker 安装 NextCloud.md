## 部署 NextCloud
先 pull 镜像
`docker pull nextcloud`
在终端运行以下命令
`docker run -d -p 8080:80 nextcloud`
> 如果你运行此命令以后无法打开 NextCloud ，请 pull 带有 `apache` tag 的镜像

访问 NextCloud
 [http://localhost:8080/](http://localhost:8080/) 
 ![](http://image.dcchen.top/www/wwwroot/easyImages/image2021/09/09/trs957.png)
 
 ## 配置 NextCloud
 用户名/密码自己填写就好了。展开==存储与数据库==，选择对应的数据库类型，并输入数据库信息，点击==安装完成==。
 > 要注意的是，如果你的数据库不在 NextCloud 容器内，数据库地址就不能使用 localhost 了
 > 由于这里我多次连接数据库无法连接。所以我这里直接选择 SQLite 了

<img src="http://image.dcchen.top/www/wwwroot/easyImages/image2021/09/09/u60w6k.png" />

***
[[设置 NextCloud 可以通过其它域名访问]]
#同步服务 #树莓派 #ARM #Docker #NextCloud