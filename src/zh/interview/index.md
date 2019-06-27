---
title: 面试必备知识点
sidebar: auto
sidebarDepth: 2
---
# 面试必备知识点

## CSS
- 盒模型
- CSS的单位和应用场景及Rem的设置
- 定位，回流与重绘
- IFC、BFC与清除浮动
- 兼容处理

## 原生JS  
- 变量提升配合作用域链
- 原型链
- 继承
- 闭包
  - 变量的作用域 分两种全局变量和局部变量
      js语言的特别之处是函数内可以直接读取全局变量 但是在函数外部无法访问函数内部的局部变量 注意：在函数内部一定要用var
  - 闭包的概念:就是能够读取其他函数内部变量的函数 本质上闭包是将函数内部和函数外部连起来的桥梁
  - 闭包的用途：一个是可以读取函数内部的变量，2就是让这些变量的值始终保存在内存中不会在函数调用后被自动清除
  - 闭包的注意点:由于闭包会使得函数中的变量都被保存在内存中，内存消耗很大，所以不能滥用闭包，否则会造成网页的性能问题，在IE中可能导致内存泄露。解决方法是，在退出函数之前，将不使用的局部变量全部删除。

  - 闭包会在父函数外部，改变父函数内部变量的值。所以，如果你把父函数当作对象（object）使用，把闭包当作它的公用方法（Public Method），把内部变量当作它的私有属性（private value），这时一定要小心，不要随便改变父函数内部变量的值。
