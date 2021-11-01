66如果你刚刚在本地配置好你的 NextCloud ，准备通过域名访问，那么你有可能看到这个画面
![](http://image.dcchen.top/www/wwwroot/easyImages/image2021/09/09/vkmsfj.png)
这时候我们进入 NextCloud 容器，使用以下命令更新软件列表并安装 vim
`apt update`
`apt install vim`
> 如果你不是使用 Docker 方式安装的，可以跳过以上部分，直接找到 NextCloud 目录

进入 Config 文件夹，修改 config.php
`vim config.php`
找到 trusted_domains ，参考示例添加域名
>
'trusted_domains' =>
  array (
   0 => 'localhost',
   1 => 'server1.example.com',
   2 => '192.168.1.50',
   3 => '[fe80::1:50]',
),
***
#NextCloud #同步服务 
