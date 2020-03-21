# RequireJs 路径的三种写法

###  写法一：完整url地址

```javascript
requirejs(['https://www.baidu.com/a.js'],function(){})
```

这种写法很显然，不必多做解释

### 写法二：相对路径（带.js后缀）

```javascript
requirejs(['a.js'],function(){})
```

如果载入的模块名称包含.js ,requirejs 会载入相对当前页面的路径下的js文件  
比如当前访问的是:  
http://www.baidu.com/test/index.html,  
上面的例子载入的js文件是:  
 http://www.baidu.com/test/a.js;

### 写法三：相对路径（不带.js后缀）

```javascript
requirejs.config({
    baseUrl:"http://ztgame.com/libs/"
})
requirejs(['a'],function(){})
```

如果载入的模块名称不带.js后缀，requirejs 会根据配置的baseUrl来寻找对应的模块,上面的例子中requirejs最终载入的js文件地址是：  
http://ztgame.com/libs/a.js  


