# vue-long-ripple

> 仿知乎、掘金点击动画效果插件, 支持所有 block 标签(或将 display 设为 block )，响应式wapper大小，可自定义波纹，开箱即用。 ***支持移动端长按特效***

## 介绍

### 前言

> 看到知乎和掘金上的tabbar有低调奢华的波纹特效，忍不住自己也想用，但是市面上好像没有什么不错的类似特效和完整的封装（发布包的时候才发现都是几年前的东西），所以自己花了一周的时间做了一个。大小约80k。

### 特色

1. 自适应外层包装，只需要把插件放到需要的盒子中即可，自适应外层容器大小，无需其他操作，完全黑盒，开箱即用。
2. 可定制波纹的颜色，控制波纹时间。
3. 支持媒体查询，pc和移动端皆可使用
4. 移动端支持长按特效！（花了不少时间）长按时间默认为 500ms 
5. 无第三方依赖

## 安装

``` 

## 下载安装包

npm install vue-long-ripple

# 在vue中引用
import Vue from 'vue'
import App from './App.vue'
import VueRipple from './lib/index.js'

Vue.use(VueRipple)

# 在组件中引用
<template>
  <div>
    <div class="btn">
      <vue-ripple></vue-ripple>
    </div>
  </div>
</template>
<style>
.btn {
  width: 30%;
  height: 300px;
  background: #eeeeee;
  margin: 0 auto;
}
</style>
```

## 效果展示

> PC直接使用

![PC直接使用](https://github.com/ctts/vue-long-ripple/raw/master/static/img/1.gif)

> 移动端直接使用和长按特效

![移动端直接使用](https://github.com/ctts/vue-long-ripple/raw/master/static/img/2.gif)

> 自定义颜色

![自定义颜色](https://github.com/ctts/vue-long-ripple/raw/master/static/img/3.gif)

> 自定义时间

![自定义颜色](https://github.com/ctts/vue-long-ripple/raw/master/static/img/4.gif)

> 综合

![综合](https://github.com/ctts/vue-long-ripple/raw/master/static/img/5.gif)

## API

用户可定制化波纹时间和颜色，用props传入对应参数即可

### 颜色

默认为 rgba(0, 0, 0, 0.25) 建议使用 rgba 字符串形式。

``` 
<vue-ripple :backgroundColor:"'rgba(10,20,120,0.3)'"></vue-ripple>
```

### ripple时间

默认为 0.6s 为保证效果，请不要超出2s（当然你觉得时间长好看我也无所谓啦），请使用 Number 类型。

移动端长按时间默认为 0.5s ，当用户设定了enterTime，则改为 enterTime-0.1s，

``` 
<vue-ripple :enterTime="1"></vue-ripple>
```

### 绝对定位

因为插件使用的是block，所以肯定会占用空间，如遇到偏移的情况，请确定外层wapper的padding或margin，或在外层添加一层 div 使用绝对定位即可。
```
.warpper{
  position: absolute;
  left: 0px;
  top: 0px;
  width: inherit;
  height: inherit;
}
```

### 最后

终于完成了…… 这一周也遇到不少问题，也学到不少东西，希望这个插件可以帮到大家。