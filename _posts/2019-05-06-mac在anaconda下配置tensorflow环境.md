---
layout:     post
title:      mac在anaconda下配置tensorflow环境
subtitle:   Mac配置tensorflow环境
date:       2019-05-06
author:     buzhenyu
header-img: img/post-bg-re-vs-ng2.jpg
catalog: true
tags:
    - 环境配置
---

首先，Anaconda在官网可以下载。
这里是Anaconda的官网。
[https://www.anaconda.com/distribution/#download-section](https://www.anaconda.com/distribution/#download-section)

点左下角的下载那个Python3.7版本的就好啦！
下好之后一路傻瓜式安装就好！（相信大家没问题的）。

安装好anaconda之后就来配置anaconda环境。

首先输入两行代码：

```bash
conda config --add channels http://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/free/
```

```bash
conda config --set show_channel_urls yes
```
然后，在终端输入如下命令

```bash
conda config --show-sources
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200211214915610.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZvbW9v,size_16,color_FFFFFF,t_70)
上图中指向的这个就是文件的地址，再通过vim修改。
在我这就应该这样写，你们对应的自己改自己的地址就行。

```bash
vim /User/buzhenyu/.condarc
```
如果不会用vim的话，就按照上面的输入。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200211215200982.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZvbW9v,size_16,color_FFFFFF,t_70)
 应该会出现以上页面，然后按键盘上的i键进行编辑（这里注意编辑状态下只能使用键盘移动光标，然后把 - Defacult那一行删除了。）
 删除完按Esc ，在输入冒号： ，再输入wq，按回车就退出了。
接着激活tensorflow环境。

使用`conda create -n tensorflow pip python-3.7`

貌似清华的镜像挂了。。。。

所以这里用

```bash
pip install tensorflow -i https://pypi.douban.com/simple
```
就可以了。

最后测试一下，可以在jupyter book中输入

```python
import tensorflow as tf
tf.__version__
```

来测试，测试结果如下。

![在这里插入图片描述](https://img-blog.csdnimg.cn/2020021121582513.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2ZvbW9v,size_16,color_FFFFFF,t_70)