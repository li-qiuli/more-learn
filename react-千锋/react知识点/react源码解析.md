https://learn.kaikeba.com/video/319370 

 

 

一、 

react/packages/react/src/ 

…ReactBaseClasses.js 

 

Compontent/PureCompontent 

 

函数组件与类组件怎样区分 : typeOf/isReactCompontent 

 

Compontent prototype原型中: setState/forceUpdate 

 

PureCompontent/Compontent区别： 

PureCompontent：内置了生命周期（想使用不想写。可使用） 

 

二、 

              …ReactElement.js 

 

creacteElement/clonEelement 

 

creacteElement(type,config,children) 

Key Ref  _self _source（系统带） 

 

key值在react diff算法中的作用：唯一性，diff时使用 

 

------>ReactElement()=>object 

$$typeof:REACT_ELEMENT_TYPE(symbol) 

 

 

三、 

react/packages/react-dom/src/client/ReactDom.js 

 /ReactDomLegacy.js 

 

fiberRoot 

child:{ 

stateNode:dom节点， 

index:下标， 

tag:节点类型 

sibling: 

Return:父节点 

} 

stateNode： 

原生标签:dom节点 

函数组件：null 

类组件：extents class 

 

 

 

Render 

三个参数（reactelement,dom,callback:render完成） 

 

四、 

react/packages/shared/ReactWorkTags.js 

 

react常见组件： 

函数组件、类组件（实力化）、原生标签节点、文本节点（插入）、《provider、consumer》（成对出现：不会生成真实的dom节点）、ForWardRef、MemoComponent 

 

 

 

react安全相关的问题 

 

react与vue的diff区别： 

虚拟dom数据结构唯一表示filber（单链表结构） 

 