---
title: 'webpack: 配置style-loader的insertAt出现的问题'
date: 2020-05-24 10:56:09
tags:
---
使用style-loader会默认将css文件里的样式拷贝到html文件里head标签的底部：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200524103342809.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
如果想要插入到head标签的顶部，应该使用insert,而不是insertAt,因为api改变了......
更新日志里说明了这一点：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20200524103815936.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzNjUwOTc5,size_16,color_FFFFFF,t_70)
正确的写法：
```javascript
module.exports = {
  module: { // 模块
    rules: [ 
    {
      test: /\.less$/,
      use:[
        {
          loader:'style-loader',
          options:{
           insert: function insertAtTop(element) {
             var parent = document.querySelector('head');
             // eslint-disable-next-line no-underscore-dangle
             var lastInsertedElement =
               window._lastElementInsertedByStyleLoader;

             if (!lastInsertedElement) {
               parent.insertBefore(element, parent.firstChild);
             } else if (lastInsertedElement.nextSibling) {
               parent.insertBefore(element, lastInsertedElement.nextSibling);
             } else {
               parent.appendChild(element);
             }

             // eslint-disable-next-line no-underscore-dangle
             window._lastElementInsertedByStyleLoader = element;
           },
          }
         },
         'css-loader',
         'postcss-loader',
         'less-loader',
      ]
    }
  ]
  }
}

 ```