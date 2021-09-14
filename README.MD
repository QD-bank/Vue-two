# Vue的两个版本

Vue有完整版和非完整版的区别

## 版本区别
 

* 非完整版对应文件名：vue.runtime.js ； vue.runtime.min.js。没有compiler,不能将HTML变成节点。webpack通过vue-loader(在yarn build里已设置)将html变成h('div',this.n)
* 完整版对应文件名：vue.js ; vue.min.js 。可以从HTML或template直接得到视图,有compiler编译器可以将含有占位符{{}}或者条件语句变成真实的DOM节点，代码体积大40%左右。
  
## template和render使用

template:一个替换挂载的元素模板。挂载元素的内容都将被忽略，除非模板的内容有分发插槽。

template的使用方法：直接写在HTML或JS上
```javascript
<template>
  <div id='app'>
    {{n}}
    <button @click = 'add'>+1</button>
  </div>
</template>
```
render:字符串模板的代替方案，允许你发挥 JavaScript 最大的编程能力。该渲染函数接收一个 createElement 方法作为第一个参数用来创建 VNode。

render的使用方法：

render函数接受一个参数h，这个参数是vue传的；用这个参数去创建实例
```javascript
render(h){
    return h('div',[this.n,h('button',{on:{click:this.add}},'+1')])
}
```

## 使用Codesandbox写Vue代码

* 第一步：点击链接直接进入网页

   [Codesandbox地址](https://codesandbox.io/)

* 第二步：点击Create Sandbox
  
![第二步](/image/1631606519(1).png)

* 第三步：选择创建Vue项目,会自动生成所需文件
  
![第三步](image/1631606779(1).png)