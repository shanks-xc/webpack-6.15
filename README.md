很多人想起前端，都会想到一个字乱,js没有块级作用域，没有强制类的开发，即可面向过程开发，也有原型继承类似面向对象开发，更加没有模块化，想要性能优化还要把js，css合并减少请求量，压缩，用个es6还要弄个babel去解析，兼容性也是稀巴烂，但是==webpack==的到来，可以很好的解决了前端的工程化问题。
> 先简单介绍一下模块化，什么叫模块化？
我这里有两个个文件，并且有层级依赖关系，一般我们会这样做，直接上代码了
a.js
```
var myName = function(){
    return "shanks"
}
```

b.js
```
var printName = function(){
    cosole.log(myName())  //shanks
}
```

这里就存在一个简单的依赖关系，a文件必须要放在b文件前面才能正确被b文件引用，这样看好像没什么，但是会衍生一个很普遍的场景，例如a文件有其他冗杂的代码呢，我是不是全部都要加载？而且这里的函数名必须是全局的才能被b文件引用
缺点
* 1.污染全局变量
* 2.不能依赖加载

所以有问题的时候我们肯定要去解决问题所以==AMD(require.js)==,==CMD(sea.js)==,==common.js==，==es6==规范就出来了，有关各种方案大家可以了解一下，本来主要还是讲webpack的。那么webpack跟模块化有啥关系呢,在webpack我们可以使用common.js的规范例如
```
 //a.js
 exports.myName = function(){return "shanks"};
 
 //b.js
 var name = require('a');
exports.printName = function(n){
    console.log(a.name();
 };
```
这里我们就可以根据吐出引入来模块化我们的代码，当然我自己的项目会用es6，毕竟es6出了模块化的方案所以作为前端的一员当然也要跟随着es6的步伐。

#### webpack的相关介绍可以看[《webpack中文网》](https://www.webpackjs.com/concepts/)
* entry:管理入口文件
* output:管理输出文件
* loader:类似其他构建工具的tesk，利用不同的loader去解析不同的文件
* 插件plugins:目的解决loader无法实现的其他事情
* webpack-dev-server 能够用于快速开发应用程序：做代理跟一些启动浏览器，热加载

webpack除了可以帮我们完成模块化我们的代码，还能帮助我们解析es6，less，sass，将图片写成url形式....现在的vue-cli有前辈帮我们铺好了路我们可以直接使用，但是如果遇到多页的传统的jq方案，大家可以参考我的github，[《webpack多页》](https://github.com/shanks-xc/webpack-6.15),要投入真实项目的时候把webpack官网记载以及看下我的源码即可知道如何正确使用！



