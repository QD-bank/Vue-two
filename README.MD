# Vue的两个版本

Vue有完整版和非完整版的区别

## 版本区别
![版本区别](image/1631605317(1).png)

* 非完整版对应文件名：vue.runtime.js ； vue.runtime.min.js。没有compiler,不能将HTML变成节点。webpack通过vue-loader(在yarn build里已设置)将html变成h('div',this.n)
* 完整版对应文件名：vue.js ; vue.min.js 。可以从HTML或template直接得到视图,有compiler编译器可以将含有占位符{{}}或者条件语句变成真实的DOM节点，代码体积大40%左右。
  
## template和render使用

Vue完整版template的使用方法：直接写在HTML或JS上
```javascript
<template>
  <div id='app'>
    {{n}}
    <button @click = 'add'>+1</button>
  </div>
</template>
```
vue非完整版render的使用方法：

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
  
[第二步](./image/1631606519(1).png)

* 第三步：选择创建Vue项目,会自动生成所需文件
  
[第三步](/image/1631606779(1).png)