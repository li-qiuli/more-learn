https://www.bilibili.com/video/BV18s411E7Tj 

# js中特殊数值端常量 

   Infinity                                表示无穷大的特殊值 

   NaN                                   特殊的非数字值 

  Number.MAX_VALUE     可表示端最大数字 

  Number.MIN_VALUE     可表示端最小数字 

  Number.NaN                   特殊的非数字值 

  Number.POSITIVE_INFINITY       表示正无穷大的特殊值 

  Number.NEGATIVE_INFINITY     表示负无穷大的特殊值 

# 编程锻炼：
https://www.codewars.com/ 

https://www.sololearn.com/Courses/ 

```javascript
/** 

* @name 获取数据类型 

* @param data  

* @returns Array|Object|Null|string|number|undefined|boolean 

*/ 

export const getDataType = (data) => { 

let typename: string='' 

if (typeof (data) == 'object') { 

let typestring = Object.prototype.toString.call(data) 

switch (typestring) { 

case '[object Array]': 

typename = 'Array' 

break; 

case '[object Object]': 

typename = 'Object' 

break; 

case '[object Null]': 

typename = 'Null' 

break; 

} 

return typename 

} else { 

typename = typeof (data) 

return typename 

} 

} 
```

js加密：jsrsasign 