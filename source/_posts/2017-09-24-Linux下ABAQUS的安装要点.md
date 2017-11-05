---
layout: post
title:  Linux下ABAQUS的安装要点
date:  2017-09-24
tags: 
     - 软件相关
---


# 安装环境

Deepin 15 ABAQUS 6.14

可以事先安装好Intel的Fortran和C++编译器，便于二次开发。

需事先安装csh，因为ABAQUS用的是csh脚本。另外可能需要g++，libstdc++5。与版本有关。

# 安装要点

在sudo下进行

1. mount上iso文件,我新建了一个abaqus文件夹。注意：所有的执行操作不得在光盘的文件夹内，这在其它软件中也一样。
2.  ``` sudo csh abaqus/setup ```
3.  按照教程走，与Windows类似。注意第一步的路径为临时安装路径，可以随意，然后一路向下，直到安装licensed，选择只安装license server但是不启动。安装完license后，停止下面的操作，先破解。
4.  进入安装license的文件夹中的License，然后在此打开终端，修改破解的ABAQUS.lic文件，将this_host 改为本机的主机名，在Linux中可以通过终端来看，就是@后面的东西。将其复制到Lisence文件夹下，运行``` ./lmgrd -c ABAQUS.lic ```，这样就跑起来了。然后用``` ./lmstat -c yourhostname@127.0.0.1 ``` 查看服务器运行状态，记下端口号，一般为27011.
5.  现在继续ABAQUS的安装，服务器地址为   端口号@主机名 ，例子可以看界面上部的Example，然后一路向下，安装结束

# 注意事项

1.  之后的启动必须在License服务器启动之后，也就是先执行``` ./lmgrd ```，再执行``` ./abaqus cae ``` ，其中一个在服务器的License文件夹下，一个在ABAQUS安装目录的commander目录下。
2.  窗口透明是因为OpenGL的问题，解决方式为``` env XLIB_SKIP_ARGB_VISUALS=1 ./abaqus cae ```
3.  可能缺少共享库，直接安装就行。
4.  把Intel Fortran与ABAQUS连接需要修改PATH环境变量，将ifort加入环境变量即可我的在“/opt/intel/compilers_and_libraries_2017/linux/bin/intel64/”

# 脚本或者桌面配置文件

将启动过程用alias或者写成sh文件便于执行，也可以做成快捷方式
``` sh
sudo /opt/simulia/./lmgrd
sudo env XLIB_SKIP_ARGB_VISUALS=1 /opt/abaqus/Commander/abaqus cae
```
```desktop
[Desktop Entry]
Name=ABAQUS
GenericName=finite element
Type=Application
Exec=/home/shuaizhao/software/abaqus/abaqus.sh %U
TryExec=/home/shuaizhao/software/abaqus/abaqus.sh
Keywords=abaqus;
Icon=/home/shuaizhao/.icons/timg.jpeg
Categories=Emulator;System;Utility;
X-Deepin-CreatedBy=com.deepin.dde.daemon.Launcher
X-Deepin-AppID=abaqus
StartupNotify=false
Terminal=true
[Desktop Action Manager]
Exec=/home/shuaizhao/software/abaqus/abaqus.sh
Name=Open abaqus
```