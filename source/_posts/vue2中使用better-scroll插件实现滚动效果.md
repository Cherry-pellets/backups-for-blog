---
title: vue2中使用better-scroll插件实现滚动效果
date: 2020-02-10 17:01:28
tags:
---
[](#vue2中使用better-scroll实现滚动效果)
#### 1.npm安装插件
(1)[到github上查看最新版本号](https://github.com/ustbhuangyi/better-scroll)
(2)在package.json中添加依赖
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200210160243969.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
（3）执行```npm install```安装，安装成功后node_module目录下生成了better-scroll文件夹
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200210165755185.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
#### 2.使用插件
（1）在需要实现滚动效果的组件中引入插件
```import BScroll from 'better-scroll';```
（2）标记元素
使用ref属性来标记需要实现滚动效果的元素，然后在js中通过this.$refs获取该元素
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200210165606153.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
（3）绑定dom
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200210165643704.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)