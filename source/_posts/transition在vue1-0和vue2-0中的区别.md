---
title: transition在vue1.0和vue2.0中的区别
date: 2020-02-12 21:08:32
tags:
---
[](#transition在vue1.0和vue2.0中的区别)
### 1. html部分：
##### vue1.0
```html
<div class="shopcart-list" v-show="listShow" transition="fold">
	<!--more code-->
</div>
```
#### vue2.0
```html
 <transition name="fold">
      <div class="shopcart-list" v-show="listShow">
      	<!--more code-->
      </div>
 </transition>
```
### 2. css部分
#### vue1.0
```css
.shopcart-list
      position: absolute
      left: 0
      top: 0
      z-index: -1
      width: 100%
      &.fold-transition
        transition: all 0.5s
        transform: translate3d(0, -100%, 0)
      &.fold-enter, &.fold-leave
        transform: translate3d(0, 0, 0)
```
#### vue2.0
```css
.shopcart-list
      position absolute
      top: 0
      left: 0
      z-index -1
      width: 100%
      // transition all 0.5s
      transform translate3d(0, -100%, 0)

      &.fold-enter-active
      &.fold-leave-active
        transition all 0.5s
        // transform translate3d(0, -100%, 0)

      &.fold-enter
      &.fold-leave-to
        transform translate3d(0, 0, 0)
```