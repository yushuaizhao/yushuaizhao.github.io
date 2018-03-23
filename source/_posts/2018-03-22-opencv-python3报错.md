---
layout: post
title: opencv-python3报错 
subtitle: opencv 在python3下莫名其妙的报错 
date: 2018-03-22
catalog: true
tags: 
    - python 
    - opencv
---
# 不懂为什么的bug

## 报错内容

```(error)
ImportError: numpy.core.multiarray failed to import
Traceback (most recent call last):
  File ".\cvsift.py", line 1, in <module>
    import cv2
ImportError: numpy.core.multiarray failed to import
```

查找官方issue，找到解决方案：在这之前就导入numpy.core.multiarray

```(python)
import numpy.core.multiarray
```

导入后继续报错，并没有解决问题

## 解决方案

换个目录，我也不知道为什么。