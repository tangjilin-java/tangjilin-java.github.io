---
title: Ubuntu使用NAT模式固定ip并联网
date: 2020-03-19 22:33:36
tags: ["Ubuntu","运维","ip"]
categories: Linux
---
# Ubuntu使用NAT模式固定ip并联网
## 1.打开虚拟机，左上角依次打开编辑–>虚拟网络编辑器，如图：
![](/images/Ubuntu/1.png)
## 2.点击更改设置，它会重新启动，选中VMnet8，可以设置自己的子网网段：，例如，我自己设置的是：192.168.112.0
![](/images/Ubuntu/2.png)
##然后在NAT设置中设置自己的网关ip：
![](/images/Ubuntu/3.png)
> 值得注意的是：你的本地网络配置里需要对VMnet8进行网络共享：
![](/images/Ubuntu/7.png)
## 3.打开虚拟机，输入命令：sudo vi /etc/network/interfaces：
![](/images/Ubuntu/4.png)
## 4.不放心的可以reboot一下就可以了：
![](/images/Ubuntu/5.png)
![](/images/Ubuntu/6.png)