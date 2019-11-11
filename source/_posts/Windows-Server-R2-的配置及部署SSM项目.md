---
layout: pages
title: Windows Server R2 的配置及部署SSM项目
date: 2019-11-11 14:12:37
tags: ["Server","部署","SSM"]
categories: 服务器
---
# Windows Server R2 配置准备
**要想配置一个Windows Server R2，首先你得去购买一个Windows Server R2服务器**
> 学生购买链接：
[https://www.qcloud.com/act/campus](https://www.qcloud.com/act/campus "腾讯云学生优惠云主机")

**买好主机之后登录控制台**
<!-- more -->
{% asset_img 1.jpg This is an example image %}

**点击云主机进行相关操作：获取用户名和密码以便用本地远程连接到云主机**
{% asset_img 2.jpg This is an example image %}

**使用本地远程连接连接到云主机Windows Server R2**
{% asset_img 3.jpg This is an example image %}

**输入用户名和密码即可连接成功**
{% asset_img 4.jpg This is an example image %}
## 使用工具：
- 腾讯云主机windows 2012 r2标准版
- JDK 1.8
- Tomcat 9.0
- Mysql 5.5
- SQL yog
## 搭建环境前提：
- 会配置jdk环境变量(不会的点这里[https://www.jianshu.com/p/6f30ce3f92e9](https://www.jianshu.com/p/6f30ce3f92e9))
- 会配置tomcat环境变量(不会的点这里[https://www.cnblogs.com/badboys/p/7659029.html](https://www.cnblogs.com/badboys/p/7659029.html))
- 会安装与配置Mysql环境(不会的点这里[https://www.cnblogs.com/LXSHYZHX/p/7043902.html?utm_source=itdadao&utm_medium=referral](https://www.cnblogs.com/LXSHYZHX/p/7043902.html?utm_source=itdadao&utm_medium=referral))
- 已经能写java web项目（jsp或servlet）或SSM项目
- 对tomcat目录的作用有所了解、对xml文档的编写有所了解
- 会在腾讯云解析自己的域名（最好会，不会也没问题）
> 以上操作与在Windows 10 上配置基本一致

# 测试配置
- 远程连接到windows 2012 r2版本云主机！
- 假设你已经解析好自己的域名了！
- 假设你安装并配置好了jdk和tomcat的环境变量（在浏览器下输入localhost:8080 能看到猫！）
# 部署SSM
- 修改目录：C:\apache-tomcat-9.0.21\conf 下的server.xml ，将图中原来的8080改为现在的80（千万要找对！）如图：
{% asset_img 7.jpg This is an example image %}
- 把一个写好的java项目打成xxx.war包放到云主机里的tomcat目录下：C:\apache-tomcat-9.0.21\webapps，如图：
{% asset_img 5.jpg This is an example image %}
- 打开C:\apache-tomcat-9.0.21\bin目录点击startup.bat，如图：
{% asset_img 6.jpg This is an example image %}
- 打开浏览器输入你的主机ip加项目名(如果自己将自己的ip解析了的就用自己解析的网址查看),如图：
{% asset_img 8.jpg This is an example image %}
*到此为止Windows Server R2的配置与部署就说完了，有什么补充的可以在文章下方留言*
- 2019/11/11 15:29:03 






