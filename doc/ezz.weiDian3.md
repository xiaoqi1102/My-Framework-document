### e找砖微店
####目录结构：
```
..
├── app                     # 应用目录
│   ├── lib                 # 公共API目录
│   ├── components          # jade 组件视图目录(不会被直接编译,只会被引用)
│   ├── containers          # 容器视图目录(编译成html文件) 
│   ├── handlebars          # handlebars 数据模型目录
│   ├── static              # 静态资源目录
│       ├── less            # less 文件目录
│       ├── less            # css 文件目录
│       ├── img             # 图片文件 文件目录
│   ├── js                  # js模块目录
│       ├── entrance        # 入口js文件目录(会直接被编译)
│       ├── common          # 通用js模块目录(不会直接编译)
├── build                   # webpack 输出目录
├── server.js               # 前端开发服务器启动文件
├── gulpfile.js             # gulp 配置文件
```
#### 详细约定 :
> * 特别说明:js/common/parameter/parameter.js  封装了设置参数和读取参数的方法,当前是将参数封装在localStorage中
> js/common/name/nameSpace.js 系统常量的模块 便于对常量的值进行配置
> * js 目录下只有entrance下的文件会被直接编译,common目录下是通用的模块 ,是通过 ES6 module 方式被引入 并使用,也就是说某一个模块
> 或者说某一个函数可被复用  那么应该放在common 目录下 ,这是当前项目的约定
 
> * 多页应用程序每个页面保持只有一个入口js ,js只有一个入口函数 
> * 针对DOM 的绑定事件 要保证在dom 完成渲染之后再执行绑定函数
> * 入口函数 要引入 babel-polyfill 实现浏览器对ES6的兼容: 

```
import 'babel-polyfill';
```
> Babel默认只转换新的JavaScript句法（syntax），而不转换新的API，比如Iterator、Generator、Set、Maps、Proxy、Reflect、Symbol、Promise等全局对象，以及一些定义在全局对象上的方法（比如Object.assign）都不会转码。
> 举例来说，ES6在Array对象上新增了Array.from方法。Babel就不会转码这个方法。如果想让这个方法运行，必须使用babel-polyfill，为当前环境提供一个垫片。
