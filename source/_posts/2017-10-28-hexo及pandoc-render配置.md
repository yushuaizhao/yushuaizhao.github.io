---
title: hexo及pandoc-render配置
date: 2017-10-28 18:46:31
tags:
    - hexo
---

# hexo安装及配置

## 安装

首先安装git和node.js，然后通过如下命令：

```
npm install hexo-cli -g
hexo init blog
cd blog
npm install
hexo server
```

## 修改配置

### _config.yml

网站的配置信息，site部分和URL部分自行配置，，writing部分略修改，其余默认。

writing部分中启用asset文件夹

# pandoc-render配置

首先安装pandoc

## 配置

先安装hexo-renderer-pandoc

```
npm install hexo-renderer-pandoc --save
```

配置参考[hexo-renderer-pandoc](https://github.com/wzpan/hexo-renderer-pandoc)

# Next主题配置

参考 [next使用文档](http://theme-next.iissnan.com/getting-started.html) 、[next wiki](https://github.com/iissnan/hexo-theme-next/wiki/)

另参考[如何让谷歌搜索到自己在GitHub上的博客](http://www.jianshu.com/p/df46bca5889d)

