---
title: JSX知识点
sidebar: auto
sidebarDepth: 2
---
# JSX

## JSX简介
```
const element = <h1>Hello, world!</h1>
```
它被称为JSX,是一个JavaScript的语法扩展。我们建议在React中配合使用JSX，JSX可以很好的描述UI应该呈现出它应有交互的本质形式。JSX可能会使人联想到模板语言,蛋挞具有JavaScript的全部功能。


## 为什么使用JSX？
React 认为渲染逻辑本质上与其他 UI 逻辑内在耦合，比如，在 UI 中需要绑定处理事件、在某些时刻状态发生变化时需要通知到 UI，以及需要在 UI 中展示准备好的数据


React 不强制要求使用 JSX，但是大多数人发现，在 JavaScript 代码中将 JSX 和 UI 放在一起时，会在视觉上有辅助作用。它还可以使 React 显示更多有用的错误和警告消息

## JSX 也是一个表达式
在编译之后，JSX 表达式会被转为普通 JavaScript 函数调用，并且对其取值后得到 JavaScript 对象。

## JSX 特定属性

你可以通过使用引号，来将属性值指定为字符串字面量
```
const element = <div tabIndex="0"></div>;
```
也可以使用大括号，来在属性值中插入一个JavaScript表达式
```
const element = <img src={user.avatarUrl}></img>;
```
在属性中嵌入 JavaScript 表达式时，不要在大括号外面加上引号。你应该仅使用引号（对于字符串值）或大括号（对于表达式）中的一个，对于同一属性不能同时使用这两种符号

警告：

因为 JSX 语法上更接近 JavaScript 而不是 HTML，所以 React DOM 使用 camelCase（小驼峰命名）来定义属性的名称，而不使用 HTML 属性名称的命名约定。

例如，JSX 里的 class 变成了 className，而 tabindex 则变为 tabIndex。

## 使用JSX指定元素

假如一个标签里面没有内容，你可以使用 /> 来闭合标签，就像 XML 语法一样：
```
const element = <img src={user.avatarUrl} />;
```
jsx标签里能够包含很多子元素
```
const element = (
  <div>
    <h1>Hello!</h1>
    <h2>Good to see you here.</h2>
  </div>
);
```

### 详细了解JSX
- [JSX简介](https://react.docschina.org/docs/introducing-jsx.html)
