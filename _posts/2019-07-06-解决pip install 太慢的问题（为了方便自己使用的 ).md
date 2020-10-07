---
layout:     post
title:      快速搭建个人博客
subtitle:   pip install 替换源 （为了让pip的速度更快）
date:       2019-07-06
author:     buzhenyu
header-img: img/post-bg-re-vs-ng2.jpg
catalog: true
tags:
    - Blog
---

pip install 替换源

本来一般都是直接`pip install numpy` 
但是有的时候真的超级慢，所以可以有如下的替换

```bash
pip install -i https://pypi.tuna.tsinghua.edu.cn/simple numpy
```

几个常用的源

```bash
清华：https://pypi.tuna.tsinghua.edu.cn/simple
阿里云：http://mirrors.aliyun.com/pypi/simple/
中国科技大学 https://pypi.mirrors.ustc.edu.cn/simple/
华中理工大学：http://pypi.hustunique.com/
山东理工大学：http://pypi.sdutlinux.org/
豆瓣：http://pypi.douban.com/simple/
```
一劳永逸的方法，一下子直接改掉源（以豆瓣为例）

```bash
pip config set global.index-url http://pypi.douban.com/simple/
```

