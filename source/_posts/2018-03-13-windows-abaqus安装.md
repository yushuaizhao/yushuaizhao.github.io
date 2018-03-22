---
layout: post
title: windows abaqus安装 
subtitle:  
date: 2018-03-12
catalog: true
tags: 
    - 软件相关

--

# 安装准备

本应该先安装documentation的，有的话就先装，没有拉倒

# 安装license server

先一路next，选择的时候选择第一项license server，弹出license server。

自动生成本机计算机名，拷贝下来保存，然后next

选择第二项只安装不运行，即just install the license utilities。

更改安装位置，等待完成，done以后即可。

# 修改license文件

继续安装product，进入选择server

换SolidSQUAD中的license，其中将ABAQUS.lic中的this_host换成应该的计算机名，然后后面的ID记住，然后将LICENSE复制到License server安装目录。

运行安装包\SIMULIA\License中的lmtools.exe，在 "Config Services"页选择三个文件"lmgrd.exe", "ABAQUS.lic" 和"ABAQUS.log"，勾选 "Use Service" 和 "Start Server at Power Up", 点击 "Save Service"保存，

切换至 "Start/Stop/ReRead"页点击"Start Server"，提示Server Start Successful.如果提示失败，需要重新操作直到成功（在 "Config Services"页，点击remove service ，重新加载三个文件），关闭窗口进行下一步。

添加系统环境变量：右键计算机-属性-高级-环境变量-新建，设置环境变量，变量值为 27011@，这个地方27011和27500别搞错，看自己许可证文件的里面是多少

# 安装ABAQUS

输入License Server 与环境变量相同

提示输入在线帮助文档，没有可以不填，点击next，弹出警告窗口，点击continue 

选择安装目录，默认是C:\SIMULIA\Abaqus，可以根据自己需要设置，这里 D:\SIMULIA\Abaqus，next。弹出创建窗口，点击yes

设置工作目录，默认C:\Temp，可以根据自己需要设置，这里设置成 D:\SIMULIA\Temp，点击next，同样弹出创建窗口点击yes

点击安装Install, 审核点击next,安装完成，点击done ，完成安装
