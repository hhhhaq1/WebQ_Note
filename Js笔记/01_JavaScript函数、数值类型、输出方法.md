补充：

​	视频内容较久因此最新ECMA6/7有补充内容

#### 变量常量的定义方法

- 定义变量 let
- 定义常量 const
  - 标识符一般为大写,通常声明对象来使用 且不允许修改
- 模版字符串  ``
- 大括号里面，直接写入变量和函数，作为对象的属性和方法
- alert("两个数的差是: "+(x+y))
  alert(`两个数的差是: ${x - y}`)

##### 

JavaScript包括三大部分
- ECMAscript
- Bom （Brower obejct model）
- Dom（Document object model）

<script> 和 </script> 会告诉 JavaScript 在何处开始和结束。

Js使用方式

- ```html
  //外部导入法，一个js多个文件使用时候
  <script src="xx.js"></script>
  ```

- 内部直接插入，放置在head或者body部分，通常放置在head部分或者是页面底部，放置打乱网页顺序。

Java中有方法，Js中有事件

#### Js中的运算符号

- 一元运算符 `++`（自增）、`--`（自减）、`+`（正号）、`-`（负号）等。

- 算数运算符 +`（加）、`-`（减）、`*`（乘）、`/`（除）、  `%`（取余数）等。

- 比较运算符 `>`（大于）、`<`（小于）、`>=`（大于等于）、`<=`（小于等于）、`==`（相等）、`!=`（不相等）、`===`（严格相等）、`!==`（严格不相等）等。

- 逻辑运算符 `&&`（逻辑与）、`||`（逻辑或）、`!`（逻辑非）等。

  ```
  逻辑与:第一个是false输出n1,第一个为true 输出n2
  逻辑或:false- true-结果为true返回前面的值
  逻辑非:
  ```

#### Js中的数据类型

- == 只比较值是否相同（布尔）
- === 完全相同
- `${}`通常被用作字符串占位符，用于将变量值插入到字符串中,配合模版输入法``。

其中他们的判断方法是通过typeof来判断

1.Number(不同于Java，)

- Nan（运算结果应该是数字但是不是的时候显示）
- Infinity（除数为0结果为无穷大）
- 相关函数
  - isNan 判断是否不是数字
  - parseInt 取整
  - parseFloat字符串转换为数字
  - Math.ceil 取整 ceil是天花板的意思

2.Boolean

- alert(a==b); 结果为ture/false
- if后面的括号会自动转换为布尔函数
- 可以将数值自动转换 有为真 无为假

3.String

- ​	length    字符串长度（设置密码判断长度）
- ​        indexOf   获取指定字符串在当前字符串第一次出现的索引
- ​        lastIndexOf 获取指定字符串在当前字符串最后一次出现的索
- ​        replace   替换
- ​        substr    截取子字符串
- ​        substring  截取子字符串
- ​        （字符串.属性）

4.Underfined (变量未手动赋值)

- var i;
- var i = underfind;

5.Null (typeof运算结果为object)


以上为基本五种 以下为引用类型 

- Object

  - 所有类型的超类
  - 通过函数创建对象 定义对象属性

    ```javascript
        Product function (nno,nname,nprise){
        	this.nno=nno;
        	this.nname=nname;
        	this.nprise=nprise;
            	//使nprise这个属性可查
            	function this.getNprice(){
                    return this.nprice;
                }
        		this.getNprice=function(){
    				return this.nprise;   	
        	}
        }
        
        var apple = new Product(1101,"apple",55.01);
        var pri = apple.getNprice();
        alert(pri); 
    
    
    //通过prototype拓展属性
    	xx.prototype. 函数名 
    	 Product.prototype.getNname = function(){
                    return this.nname;
            }
    	
    ```
    
  - 属性

    - prototype 给类动态拓展属性和函数
    - constructor

- Symbol
- Bigint

​	Nan、null、underfind三者之间数据类型不同 number object underfind

**特殊运算符 typeof 使用

​	运算结果是字符串"string" number、boolean、function、string、underfind、object比较字符串实用"=="

#### Js中数据的显示和输出

显示数据的方法

- 使用模版符号可以简化写法 

```javascript
 alert("两个数的差是: "+(x+y))
alert(`两个数的差是: ${x - y}`)
```

- 写入到html元素

  ```javascript
  innerHTML=""; 
  ```

- 控制台中输出

  ```javascript
  console.log("输出到控制台中的信息");
  ```

- 输出windows弹窗

  ```javascript
  windows.alert("这是一个警告框");
  ```

- 输出html语句:	

  ```javascript
  document.write("<h1>asdsa</h1>");
  document.write(Date());
  ```

获取元素并且操作

- prompt 用户通过输入

- 通过id获取

- +prompt可以使输入的字符串转换为数字

  ```
  document.getElementById("name").innerHtml="段落已经修改.";
  ```

##### 变量定义

相较于java中，js中的赋值定义比较简单， 

```java
int a = 10;
```

 = 表示赋值 == 表示数值相同时类型可以不同 ===表示类型和值都完全相同

赋值，非强定义类型

```javascript
var a = abc;
a = 100;
a = ture;
a = null;
a = underfind;
a = new object();
```

局部变量和全局变量

```javascript
/*
	全局变量：一直存在浏览器中的内存中，一般尽量使用全局变量
	局部变量:方法开始，函数执行时，执行结束之后为生命周期。声明时候需要使用var 否则直接声明就是全局变量
```

#### Js中的三位运算符

运算的优先级 一元-算数-比较-逻辑

#### Js中的函数定义/Java中的方法

- 函数和方法有共同点就是需要定义然后调用
- Js函数同名后覆盖前
- 函数的定义可以使用=>来进行简写
  - 如果形参只有一个，则小括号可以省略
  - 函数体如果只有一条语句，则花括号可以省略，函数的返回值为该条语句的执行结果
  - 箭头函数 this 指向声明时所在作用域下 this 的值，箭头函数不会更改 this 指向，用来指定回调函数会非常合适
  - 箭头函数不能作为构造函数实例化
  - 不能使用 arguments 实参

##### 在java中的方法定义

```java
/*[修饰符列表]返回值 形式参数列表{
	方法体；
	不为空 则返回值必须对应   
} */
	public static boolean (int a, int b){
		if(a>b){
        	system.out.println("这个是对的");
    		}
        return true;
	}
	
```

##### 在JS中的函数定义

```javascript
/*
	在Js中因为他弱定义的特性所以没有返回值.
	
	function 函数名（形式参数列表）{
		函数体;
		}
	
	函数名 = function(形式参数列表){
		函数体;
		} 							*/
		
	function sum(a,b){
        //a b 都是局部变量
        alert(a+b);
    	}
```

##### Js中的Argments对象

​	动态的数组，可以获取传参中尚未知道的数组数量

​	箭头函数中没有Arguments对象

##### 拓展运算符...arr

`...arr` 语法被称为扩展运算符（Spread Operator）。它允许一个表达式在需要多个参数（用于函数调用）或多个元素（用于数组字面量）或多个变量（用于解构赋值）的地方展开。

##### 定时器间歇函数

作用 重复执行某些代码,函数不用加小括号，返回值是一个id数字

```javascript
//需要使用let来定义不能使用const
//setInterval(函数,间隔时间毫秒)
setInterval(function(){
	console.log()
})
//关闭ClearInertval(变量名)

```

#### 注意事项

switch的结束之后需要添加break 防止穿透

typeof

