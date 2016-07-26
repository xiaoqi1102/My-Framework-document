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