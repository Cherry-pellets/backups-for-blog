---
title: 'vue:使用vue-resource'
date: 2020-02-06 14:50:32
tags:
---
[](#vue:使用vue-resource)
#### 1. 在package.json中添加依赖
如图，后面的版本号根据自己喜欢的来写。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200206144039119.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
#### 2.安装
执行```npm install```安装，完成后node_modules目录下生成了vue-resource文件夹
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200206144321828.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
#### 3.导入插件并注册
将vue-resource导入到main.js中并全局注册
![在这里插入图片描述](https://img-blog.csdnimg.cn/2020020614442897.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
#### 4.发送请求
这里要提前准备好接收请求的接口或者mock数据
![](https://img-blog.csdnimg.cn/20200206144714186.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)