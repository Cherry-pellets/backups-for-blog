---
title: 'vue2:安装、配置、使用前端路由vue-router'
date: 2020-02-05 18:40:24
tags:
---
[](vue2:安装、配置、使用前端路由vue-router)
#### 1.查看是否已安装vue-router
首先查看package.json文件中是否已经添加了vue-router依赖：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200205175021886.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
再查看node_modules文件夹下是否有vue-router文件夹
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200205181828319.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
如果有以上文件，则说明已经安装了vue-router。
一般在搭建项目时会出现是否安装vue-router这一个选项：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200205180054478.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
如果选了yes，项目搭建时就会安装vue-router。
如果package.json中没有这句代码或者没有vue-router文件夹，则自己在packsge.json中添加一句代码：
```
"vue-router": "^3.0.1"
```
(后面的"^3.0.1"为版本号，可以自己去官网或者github上查看最新稳定版的版本号)，添加完以后执行 
```
npm install
```
再去查看node_modules文件夹下是否有vue-router文件夹，如果有，则完成安装。
#### 2.添加组件
添加所需的组件
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200205180626552.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
#### 3.修改index.js
首先导入上面创建的组件：
```
import goods from '../components/goods/goods';
import seller from '../components/seller/seller';
import ratings from '../components/ratings/ratings';
```
然后配置导入的组件作为路由：{第一个{}及其内容不是必需的，只是为了设置一个默认显示的路由}
```
export default new Router({
  routes: [
    {
      path: '/',
      name: 'goods',
      component: goods
    },
    {
      path: '/goods',
      name: 'goods',
      component: goods
    },
    {
      path: '/seller',
      name: 'seller',
      component: seller
    },
    {
      path: '/ratings',
      name: 'ratings',
      component: ratings
    }
  ]
});
```
如图：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200205181316966.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
#### 4.使用路由
首先在main.js中引入刚才配置好的路由
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200205182609344.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
然后在app.vue中添加路由，这里的router-link标签中to属性的值要与index.js中path的值对应
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200205182747991.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
#### 5.效果
点击商品：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200205183201929.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
点击评论
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200205183218229.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)