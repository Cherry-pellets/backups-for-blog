---
title: shell脚本参数超过9个时的处理
date: 2020-06-06 10:11:35
tags:
---
如果shell脚本中使用的参数不超过9个，用$1-$9即可。
当脚本程序的参数多于9个时，可以用shfit命令来使用序号大于9的参数。这个命令把命令行参数全体向左移一位。
```shell
#! /bin/bash
echo "前三个参数:$1 $2 $3"
shift
echo "前三个参数:$1 $2 $3"
shift
echo "前三个参数:$1 $2 $3"
```
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200606100930534.png)