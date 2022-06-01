Async post 

```javascript
const getData=async()=>{ 
    try { 
        const response=await fetch('https://api-to-call.com/endpoint',{ 
            method:'POST', 
            body:JSON.stringify({id: 200}) 
        }) 
        if(response.ok){ 
            const jsonResponse=await response.json() 
            return jsonResponse 
        } 
        throw new Error('Request failed!') 
    }catch(error){ 
        console.log(error) 
    } 
} 
 
//返回信息操作  
mergeImg() { 
    let params = { 
        'ModelId': ‘’, 
        'merge_base64': ‘’, 
    }; 
    return new Promise((resolve, reject) => { 
        axios({ 
            method: 'post', 
            url: 'services/', 
            data: params , 
            headers: { 
            'Content-Type': 'application/x-www-form-urlencoded', 
        } 
        }).then(response => { 
            if (response.data.code === 200) { 
                resolve(response.data.data.results.image_url); 
            } else { 
                throw new Error(response.data.msg);(将错误信息放入reject) 
            } 
        }).catch(error => { 
            reject(error); 
        }); 
    }); 
} 
```
```javascript
//合并对象 

1. this.options = Object.assign(this.defaults, option); 
2. this.options = (…this.defaults, …option); 

//节点操作 
1. element.appendChild（newNode） 
//将新的子节点作为最后一个子节点添加到元素。 
2. insertBefore（node1，node2） 
//在node2之前将node1作为子节点插入。
``` 

区分pc端与手机端 

```javascript
let c=navigator.userAgent 

if(c.match(/(phone|pad|pod|iPhone|iPod|ios|iPad|Android|Mobile|BlackBerry|IEMobile|MQQBrowser|JUC|Fennec|wOSBrowser|BrowserNG|WebOS|Symbian|Windows Phone)/i)) { 
    // window.location.href="移动端url"; 
    alert("mobile"); 
    //判断访问环境是 移动端 则加载以下样式 
    setStyle(['css/public/base.css','css/layout.css','css/home.css']); 
}else { 
    // window.location.href="pc端url"; 
    alert("pc")  
} 
```

# WebSocketd
```javascript
if ('WebSocket' in window) { 
    ttsWS = new WebSocket(url) 
} else if ('MozWebSocket' in window) { 
    ttsWS = new MozWebSocket(url) 
} else { 
    alert('浏览器不支持WebSocket') 
    return 
} 

// 连接成功后的回调函数。 
ttsWS.onopen = e => { 
    // 用于向服务器发送数据。 
    ttsWS.send(JSON.stringify(newParam)) 
} 

// 指定收到服务器数据后的回调函数。 
ttsWS.onmessage = e => { 
    result(e.data) 
    // 客户端主动断开链接的方法ws.close() 
    ttsWS.close() 
} 

// 指定报错时的回调函数。 
ttsWS.onerror = e => {} 

// 连接关闭后的回调函数。 
ttsWS.onclose = e => {
    console.log(e) 
} 
```