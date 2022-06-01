6.bit语义化版本控制学习 

https://semver.org/lang/zh-CN/ 

 

bit list 查看本地组件 

bit list -s <scope> 查看remote组件 

bit show <id> | <remote id> 可以查看组件的信息 

bit status 查看本地组件状态 

 

bit add 添加索引文件（bit <组件> --tests <测试文件> --id <自定义ID>） 

{ 
* bit import bit.envs/compilers/babel --compiler babel 编译环境 
* bit import bit.envs/testers/jest --tester jest测试环境 （不稳定，不建议使用） 
* bit import bit.envs/testers/mocha --tester mocha测试环境(yarn add -D mocha chai) 

} 

 

bit tag 组件版本 

bit tag <id> --major         with a major version.   1.0.0 -> 2.0.0 
bit tag <id> --minor          1.0.0 --> 1.1.0 
bit tag <id> --patch           1.0.0 ---> 1.0.1 

 

bit import <远程组件>  导入组件本地开发 

bit export <远程库>  导出组件到远端  {--eject (退出组件开发状态)} 

 

bit test <id>组件测试 

*bit install 用于安装组件内的package 依赖包，这个也是比较有用的 

 

bit untag 可以用于撤销本地已经给组件打的tag版本 

git untrack 可以使untrack 一个还没有打tag的组件 

 

bit checkout 在组件版本之间切换 

bit remove id 更改仓库地址 先remove 再add->.... 

bit init --standalone (删除了.bitmap文件，bit init 报错) 

bit remove heieo.frontend.test/demo --remote(删除远程) 

 

***Url:***

npm install bit-bin -g 

https://docs.bit.dev/docs/best-practices.html 

https://docs.bit.dev/docs/installing-components.html(安装) 

 

 

选用一个boilplate 来创建一个项目demo https://github.com/hodgef/js-library-boilerplate， 这是es6 webpack 的一个starter，可以选用其他的starter 

 

git clone https://github.com/hodgef/js-library-boilerplate demo ,  

 

bit登陆： https://bit.dev/21epub 

 

 测试bit地址    heieo.21epub 用于存放生产性 组件代码 

https://bit.dev/heieo/frontend    

 

 

石墨文档 

https://shimo.im/docs/VNLysCJLIRU6htjo 

 