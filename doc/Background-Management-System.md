###  后台管理系统
#### [1]相关第三方类库及示例:
##### (1) react
##### (2) react-router
##### (3) redux
##### (4) redux-thunk
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
    "build": "webpack --config webpack.build.config.js -w --colors --profile --display-modules",
    "start": "webpack-dev-server --config webpack.dev.config.js --devtool eval --progress --hot --colors --content-base build"
  },

```
> *  开发测试的命令为: npm start
> *  打包生成生成生产环境的文件: npm run build
