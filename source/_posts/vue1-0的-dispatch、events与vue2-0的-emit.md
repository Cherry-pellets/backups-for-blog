---
title: vue1.0的$dispatch、events与vue2.0的$emit
date: 2020-02-14 15:56:26
tags:
---
[](#vue1.0的&#36;dispatch、events与vue2.0的&#36;emit)
vue2.0弃用了vue1.0中的$dispatch,选择用&#36;emit向父组件传递数据，例子：
#### vue2.0
子组件：
```html
<div class="ratingselect">
    <span @click="select(2)">{{desc.all}}</span>
    <!-- more code-->
    <div @click="toggleContent">
    <!-- more code-->
    </div>
</div>
```
```javascript
methods: {
    select(type) {
        // more code
        this.$emit('ratingtype-select', type);
        // 向父组件传递,参数1为自定义的事件名称，参数2为传递的参数
    },
    toggleContent() {
        // more code
        this.$emit('content-toggle', this.onlyContent);
        // 向父组件传递,参数1为自定义的事件名称，参数2为传递的参数
    }
}
```
父组件：
```ratingtype-select```和```content-toggle```是子组件中定义的事件名称；
```html
<ratingselect @ratingtype-select="ratingtype_select" 
			@content-toggle="content_toggle"></ratingselect>
```
```ratingtype_select```和```content_toggle```是父组件自己在methods中定义的方法，参数是子组件传过来的
```javascript
methods: {
	ratingtype_select(type) {
	   // more code
	},
	content_toggle(onlyContent) {
	    // more code
	}
}
```
#### vue1.0
子组件：
```html
<div class="ratingselect">
    <span @click="select(2,$event)">{{desc.all}}</span>
    <!-- more code-->
    <div @click="toggleContent($event)">
    <!-- more code-->
    </div>
</div>
```
```javascript
methods: {
  select(type, event) {
      // more code 
      this.$dispatch('ratingtype.select', type);
      // 向父组件传递,参数1为自定义的事件名称，参数2为传递的参数
    },
    toggleContent(event) {
      // more code
      this.$dispatch('content.toggle', this.onlyContent);
      // 向父组件传递,参数1为自定义的事件名称，参数2为传递的参数
    }
  }
```
父组件：
```html
<ratingselect>
	<!-- more code-->
</ratingselect>
```
```javascript
events: {
   'ratingtype.select'(type) {
      // more code
    },
    'content.toggle'(onlyContent) {
      // more code
    }
  }
```
综上所述，
在vue1.0中，子组件使用的是&#36;dispatch,父组件在events中接收子组件传递过来的事件和参数；
在vue2.0中，子组件使用的是&#36;emit,父组件直接在标签中用v-on(语法糖为@)来接收子组件传递过来的事件和参数
