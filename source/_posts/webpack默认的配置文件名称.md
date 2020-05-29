---
title: webpack默认的配置文件名称
date: 2020-05-24 10:24:17
tags:
---
Webpack的配置文件名称默认使用webpack.confid.js或webpackfile.js：
可在node_modules/webpack-cli/bin/config/config-yarn.js中查看
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200524102117145.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
如果想要修改配置文件的名称，可执行命令：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200524102229178.png)
也可以在package.json的scripts里添加：
```"build": "webpack --config webpack.config.js",```
其中 webpack.config.js可以替换为自己想要的名称![在这里插入图片描述](https://img-blog.csdnimg.cn/20200524102804697.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
