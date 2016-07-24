# sunopar's world

## 技术栈

### 工程化工具

- [npm](https://www.npmjs.com/)

包管理
- [webpack](https://github.com/webpack/webpack)

1. 使用CommonJS和ES6混合的模块化加载方案
2. 对图片等较小的资源进行base64转码
3. 对于文件的更新采用hash码

### 前端

- [Bootstrap](http://www.bootcss.com/)
- [jQuery](http://jquery.com/)
- [Vue](http://vuejs.org.cn/)
- [Vue-router](https://github.com/vuejs/vue-router)---路由管理
- [Vue-source](https://github.com/vuejs/vue-resource)---Ajax管理
- [SASS](http://www.w3cplus.com/sassguide/)
- [ES6](http://www.es6js.com/)---使用bebel编译

###后端：

- [Node](http://nodejs.cn/)
- [MongoDB](https://www.mongodb.com/)

## 前端详解

### Direcotry
```
|- bin ------webpack打包后的路径
|- src ------本地资源路径，也就是你写代码的地方
  |- components ------存放你的vue组件
  |- lib ------存放你的第三方非npm下的插件,及公共资源
  |- App.vue ------整个vue入口
  |- main.js ------整个页面的入口
|- data 页面存放的json数据
|- webpack.config.js ------webpack配置文件
|- package.json ------项目说明，module等的配置文件
|- index.html ------项目页面
```
### software

- [Git for windows](https://git-scm.com/download/win)
- [nodejs](http://nodejs.cn/download/)
- [sublime](http://www.sublimetext.com/3)
- [ruby](https://www.ruby-lang.org/zh_cn/downloads/)

### npm&webpack config
npm
主要是模块的管理和一些命令的集成(dev&build)

webpack.config.js

- loader:
 - vue:load vue
 - raw:load html
 - babel:load es6
 - flie-loader&url-loader:load images
- external:
extract third party by `<link>` or `<script>`
- devtool:
source-map
- plugin:
 - HtmlWebpackPlugin:creation of HTML files to serve your webpack bundles
 - ExtractTextPlugin:move every stylesheet into a separate css output files
 - CommonsChunkPlugin:Split your commons code into vendor and application

更多详情可以看我的`webpack.config.js`文件。
### 页面分析

components目前分为
```
|- header ---头部
|- content ----主体
  |- banner ---- 首页内容
  |- blog ---- 博客
  |- about ----about页面
```
banner，gallery，blog的配置使用vue-router配置

**example：**
```
// 路由map
router.map({
	'/':{
		component:banner
		},
	'/gallery':{
		component:gallery
	}
	
})
router.start(App,'app')
```