- new与面向对象
- event loop
- event delegation/proxy
- 节流与防动 [传送门](https://www.jianshu.com/p/c8b86b09daf0?tdsourcetag=s_pcqq_aiomsg)
  - 抖动：把在指定时间内可能会多次执行的方法打包成一次
  - 节流：节流函数允许一个函数在规定的时间内只执行一次
  - 区别：节流函数不管事件触发有多频繁，都会保证在规定时间内一定会执行一次真正的事件处理函数
  - 防抖动debounce：将几次操作合并为一此操作进行。原理是维护一个计时器，规定在delay时间后触发函数，但是在delay时间内再次触发的话，就会取消之前的计时器而重新设置。这样一来，只有最后一次操作能被触发。

  - 节流throttle ：使得一定时间内只触发一次函数。
  - 它和防抖动最大的区别就是，节流函数不管事件触发有多频繁，都会保证在规定时间内一定会执行一次真正的事件处理函数，而防抖动只是在最后一次事件后才触发一次函数。
  - 原理是通过判断是否到达一定时间来触发函数，若没到规定时间则使用计时器延后，而下一次事件则会重新设定计时器
- Promise
   - Promise 的在三种状态 ：pending 进行中 fulfilled 已成功 rejected 已失败
   - then() 在Promise中是通过then()方法来指定处理异步操作结果的方法
   - catch() 是promise实例的方法 它其实是.then(null,rejection)的简写 用于指定 发生错误时的回调 catch()返回一个Promise对象
   - promise对象的Error对象具有冒泡性质，会一直向后传递，直到被捕获为止,即 错误 总是会被下一个catch语句捕获
   - all() 用于将多个Promise实例 包装成一个新的promise实例 全部成功才成功 否则失败
   - race() 其中任意一个实例率先改变，它的状态就跟着改变，而且状态有率先改变的实 例决定
   - Promise.resolve()可以将现有的对象装换为promise对象
   - Promise.reject() 返回一个新的promise实例 它的状态为rejected
   - finally() 用于指定不管promise对象最后的状态如何都会执行
   - done() 处理回调链的尾端，保证抛出任何可能出现的错误
- SPA路由原理
- 本地存储localStorage、sessionStorage与cookie之间的区别

## Vue
- 深入Vue的响应原理?
- Vue多版本之间的区别（运行时依赖，运行时编译）?
- Vue中computed、watch与methods的区别
- 多种指令与自定义指令
- 路由传参与导航守卫
- Element UI && so on

## React
- 什么是MVVM？React与Vue的区别与联系？
- JSX语法、Virtual DOM与DOM Diff算法？
- 详细介绍生命周期(三个阶段，生命周期的触发顺序)？
- 合成事件与改变this指向的三种方式及之间的区别？
- 样式绑定与CSS Modules
- 多种组件创建方式及其区别？什么是受控组件？
- 高阶组件与装饰器
- 组件通信的多种方式及其之间的区别
- React Router及其简单实现
- Redux数据流向及三个中间件（redux-logger、redux-thunk、redux-saga）
- Ant Design && so on

## 快排
- 通过两个for循环，每一次对比相邻两个数据的大小，小的排在前面，如果前一个比后一个大就交换位置


![快排1](/study/img/QuickSort1.png)
- 1）先判断数组的长度，如果小于等于1，直接return返回，2）去取数组中间的值， 然后遍历数组，把比中间的小的放在一个数组里，比中间值大的放在另一个数组中最后合并数组


![快排2](/study/img/QuickSort2.png)

## 浏览器渲染流程


![浏览器渲染流程](/study/img/windowRender.png)


## 预渲染

 - 在webpack中配置
    const PrerenderSPAPlugin = require('prerender-spa-plugin')
 - 如何通过预渲染的方式降低空白屏的时间
   - 尽可能的缩小webpack或者其他打包工具生成的包的大小 
   - 使用服务端渲染的方式 
   - 使用预渲染的方式 
   - 使用gzip减小网络传输的流量大小 
   - 按照页面或者组件分块懒加载


 [传送门](http://www.imooc.com/article/78956)


## ES6 模块化
 - Es6的模块化分为导出(export) 与(import)两个模块
 - AMD即Asynchronous Module Definition,实现提前加载  requirejs  
 - AMD采用异步方式加载模块，模块的加载不影响它后面语句的运行。所有依赖这个模块的语句，都定义在一个回调函数中，等到加载完成之后，这个回调函数才会运行
 - CMD即 common moudle definition实现按需加载  commonjs     通用模块定义
#### CMD与AMD的不同的在于：
   - AMD推崇依赖前置；CMD推崇依赖就近，只有在用到某个模块的时候再去require：
   - AMD用户体验好，提前加载，CMD性能好 用户需要时才加载
 - import 做两件事 加载js 挂载js 
 - import 返回的promise对象
#### 模块化开发的优点：
 - 代码复用，让我们更方便地进行代码管理、同时也便于后面代码的修改和维护。
 - 一个单独的文件就是一个模块，是一个单独的作用域，只向外暴露特定的变量和函数。这样可以避免污染全局变量，减少变量命名冲突。
#### js模块化规范有：CommonJS、AMD、CMD、ES6的模块系统。

### export的用法
 - 在ES6中每一个模块即是一个文件，在文件中定义的变量，函数，对象在外部是无法获取的。如果你希望外部可以读取模块当中的内容，就必须使用export来对其进行暴露（输出） 如果你不想暴露模块当中的变量名字,可以通过as来进行操作
 ![图片](/study/img/export1.png)
 ![图片](/study/img/export2.png)
 ![图片](/study/img/export3.png)
#### 默认导出：一个模块只能哟一个默认导出，对于默认导出，导入的名称可以和导出的名称不一致
 ![图片](/study/img/export4.png)
#### 混合导出
 ![图片](/study/img/export5.png)
 ![图片](/study/img/export6.png)
 

## Object.definedProperty()
 - 语法： Object.definedProperty(obj,prop,descriptor)
 - 参数: obj:被定义或修改属性的对象
 - prop:要定义或修改的属性名
 - descriptor:对属性的描述
 - configurable 可配置 可删除 默认为false
 - enumerable 可枚举(遍历) 默认为false
 - writable 可写(赋值操作) 默认为false
 - value 设置属性值 
 - get() 当获取值时触发的函数
 - set() 设置值是触发的函数 设置的值通过value值拿到

### async/await
 - async 作为关键字放到函数前面 表示是一个异步函数 它返回一个promise对象
 - await 等待的意思 它后面可以跟任何表达式，但我们更多放一个返回promise对象的表达式 注意await只能放到async函数里 

### Proxy是一个构造函数 使用new Proxy创建代理器 第一个参数为一个对象 第二个参数也是一个对象 返回被包裹后的代理器
 - get(target,props)获取值触发的函数
 - set(target,props,value)设置值触发的函数

#### 堆内存：引用类型
#### 栈内存：基本类型

## 单页面应用(SPA)
 - 只有一张Web页面的应用，是一种从Web服务器加载的富客户端，单页面跳转仅刷新局部资源 ，公共资源(js、css等)仅需加载一次，常用于PC端官网、购物等网站
 - ![单页面应用](/study/img/spa.png) 

## 多页面应用(MPA)
 - 多页面跳转刷新所有资源，每个公共资源(js、css等)需选择性重新加载，常用于 app 或 客户端等
 - ![多页面应用](/study/img/mpa.png)
### 区别
 - ![区别](/study/img/spampa.png)

## Vue生命周期图
 - ![vue](/study/img/vue.png)

## React生命周期图

  - ![react](/study/img/react1.png)

  - ![react](/study/img/react2.png)

  - ![react](/study/img/react3.png)
## 跨域 
  ### 同源策略
    - 相同协议 
    - 相同域名
    - 相同端口
 - 解决跨域方法 [详情](https://blog.csdn.net/qq_38128179/article/details/84956552)
 
 ### 反向代理
  - proxy
  - proxies
 ### JSONP
   - jsonp是前端解决跨域最实用的方法
   - 原理就是html中 的link,href,src属性都是不受跨域影响的，link可以调用远程的css文件，href可以链接到随便的url上，图片的src可以随意引用图片，script的src属性可以随意引入不同源的js文件

## http强缓存(本地缓存)和协商缓存
  - ![区别](/study/img/http1.png)
  - 与强制缓存相关：catch-control、expires
  - 与协商缓存相关：Last-Modified/if-Modified-Since、Etag/if-None-Match.
  - ![区别](/study/img/http2.png)
  - [详情](https://blog.csdn.net/lncci/article/details/82182788)



