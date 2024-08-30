## 概念

1.一个静态模块（html，css， js，图片等固定内容的文件）打包工具，从入口构建依赖图，打包有关的模块，最后用于展示你的内容 默认只识别 JS 和 JSON 文件内容

*只有和入口有直接/间接引入关系的模块，才会被打包*

##### 重点

2.Webpack 的作用：把静态模块内容，压缩，这个和，转译等（前端工程化）

* 把 less/sass 转成 css 代码
* 把 ES6+ 降级成 ES5 等
* 支持多种模块文件类型，多种模块标准语法
* 初级的webpack打包之后需要将新导出的js文件导入到旧html中，并不会重新生成html

3.通常的打包过程

```
a.初始化node环境   npm init -y
b.创建需要打包的文件
c.安装webpack（独立因为不同项目需要使用的版本不同）
	npm i webpack webpack-cli --save-dev
d.在package.json的scripts中插入命令:
	 "build":"webpack"
e.npm run build //会将文件打包到dist文件夹中
```

4.可以通过新建配置文件来影响webpack的打包过程

- 项目根目录，新建 Webpack.config.js 配置文件

- 导出配置对象，配置入口，出口文件路径（别忘了修改磁盘文件夹和文件的名字）

  ```javascript
  const path = require('path')
  
  module.exports = {
    entry: path.resolve(__dirname, 'src/login/index.js'),
    output: {
      path: path.resolve(__dirname, 'dist'),
      filename: './login/index.js'  
    }
  }
  ```

- 重新打包观察

### WebPack插件

##### 打包HTML

- html-webpack-plugin ：打包时生成 html 文件，并引入其他打包后的资源

  ```
  1. 1. 下载 html-webpack-plugin 本地软件包到项目中
  
        ```bash
        npm i html-webpack-plugin --save-dev
        ```
  
     2. 配置 webpack.config.js 让 Webpack 拥有插件功能
  
        ```js
        // ...
        const HtmlWebpackPlugin = require('html-webpack-plugin')
        
        module.exports = {
          // ...
          plugins: [
            new HtmlWebpackPlugin({
              template: './public/login.html', // 模板文件
              filename: './login/index.html' // 输出文件
            })
          ]
        }
        ```
  
     3. 指定以 public/login.html 为模板复制到 dist/login/index.html，并自动引入其他打包后资源
  
  2. 运行打包命令，观察打包后 dist 文件夹下内容并运行查看效果
  
  
  ```

  ##### 打包CSS	

-  mini-css-extract-plugin ：让 webpack 把 css 代码内容字符串单独提取到 dist 下的 css 文件

  ```
  1. 下载 mini-css-extract-plugin 插件软件包到本地项目中
  
     ```bash
     npm i --save-dev mini-css-extract-plugin
     ```
  
  2. 配置 webpack.config.js 让 Webpack 拥有该插件功能
  
     ```js
     // ...
     const MiniCssExtractPlugin = require("mini-css-extract-plugin")
     
     module.exports = {
       // ...
       module: {
         rules: [
           {
             test: /\.css$/i,
             // use: ['style-loader', 'css-loader']
             use: [MiniCssExtractPlugin.loader, "css-loader"],
           },
         ],
       },
       plugins: [
         // ...
         new MiniCssExtractPlugin()
       ]
     };
     ```
  
  3. 打包后观察效果
  
  4. 注意：不能和 style-loader 一起使用
  
  5. 好处：css 文件可以被浏览器缓存，减少 JS 文件体积，让浏览器并行下载 css 和 js 文件
  ```

  ##### 通过配置打包图片

```
1. [资源模块](https://webpack.docschina.org/guides/asset-modules/)：Webpack 内置了资源模块的打包，无需下载额外 loader 

2. 步骤：

   1. 配置 webpack.config.js 让 Webpack 拥有打包图片功能

      占位符 【hash】对模块内容做算法计算，得到映射的数字字母组合的字符串

      占位符 【ext】使用当前模块原本的占位符，例如：.png / .jpg 等字符串

      占位符 【query】保留引入文件时代码中查询参数（只有 URL 下生效）

      

   2. 注意：判断临界值默认为 8KB

      大于 8KB 文件：发送一个单独的文件并导出 URL 地址

      小于 8KB 文件：导出一个 data URI（base64字符串）

   3. 在 src/login/index.js 中给 img 标签添加 logo 图片

      ```js
      /**
       * 目标9：打包资源模块（图片处理）
       *  9.1 创建 img 标签并动态添加到页面，配置 webpack.config.js
       *  9.2 打包后观察效果和区别
       */
      // 9.1 创建 img 标签并动态添加到页面，配置 webpack.config.js
      // 注意：js 中引入本地图片资源要用 import 方式（如果是网络图片http地址，字符串可以直接写）
      import imgObj from './assets/logo.png'
      const theImg = document.createElement('img')
      theImg.src = imgObj
      document.querySelector('.login-wrap').appendChild(theImg)
      ```

   4. 配置 webpack.config.js 让 Webpack 拥有打包图片功能

      ```js
      // ...
      
      module.exports = {
        // ...
        module: {
          rules: [
            // ...
            {
              test: /\.(png|jpg|jpeg|gif)$/i,
              type: 'asset',
              generator: {
                filename: 'assets/[hash][ext][query]'
              }
            }
          ]
        }
      }
      ```

   5. 打包后运行观察效果


```

