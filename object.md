### create

```javascript
let user = new Object(); // “构造函数” 的语法
let user = {};  // “字面量” 的语法
```

### 判断是否存在
```javascript
let obj = {
    test: undefined
};

alert( obj.test ); // 显示 undefined，所以属性不存在？

alert( "test" in obj ); // true，属性存在！
```

### operation object
```
删除属性：delete obj.prop。
检查是否存在给定键的属性："key" in obj。
遍历对象：for(let key in obj) 循环。
```

### gc
```angular2html
same with golang, reachable analyse
```

### this
```angular2html
https://www.ruanyifeng.com/blog/2018/06/javascript-this.html

this 不是对象的this，是运行环境的this
```

### visit opt props safely
```angular2html
可选链 ?. 语法有三种形式：

obj?.prop —— 如果 obj 存在则返回 obj.prop，否则返回 undefined。
obj?.[prop] —— 如果 obj 存在则返回 obj[prop]，否则返回 undefined。
obj.method?.() —— 如果 obj.method 存在则调用 obj.method()，否则返回 undefined。
```

