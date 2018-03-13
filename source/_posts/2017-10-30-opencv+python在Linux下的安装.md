---
title: opencv+python在Linux下的安装
date: 2017-10-30
tag:
    - deep learning
    - linux
    - python
---

# 安装前准备

linux下opencv用源码安装，要求有编译环境，安装时可以根据报错查看

一般有gcc、g++、cmake、pkg-config

# 安装

首先下载源码，建议git

```sh
git clone https://github.com/opencv/opencv.git
git clone https://github.com/opencv/opencv_contrib.git
```

然后在opencv文件夹下新建build文件夹，进入build文件夹，执行下面的语句。这里要注意使用的是python3的3.5版本，版本号要对上，另外还有numpy的安装位置PYTHON3_NUMPY_INCLUDE_DIRS，通过`pip3 show numpy`显示。

```sh
cmake -D CMAKE_BUILD_TYPE=Release \
-D OPENCV_EXTRA_MODULES_PATH=<opencv-contrib-directory>/modules \  \\可选安装opencv-contrib
-D CMAKE_INSTALL_PREFIX=/usr/local  \  
PYTHON3_EXECUTABLE=/usr/bin/python3 \  
PYTHON_INCLUDE_DIR=/usr/include/python3.5 \  
PYTHON_LIBRARY=/usr/lib/x86_64-linux-gnu/libpython3.5m.so \  
PYTHON3_NUMPY_INCLUDE_DIRS=/home/shuaizhao/.local/lib/python3.5/site-packages/numpy/core/include ..
```

若有问题，去掉D后面的空格

最后`make`和`sudo make install`即可。注意make可以使用例如`make -j7`采用多个进程。