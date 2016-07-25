
### 移动端多页应用程序
#### [1]主要技术:
##### (1) webpack 推荐教程:[webpack入门教程](https://fakefish.github.io/react-webpack-cookbook/index.html)
###### 说明:
-在此项目中 webpack 只用做编译 ES6

##### (2) gulp 推荐教程: [gulp中文网](http://www.gulpjs.com.cn/docs/api/)
###### 用途&说明:
- 将less 文件编译成 css 文件后缀: .less
- 将jade 编译成html 文件后缀: .jade
- 将handlebar 编译成 js 模板方法  .handlebars .hbs
- 其他资源整合

##### (3) ES6 推荐教程:[阮一峰ES6入门教程](http://es6.ruanyifeng.com/)
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

##### (4) handlebars [js模版引擎handlebars.js实用教程](http://www.cnblogs.com/iyangyuan/archive/2013/12/12/3471227.html)
##### (5) less 推荐教程:[less中文网](http://www.bootcss.com/p/lesscss/)
##### (6) jade
#### 约定及注意事项

- 打包命令 $ npm start
- 编译及打包的配置文件 gulpfile.js