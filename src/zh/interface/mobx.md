---
title: mobx
sidebar: auto
sidebarDepth: 2
---
# mobx
  ### 快速新建一个项目
```
  npx create-react-app mobx-react

  cd mobx-react

  yarn eject
```
  报错的话执行 git add . 
  git commit -m "aa"
  ### 安装依赖包 
```
   yarn add babel-plugin-transform-decorators-legacy @babel/plugin-proposal-decorators mobx mobx-react --save-dev
```
  ### 配置package.json
```
   "babel": {
    "plugins":[
      [
        "@babel/plugin-proposal-decorators",
        {
            "legacy":true
        }
      ],
      [
        "@babel/plugin-proposal-class-properties",
        {
            "loose":true
        }
        ]
      ],
    "presets":[
    "react-app"
    ]
  }
```
 index.js中
```
   import React from 'react';
   import ReactDOM from 'react-dom';
   import App from './App';
   //引入provider
   import {Provider} from "mobx-react"
   //引入store
   import store from "./store"

   ReactDOM.render(<Provider {...store}><App /></Provider>, document.getElementById('root'))
```
  APP.js
```
  import React from 'react';
  import {inject,observer} from "mobx-react"
  @inject("count")
  @observer
  class App extends React.Component{
    render(){
        console.log(this.props)
        return (
        <div>
        <button onClick={()=>this.props.count.changeCount('+')}>+</button>
        <p>{this.props.count.count}</p>
        <button onClick={()=>this.props.count.changeCount('-')}>+</button>
        </div>)
  }
}

export default App;
```
 store.js中
```
  //加载子模块
  import Count from "./moudle/count"
  //引入日志
  // import {autorun} from "mobx"

  let count=new Count()

  export default {
    count
  }
```
 子模块中
```
    import { observable, action } from "mobx"
    export default class Count {
    //模块的数据
    @observable count = 1;//可观察的状态
    //模块的行为
    @action changeCount(type) {
        type === '+' ? this.count++ : this.count--
    }
    }
```
  
  