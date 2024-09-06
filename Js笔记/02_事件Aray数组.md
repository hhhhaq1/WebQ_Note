### Js中的事件和Aray数组

- 获取表单/按钮id
- 定义时间发生时，调用某个函数
- 写出函数具体操作

1. 鼠标事件：
   - click：点击鼠标时触发。
   - dblclick：双击鼠标时触发。
   - mouseover：鼠标移入元素时触发。
   - mouseout：鼠标移出元素时触发。
   - mousedown：鼠标按下时触发。
   - mouseup：鼠标松开时触发。
2. 键盘事件：
   - keydown：按下键盘按键时触发。
     - 回车键值 13
     - ESC键值 27
   - keyup：释放键盘按键时触发。
   - keypress：按下键盘按键并释放时触发。
3. 表单事件：
   - submit：提交表单时触发。
   - change：表单元素的值改变时触发。
   - focus：表单元素获得焦点时触发。
   - blur：表单元素失去焦点时触发。
4. 窗口事件：
   - load：页面加载完成时触发。
   - resize：窗口大小改变时触发。
   - scroll：窗口滚动时触发。
5. 其他事件：
   - load：元素加载完成时触发。
   - error：资源加载失败时触发。

事件的使用方式：

​	事件句柄前加on

回调函数:由自己编写，但是不由自己负责调用，由其他程序负责调用

函数注册到按钮上，等待点击时候调用函数，称之为回调函数



##### Js的函数编写顺序需要注意

页面未加载完成时候，js已经运行，导致显示找不到id为b1的按钮。

```html
<body onload=ready()>
//或者
<script>
window.onload= function(){

}
    </script>
```



##### Js中的控制语句和Java中的类似

```Java
if
switch

while
do...while

for
break
continue
    
 //Java中创建数组
    public class Test{
        public static void main (String[]args){
            int[] arr= {1,2,3,4,5};
            int[] arr2=new int{5}；
            String[] arr3 = {"a";"b";"c"};
            String[] arr4 = new String[3]；
        }
    }

```

##### Aray数组:

一个多条[] 一个多种{}

数组的编号是从0开始的 如一个数组有4个元素 0,1,2,3

在新的ECMA6中可以对数组直接进行简单的解构并且赋值

```javascript
//const用来定义数组和对象等不可修改
const my = {
			name:"lioiu",
			hobby:"吃饭","睡觉","打豆豆"
}
let {name hobby} = my
console.log(name)
consloe.log(hobby)
```



```javascript
  //穿插符号
        var a = new Array(1,2,3,4,5);
        var str = a.join("-");
        alert (str);
        //穿插最后一个数组
        a.push(10);
        alert(a.join("-"));

        //将末尾元素弹出
        var endElt = a.pop();
        alert(endElt);
        alert(a.join("-"));
		//反转数组
        a.reverse();
        alert(a.join("="));
		//删除数组
		//第一个参数：表示开始位置的索引
		//第二个参数：表示要删除的元素数量
		a.splice(1,1)
```

##### 选取随机数的方式

```javascript
function getRandomInt(max){
      return Math.floor(Math.random() * max);
      }
//表示0-4取随机数
let n = getRandomInt(5)
```

