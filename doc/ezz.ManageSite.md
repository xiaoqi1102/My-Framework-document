### e找砖后台管理系统 
#### 简述:
> * 此项目对项目目录进行一写整理,所有的源码都放在src目录下 
> * lib 目录存放的是除了npm 完成安装之外的模块 
> * 打包的文件都会在build 目录下
#### [1]相关第三方类库及示例:
##### (1) react
##### (2) react-router
> * react-router 有多种路由可选,browserHistory 必须有服务器端支持 ,没有服务器端支持的同学自觉使用 hashHistory
###### 关键api:

```
//跳转到另一个路由路径:
 hashHistory.push('...')
//替换当前路由:
 hashHistory.replace('...')
//返回上级路由
 hashHistory.goBack();
```
##### (3) redux 推荐教程:[Redux 中文文档](http://cn.redux.js.org/index.html)
###### 要点:
- 应用中所有的 state 都以一个对象树的形式储存在一个单一的 store 中。
- 惟一改变 state 的办法是触发 action，一个描述发生什么的对象。
- 为了描述 action 如何改变 state 树，你需要编写 reducers。

##### (4)  [redux-chunk](https://github.com/gaearon/redux-thunk)

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
          
##### (5) [react-bootstrap](http://react-bootstrap.github.io/)
##### (6) webpack
###### 说明:用于jsx css img 等文件的编译打包方案
###### 要点:

- 掌握loader 加载器的配置  
- webpack的编译速度优化 

#### 约定及注意事项
- e找砖后台管理系统使用的 react-bootstrap 版本是@0.29.4
- 菲特后台管理系统使用的 react-bootstrap 版本是@0.28.3 版本不同组件的使用方式有差别请注意
- package.json 的scripts 存储了打包编译的命令 如:
- 将用于开发环境的webpack 配置文件和 生产环境的配置文件分开

```
 "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1",
    "build": "webpack --config webpack.config.js -w --colors --profile --display-modules",
    "start": "webpack-dev-server --config webpack.dev.config.js --devtool eval --progress --hot --colors --content-base build"
  },

```
> *  开发测试的命令为: npm start
> *  打包生成生成生产环境的文件: npm run build
> * react 项目中的编程方式倾向于 ES6简洁 的编程语法
> * 使用babel 进行ES6 的编译 相关链接: [Babel 入门教程](http://www.ruanyifeng.com/blog/2016/01/babel.html)
