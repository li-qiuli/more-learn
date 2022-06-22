问题：
```javascript

const root =ReactDom.creactRoot(document.getElementById('root'))
root.render(
 // 严格模式去掉
// 会影响useEffect的执行时机
<ReactDom.StrictMode>
    <App>
</ReactDom.StrictMode>
)
```