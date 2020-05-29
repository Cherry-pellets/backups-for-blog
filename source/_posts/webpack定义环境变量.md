---
title: webpack定义环境变量
date: 2020-05-25 15:57:51
tags:
---
###### 方法1：直接配置
（1）在webpack配置文件中使用webpack自带的DefinePlugin插件
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200525152551162.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
（2）在其他文件中使用变量
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200525152648951.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
（3）效果：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200525152659704.png)
###### 2.方法2：在不同的环境中定义不同的变量
(1)```npm install webpack-merge```
(2)项目目录下新建webpack.base.js, webpack.prod.js, webpack.dev.js文件
其中webpack.prod.js用于生产环境，webpack.dev.js用于开发环境，webpack.base.js同时用于开发环境和生产环境
```javascript
// webpack.prod.js
let {smart} = require('webpack-merge')
let base = require('./webpack.base.js')

module.exports = smart(base, {
    mode: 'production'
})
```
```javascript
// webpack.dev.js
let {smart} = require('webpack-merge')
let base = require('./webpack.base.js')

module.exports = smart(base, {
    mode: 'development'
})
```
(3)分别在开发环境和生产环境中打包:```npm run build --  --config webpack.dev.js```
```npm run build --  --config webpack.prod.js```
也可以在package.json中修改命令：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200525160100672.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
(4)然后可以在不同的环境下根据方法1定制不同的变量