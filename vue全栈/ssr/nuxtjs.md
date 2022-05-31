Nuxt.js：基于vue.js的通用应用框架 

    通过对客户端/服务端基础架构的抽象组织，Nuxt.js主要关注的是应用的ui 渲染。 

特性： 
* 代码分层
* 服务端渲染 
* 强大的路由功能 
* 静态文件服务 
 
# Nutx.js渲染流程  

Nutx安装：npx create-nutx-app <项目名> 

运行项目：npm run dev 


案例：  
实现如下功能点： 
* 服务端渲染
* 权限控制 
* 全局状态管理 
* 数据接口调用 

 

路由：生成：pages目录中所有*.vue文件自动生成应用的路由配置，新建：pages/admin.vue 商品管理页。 


导航： 

添加路由导航， layouts/default.vue 
```javascript
<nav> 
    <nuxt-link to="/">首页</nuxt-link> 
    《别名：n-link，Nlink,NuxtLink》 
</nav> 
```
功能和router-link等效 

属性：no-prefetch 禁用预加载行为 