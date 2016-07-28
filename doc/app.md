###  app单页应用程序架构
#### [0] 简述:
> * 使用cordova 做为app 打包方案
> * 使用ionic 作为app 的基础样式库 
> * 使用react 作为组件化开发方案 
> * 使用react-router 作为路由
> * redux react-redux redux-thunk 做状态管理

#### [1] 框架主要思路:

- 单向数据流
- react 基于state状态机的dom渲染,推荐文章:[React 源码剖析系列 － 解密 setState](https://zhuanlan.zhihu.com/p/20328570?refer=purerender)
- react 生命周期,推荐文章:[React 源码剖析系列 － 生命周期的管理艺术](https://zhuanlan.zhihu.com/p/20312691?refer=purerender)

#### [2]相关第三方类库及示例:
##### (1)ionic 
##### [ionic 组件库](http://ionicframework.com/docs/components/)
> * 特别说明:
> ionic 的组件库 本身是用于angularJS 开发app的,但是angular组件dom渲染的结果和一般的HTML的DOM
> 是没有差别的,所以本项目是以ionic的css为样式库,定义了项目自身的react 组件

##### [ionic icon 库](http://ionicons.com/)
###### 使用示例:
```
安装:
$ npm install ionic -g 

启动服务器:
$ ionic serve

添加平台:

android:
$ ionic platform add android

ios:
$ ionic platform add ios

打包:

安卓包:
$ ionic build android

ios 包:
$ ionic build ios

打包全部平台:
$ ionic build 
```
######  [Automating Icons and Splash Screens](http://blog.ionic.io/automating-icons-and-splash-screens/)
 
> * 在resources 中放置 icon.png 和 splash.png ,然后执行命令:

```
 $ ionic resources
```
> 那么该操作进行的操作是,将icon.png splash.png 作为源图片 ,上传到ionic的服务器,
> 并将适配多种尺寸屏幕的图片下载下来 存入resources目录下
> 值得注意的是 图片的尺寸是有相关要求的 ,详情请自行看文章链接

###### [ionic PROBLEM ](http://www.ayqy.net/blog/ionic%E5%BC%80%E5%8F%91%E8%B7%A8%E5%B9%B3%E5%8F%B0app%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98/)
##### (2)cordova

###### 常用插件:


[相机](https://www.npmjs.com/package/cordova-plugin-camera):
```
$ cordova plugin add cordova-plugin-camera


```
[白名单:](https://www.npmjs.com/package/cordova-plugin-whitelist)

```

$ cordova piugin add cordova-plugin-whitelist

```

[上传/下载文件组件:](https://www.npmjs.com/package/cordova-plugin-file-transfer)

```

$ cordova plugin add cordova-plugin-file-transfer

```

[剪切板 :](https://github.com/VersoSolutions/CordovaClipboard)
```

$ cordova plugin add https://github.com/VersoSolutions/CordovaClipboard

```

[消息通知:](https://github.com/katzer/cordova-plugin-local-notifications)
```

$ cordova plugin add https://github.com/katzer/cordova-plugin-local-notifications

```
###### 其他命令

```

查看插件列表:
$ cordova plugin ls

移除某个插件:
$ corodva plugin rm cordova-plugin-whitelist

```
##### (3) react

写一个组件:
```
import React from 'react';

const Account extends React.Component(){
 constructor(props) {
    super(props);
    //初始化当前组件state
    this.state = {name:'小齐'};
  }
render(){
return(
<div>
hello I am {this.state.name};
</div>
)
}
}
//将组件暴露出去
export default Account;
```
##### (4) redux 推荐教程[Redux 中文文档](http://cn.redux.js.org/index.html)
###### 要点:
> * 应用中所有的 state 都以一个对象树的形式储存在一个单一的 store 中。
> * 惟一改变 state 的办法是触发 action，一个描述发生什么的对象。
> * 为了描述 action 如何改变 state 树，你需要编写 reducers。
###### 示例:

```
//创建一个reducers 
import { combineReducers } from 'redux'
import todos from './todos'
import counter from './counter'
export default combineReducers({
  todos,
  counter
})
```
##### (5) react-redux
##### (6) [react-router](https://github.com/reactjs/react-router)
###### 要点:
> * react-router 有多种路由可选,browserHistory 必须有服务器端支持 ,没有服务器端支持的同学自觉使用 hashHistory
> * 推荐教程:[React Router 使用教程](http://www.ruanyifeng.com/blog/2016/05/react_router.html)
###### 关键api:

```
//跳转到另一个路由路径:
 hashHistory.push('...')
//替换当前路由:
 hashHistory.replace('...')
//返回上级路由
 hashHistory.goBack();
```
##### (7) [redux-chunk](https://github.com/gaearon/redux-thunk)
###### 说明:用于使用异步action,用法比较简单,在项目中加配置即可

```
import { createStore, applyMiddleware } from 'redux';
import thunk from 'redux-thunk';
import rootReducer from './reducers/index';

// Note: this API requires redux@>=3.1.0
const store = createStore(
  rootReducer,
  applyMiddleware(thunk)
);

```


##### (8) webpack
###### 说明:用于jsx css img 等文件的编译打包方案
###### 要点:
- 掌握loader 加载器的配置  
- webpack的编译速度优化 
- 各种plugin 

##### (9) [material-ui@0.14.4](http://www.material-ui.com/v0.14.4/)
##### (10) ES6 推荐教程:[阮一峰ES6入门教程](http://es6.ruanyifeng.com/)
###### 要点:
> * Promise 示例:

```
let getData=(id)=>{
   return new Promise(function(resolve,reject){
   $.ajax({
   url:'http://192.168.1.107:4000/account',
   type:'get',
   data:{accountId:id},
   success:function(res){
    resolve(res)
   },
   error(err){
   reject(err);
   }
   }) 
   })
};
//推荐使用promise的方式 添加回调
getData('1212ads').then(function(res){
console.log(res)

},function(err){
console.log(err)
})

```

> * 箭头函数 

```
//函数写法 
const getData=()=>{
console.log('get data');
}

```

> * 对象扩张 Object.assign 等方法 示例:


```

let a={a:123},b={name:'myName'}; 
let c = Object.assign({},a,b);
console.log(c);//Object {a: 123, name: "myName"}

```

> * 数组扩张  Array.find() 等方法,示例:

```

let array=[{id:1},{id:2}];
let result=array.find(function(item,index){ return item.id==1});
console.log(result);

```
###### 说明:
> 使用material-ui 中的一些组件
#### [3] 约定及注意事项
约定:
- package.json 的scripts 存储了打包编译的命令 如:
- 将用于开发环境的webpack 配置文件和 生产环境的配置文件分开(app架构暂时没有分离,有待优化)
```
 "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "webpack --config webpack.build.config.js -w --colors --profile --display-modules",
    "start": "webpack-dev-server --config webpack.dev.config.js --devtool eval --progress --hot --colors --content-base build"
  },

```
> *  开发测试的命令为: npm start
> *  打包生成生成生产环境的文件: npm run build
