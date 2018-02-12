---
layout: post
title: virtualbox摄像头 
subtitle: 虚拟机中如何使用集成摄像头 
date: 2018-02-10
tags: 
    -虚拟机  
---

# virtualbox

virtualbox的使用体验感觉还不错，但使用时有一些地方需要注意。

在virtualbox 5.2.2和deepin15.5上测试通过。

1. 使用时注意选择正确的网卡，网络设置要正确
1. 管理员运行和普通运行时虚拟机列表是不同的
1. 扩展安装包要安装正确的版本
1. 虚拟机还有一个OSE版本，不要安装串了，出现问题的话卸载重装一般即可解决。

# 使用集成摄像头

在安装虚拟机后注意是找不到摄像头的，需要下载扩展包[Oracle VM VirtualBox Extension Pack](https://www.virtualbox.org/wiki/Downloads)

然后在 ```管理->全局设定->扩展``` 中添加扩展包，添加完成后注意打开```设置->USB设备```，启动USB2.0即可。

![深度录屏_VirtualBox Manager_20180212115410](https://i.loli.net/2018/02/12/5a8110bc642c0.gif)

打开虚拟机，在```设备->摄像头```中点击打开摄像头，等待系统安装驱动后即可使用。

# 虚拟机下载

在实际使用中，自行安装的虚拟机因为优化不是很好会占用过多的资源，导致机器比较卡。

win7\win8\win10虚拟机微软有着专门用于测试IE的虚拟机可供使用，感觉比较流畅。下载地址为：[https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/]()


