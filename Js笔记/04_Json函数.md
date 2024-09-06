## 	JavaScript Oject Notation

1.总体来说 简称json

2.两种数据交换模式使用最多xml（语法严谨解析麻烦）与json

​	使用json的优点

- 体积小
- 容易解析

3.Json的格式

```javascript
//这个是json
let datas = {
	"totals":5,
	"student":[
	{"name":"小明","hobby":"吃饭"},
	{"name":"小明","hobby":"吃饭"},
	{"name":"小明","hobby":"吃饭"},
				]
}
//这个是数组
const b = [a,a,a,1,2,3]
```

JSON:JavaScript 对象标记法

Json格式化网站

语法简单 多用于数据传输。前端后端传输响应复杂函数。

- 调用格式

​	对象名.属性名,

​	对象名.函数名，	

------

Eval函数

将字符串内的js函数执行，使用方法将java发送过来的字符串转换为json对象

```javascript
window.eval("var a = 100;");

var fromJava = "var jsonObj = {"name":"zhangsan","pwd":"123456"} ";
window.eval("var jsonObj = " + fromJava);
```

因为java查询数据库后会拼接成一个json格式的字符串，并将json格式的字符串响应到浏览器

因此浏览器上接收到的结果还只是一个json格式的字符串还不是json对象

{}是Json []是数组

- 作用域  

var：是函数作用域和全局作用域。在函数内声明的`var`变量，整个函数内都是有效的，在`for`循环内定义的`var`变量，在`for`循环以外也可以访问 。 

let：是块级作用域，只在`let`命令所在的代码块内有效。如果在块作用域内（比如`for`循环内）定义的变量，在其外面是不可被访问的 。

- 变量提升  

  var：存在变量提升现象，即可以在声明之前使用，值为`undefined` 。  

  let：不存在变量提升，在声明之前使用会报错 。 

  重复声明  

  - var：可以允许重复声明相同的变量，后者会覆盖前者 。  

  - let：不允许在相同作用域内重复声明同一个变量 。  

     全局对象绑定  

    - var：在全局作用域中用`var`声明变量，此变量会默认成为`window`的一个属性。  
    - let：在全局作用域中用`let`声明变量则不会添加到`window`对象中。 
