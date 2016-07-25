###  app单页应用程序架构
#### [1] 组件化思路:
#### [2] 框架主要思路:
- 单向数据流
- react 基于状态机的dom渲染

#### [3]主要技术:
##### (1)ionic 
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
##### (2)cordova

###### 常用插件:


```
相机:
$ cordova plugin add cordova-plugin-camera

白名单:
$ cordova piugin add cordova-plugin-whitelist

上传/下载文件组件:
$ cordova plugin add cordova-plugin-file-transfer

剪切板 :
$ cordova plugin add https://github.com/VersoSolutions/CordovaClipboard

消息通知:
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
##### (4) redux
##### (5) react-redux
##### (6) react-router
##### (7) redux-chunk
##### (8) webpack