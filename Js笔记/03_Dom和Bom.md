# Dom

- DOM（**Document Object Model ，文档对象模型**）一种独立于语言，**用于操作xml，html文档**的**应用编程接口**。也可以叫方法

- 获取文档中特定id的元素

  ```javascript
  doucment.getElementByid("")
  ```

- 获取文档中匹配指定 CSS 选择器的一个元素

  ```javascript
  document.querySelector("#demo");
  doucment.querySelectorAll() ;//获取所有元素
  ```

- html中常常使用data- 来表示元素的自定义属性

  ```html
   <div data-sm="qqe">1</div>
    <script>
      //获取第一个div元素
      const app = document.querySelector('div')
      //获取自定义html属性
      console.log(app.dataset.sm)
    </script>
  ```

  

​		

