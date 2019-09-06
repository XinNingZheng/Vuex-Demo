# vuex-demo 
### 1.什么是Vuex

> 官方定义：

- Vuex是一个专门为Vue.js应用程序开的`状态管理模式`
- 它采用集中式存储管理应用的所有组件的状态（存在全局的对象中 ）
- 并以相应的规则保证以一种可预测的方式发生变化（响应式）

>简单来说：Vuex是一个类似于全局对象存储的所有组件里面的响应式数据状态

### 2.应用场景

- 多个视图依赖于同一状态（读）
- 来自不同视图的行为需要改变同一个状态（改）
- 适合中大型的前端页面应用，不适合小的单页面应用

### 3.Vuex的组成介绍

- State---------数据仓库（一个庞大的json对象）
- getter--------获取数据（类似于vue的computed，相当于从现有state中派生新的state）
- Mutation----修改数据（commit一个Mutatuin在传入state，每一次提交Mutation都会有一个记录，为了记录每个操作的历史，方便监听和回滚，只能写同步的，异步会有问题）
- Action-------提交mutation（可以进行异步操作）
- Module------模块化
 

### 安装

- 安装vuex包 npm install vuex
- 在mian.js中 new Vuex.store()
- mian.js中将vuex实例挂载到vue对象上
 

### 实现count++

- state中创建count字段
- mutations中创建一个count++的mutation
- button新增click事件触发mutation改变count
- 
### 如何获取Vuex中state里面的数据
 
- 通过实例
```
{{this.$store.state.count}}
```
- 定义一个计算属性
```html
<template>
  {{count}}
</template>

<script>
export default{
  computed:{
    count(){
      return this.$store.state.count;
    }
  }    
}
</script>
```
- 通过vuex启动的mapstate方法（一种function 通过解构的方式获得state数据）

```html<template>
<template>
  <span style="color: red;">{{memberInfo}}用户</span>
</template> 
<script>
  computed: {
    ...mapState(["userStatus", "vipLevel"]),
    ...mapGetters(["memberInfo"])
  },
<script>
```


### 案例讲解

> 业务目标

- 制作一个需要账号登陆的课程学习项目
- 不同的课程需要不同的会员等级`权限`，实现购买会员功能，课程分享

> 功能

- 通过state.userInfo控制用户登录路由限制
- 多组件共享state.userStatus和state.vipLevel状态
- 多组件修改state.userStatus和state.vipLevel


###  本地代码与远程仓库的链接
```
git init
git add .
git commit -m "提交的内容"
git remote add origin https://github.com/XinNingZheng/Vuex-Demo.git
git push -u origin master
```

## Project setup
```
yarn install
```

### Compiles and hot-reloads for development
```
yarn run serve
```

### Compiles and minifies for production
```
yarn run build
```

### Run your tests
```
yarn run test
```

### Lints and fixes files
```
yarn run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).


