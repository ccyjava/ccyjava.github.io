---
layout: post
title: 破解联通(北京)光猫，使用自己的路由器连接网络
description: 破解联通光猫，只使用其桥接功能
category: blog
---
>联通北京宽带的光猫自带路由，无线功能，能满足一般的使用。但对于高级用户，其限制又太多，比如想做个端口映射，自定义DNS服务器都不方便。本文参考网络上的资料，将联通光猫的路由功能关闭，开启桥接功能，使其仅仅作为一个调制解调器使用，然后外接一个小米路由拨号上网。

##获得管理员账号 
  
1. 访问 http://192.168.1.1/logoffaccount.html，隐藏用户改为启用，启用工程账号 
2. 登录 http://192.168.1.1 工程帐号用户名：fiberhomehg2x0 密码：hg2x0 
3. 开启 CUAdmin 账号：进服务设置，找到维护帐号开关，选开启后保存，这样就可以用管理员登录了 
4. 访问 http://192.168.1.1/backupsettings.html 下载 backupsettings.conf 
5. 在 backupsettings.conf 里找 AdminPassword  
我这台上是 <AdminPassword>MTIzcXdlYXNkenhjAA==</AdminPassword>  
base64解码拿到密码 123qweasdzxc 看这密码的长相估计这批设备上的都一样 
6. 重启路由器
7. 登录 http://192.168.1.1/cu.html，管理员用户名：CUAdmin, 密码：123qweasdzxc（注意网址和大小写） 
  
以上成功登录以管理员身份进入到联通光猫 
  
##修改桥接模式 
  
8. 进入宽带设置-> Internet 连接，记下 2_Internet_xxx 链接中的Vlan id， 
北京联通是3691，**删除2_Internet_xxx 链接**，重启光猫 
9. 重复步奏 6和7，以管理员登录，在宽带设置中新增 Wan 链接，模式选择桥接， 
选中Vlan，将Vlan ID 设置成之前记录下的Vlan ID，服务模式选Internet 
10. 我是直接重新将端口设置在了端口2，所以直接绑定端口2，您可以选择绑定端口1，保存并重启光猫 
11. 将路由器接在端口2，设置PPPOE，上网拨号成功 
  
##常用用户名密码记录 
  
普通用户：  user，盒子背面的密码 

工程账号：  fiberhomehg2x0，hg2x0 

管理员账号：CUAdmin，123qweasdzxc 


[newsmth][]:	水木上的原文

[newsmth]:	http://download.newsmth.net/nForum/#!article/Networking/69721?p=1 "水木上的帖子"