---
title: vue2.0使用keep-alive实现页面缓存
date: 2020-02-16 15:49:56
tags:
---
[](#vue2.0使用keep-alive实现页面缓存)
#### 1. 所有页面都缓存
只需要在用到router-view的地方多加一个```<keep-alive></keep-alive>```标签即可
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200216154410233.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
#### 2. 缓存部分页面
（1）修改路由配置,需要缓存的（即切换页面后数据仍保留的）路由的keepAlive属性设置为true,不需要缓存的设置为false或者不设置（因为默认是false），如图：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200216154549264.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
（2）修改引用路由的地方![在这里插入图片描述](https://img-blog.csdnimg.cn/20200216154741669.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)