---
title: 前端面试题：正则表达式以及replace的使用
date: 2020-04-21 21:21:00
tags:
---
题目：
```javascript
function template(tmpl, data) {
    // your code
}
template('我的名字是{{name}}，我的工作是{{work}}，我喜欢{{work}}', {
   name: '小周',
   work: '编程'
 });
  // 函数的返回是 '我的名字是小周，我的工作是编程，我喜欢编程'
```
##### 解法1：使用正则表达式以及replace
```javascript
function template(tmpl,data){
    let str = tmpl.replace(/\{\{([^\}]+)\}\}/g,function(){
      return data[arguments[1]];
    });
    console.log(str);
}

template('我的名字是{{name}}，我的工作是{{work}}，我喜欢{{work}}', {
   name: '小周',
   work: '编程'
 });
  ```
  replace方法第二个参数为替换函数，这个函数可以接受多个参数。其中，第一个参数是捕捉到的内容，第二个参数是捕捉到的组匹配（有多少个组匹配，就有多少个对应的参数）。此外，最后还可以添加两个参数，倒数第二个参数是捕捉到的内容在整个字符串中的位置（比如从第五个位置开始），最后一个参数是原字符串。
  参考：https://wangdoc.com/javascript/stdlib/regexp.html#stringprototypereplace
  ##### 解法2：直接粗暴
  ```javascript
  function template (tmpl, data) {
    // your code
    let arr = tmpl.split('}}')
    arr.splice(arr.length - 1, 1)
    // console.log(arr)
    let ans = []
    let left, right
    for (key in arr) {
      left = arr[key].split('{{')[0]
      right = arr[key].split('{{')[1]
      for (prop in data) {
        if (right === prop) {
          right = data[prop]
          break
        }
      }
      ans.push(left + right)
    }
    ans = ans.join('')
    console.log(ans)
    return ans
  }
  template('我的名字是{{name}}，我的工作是{{work}}，我喜欢{{work}}', {
    name: '小周',
    work: '编程'
  });
```