# HTML5 十大新特性

> 为 HTML5 建立的一些规则：
> - 新特性应该基于HTML、CSS、DOM 以及 JavaScript；
> - 减少对外部插件的需求（如 Flash）；
> - 更优秀的错误处理；
> - 更多取代脚本的标记；
> - HTML5 应该独立于设备；
> - 开发进程对公众透明；


## 语义标签
可以使开发者更方便清晰构建页面的布局。

| **标签** | **描述** |
| --- | --- |
| `<header>` | 定义文档的头部区域 |
| `<footer>` | 定义文档的尾部区域 |
| `<nav>` | 定义文档的导航 |
| `<section>` | 定义文档章节 |
| `<article>` | 定义文章 |
| `<aside>` | 定义页面意外的内容 |
| `<details>` | 定义用户可以看到的或者额外隐藏的细节 |
| `<summary>` | 标签包含details元素的标题 |
| `<dialog>` | 定义对话框 |
| `<figure>` | 定义自包含内容，如图表 |
| `<main>` | 定义文档主内容 |
| `<mark>` | 定义文档主内容 |
| `<time>` | 定义日期/时间 |


## 增强型表单
html5修改了一些新的input输入特性，改善更好的输入控制验证。

| **输入类型** | **描述** |
| --- | --- |
| color | 主要用于选取颜色 |
| data | 选取日期 |
| datetime | 选取日期（UTC时间） |
| dataime-local | 选取日期（无时区） |
| month | 选择一个月份 |
| week | 选择周和年 |
| time | 选择一个时间 |
| email | 包含e-mail地址的输入域 |
| number | 数值的输入域 |
| url | url地址的输入域 |
| tel | 定义输入电话号码和字段 |
| search | 用于搜索域 |
| range | 一个范围内数字值的输入域 |

### 新增五个表单元素

- datalist：用户会在他们输入数据时看到预定义选项的下拉列表；
- progress：进度条，展示连接/下载进度；
- meter：刻度值，用于某些计量，例如温度、重量等；
- keygen：提供一种验证用户的可靠方法，生成一个公钥和私钥；
- output：用于不同类型的输出；
### 新增表单属性

- placehoder：输入框默认提示文字；
- required：要求输入的内容是否可为空；
- pattern：描述一个正则表达式验证输入的值；
- min/max：设置元素最小/最大值；
- step：为输入域规定合法的数字间隔；
- height/width：用于image类型`<input>`标签图像高度/宽度；
- autofocus：规定在页面加载时，域自动获得焦点；
- multiple：规定`<input>`元素中可选择多个值；

## 视频和音频
html提供了音频和视频文件的标准，即使用 `<audio>` 元素。
```html
<audio controls>	// controls 属性提供添加播放、暂停和音量控件；
  <source src="horse.ogg" type="audio/ogg">
  <source src="horse.mp3" type="audio/mpeg">
  您的浏览器不支持 audio 元素	// 浏览器不支持显示文字；
</audio>

<video width="320" heigth="240" controls>
  <source src="movie.mp4" type="video/mp4">
  <source src="movie.ogg" type="video/ogg">
</video>
```

## Canvas绘图
[https://www.runoob.com/w3cnote/html5-canvas-intro.html](https://www.runoob.com/w3cnote/html5-canvas-intro.html)

## SVG绘图
SVG是可伸缩矢量图形；
SVG用于定义用于网络的基于矢量的图形；
SVG图像在放大或改变尺寸的情况下其图形质量不会有损失；
### SVG的优势

- svg图像可通过文本编译器来创建和修改；
- svg图像可被搜索、索引、脚本化或压缩；
- 可伸缩；
- 放大缩小不失真；
### SVG与Canvas区别
[https://www.w3school.com.cn/html5/html_5_canvas_vs_svg.asp](https://www.w3school.com.cn/html5/html_5_canvas_vs_svg.asp)

- svg适用于描述xml中的2D图形的语言；
- canvas随时随地使用JavaScript绘制2D图形；
svg是基于xml的，可以操作DOM，并为某个元素附加js事件处理器；
- svg每个形状都当作对象，svg改变会引起重绘；
canvas是以像素为单位渲染，改变位置会引起整个场景；
| **Canvas** | **SVG** |
| --- | --- |
| 依赖分辨率 | 不依赖分辨率 |
| 不支持事件处理器 | 支持事件处理器 |
| 能够以 .png 或 .jpg格式保存结果图像 | 复杂度高会减慢渲染速度 |
| 文字呈现功能简单 | 适合大型渲染区域的应用程序 |
| 适合图像密集的游戏，许多对象会被频繁重绘 | 不适合游戏应用 |

## 地理定位
[https://www.w3school.com.cn/html5/html_5_geolocation.asp](https://www.w3school.com.cn/html5/html_5_geolocation.asp)
```html
<script>
  var x=document.getElementById("demo");
  function getLocation() {
    if (navigator.geolocation) {
      navigator.geolocation.getCurrentPosition(showPosition);
    }
    else {
      x.innerHTML="Geolocation is not supported by this browser.";
    }
  }
  function showPosition(position) {
    x.innerHTML="Latitude: " + position.coords.latitude +
    "
Longitude: " + position.coords.longitude;
  }
</script>
```

## 拖放API
拖放是H5标准的一部分
```html
<div draggable="true" ondragstart="drag(event)">给我offer</div>
<script>
  function drag(ev) {
    console.log(ev)
  }
</script>
```
| **拖动生命周期** | **属性名** | **描述** |
| --- | --- | --- |
| 拖动开始 | ondragstart | 拖动开始时执行脚本 |
| 拖动过程 | ondrag | 只要元素正在被拖动就会运行脚本 |
| 拖动过程 | ondragenter | 元素被拖动到一个合法到放置目标时，执行脚本 |
| 拖动过程 | ondragover | 只要元素正在合法到放置目标上拖动时就会执行脚本 |
| 拖动过程 | ondragleave | 当元素离开合法当放置目标是执行脚本 |
| 拖动结束 | ondrop | 将被拖放元素放在目标元素内时运行脚本 |
| 拖动结束 | ondragend | 拖动操作结束时运行脚本 |


## WebWorker
Web worker可以通过加载一个脚本文件，进而创建一个独立工作的线程，在主线程之外运行。
### 基本原理
在当前JavaScript的主线程中，使用Worker类加载一个JavaScript文件来开辟一个新的线程，达到互不阻塞的效果，并提供主线程和新线程之间数据交换的接口：`postMessage、onmessage`
### 使用
```html
<script>
  var worker = new Worker("worker.js"); // 创建 Worker 对象，并向它传递将在新线程中执行的脚本；
  worker.postMessage("hello world");  // 向 worker 发送数据；
  worker.onmessage = function (evt) { // 接收 worker 传来的数据函数
    console.log(evt.data)
  }
</script>
```
```javascript
onmessage = function (evt) {
  var d = evt.data;
  console.log(evt)
  postMessage(123)
}
```

## Web存储
### localStorage方法
用 `localStorage` 方法存储的数据没有时间限制，一段时间后数据依然可用。
```html
<script>
  if (localStorage.pagecount) {
    localStorage.pagecount++
  } else {
    localStorage.pagecount = 1;
  }
  console.log(localStorage);

  document.write(localStorage.pagecount)
</script>
```
### sessionStorage
用 `sessionStorage` 方法针对一个session进行数据存储，当浏览器窗口关闭后，数据会被删除。
```html
<script>
  if (sessionStorage.pagecount) {
    sessionStorage.pagecount++;
  } else {
    sessionStorage.pagecount = 1;
  }
  console.log(sessionStorage)

  document.write(sessionStorage.pagecount)
</script>
```
### *应用程序缓存
HTML5 引入了应用程序缓存，意味着web应用可以进行缓存，并可以在没有因特网连接时进行访问。
应用程序缓存为应用带来三个优势：

- 离线浏览：用户可以在离线时使用他们；
- 速度：一缓存资源加载得更快；
- 减少服务器负载：浏览器将只是从服务器下载更新过或更改过的资源。

[https://www.w3school.com.cn/html5/html_5_app_cache.asp](https://www.w3school.com.cn/html5/html_5_app_cache.asp)

## 服务器发送事件
### WebSocket
##### 是什么
一种基于TCP协议的通讯手段，默认端口80和443，协议标识符是ws（加密为wss），实现了浏览器与服务器的**全双工通信**，扩展了浏览器与服务器的通信功能，使服务器能主动像客户端发送数据，不受跨域限制。
##### 有什么用
用来解决http不能持久连接的问题。双向通信可以实现聊天室等其他需要服务器主动推送的功能。
### EventSource
##### 是什么
官方名称为 Server-sent events（SSE），服务器端派发事件，是基于http协议实现的简单的单项通信，实现了服务器端像客户端推送数据，但客户端不能通过EventSource向服务器发送数据。
##### 有什么用
应用于需要服务器主动推送的功能。实现便捷。
##### WebSocket和EventSource的区别

- WebSocket基于TCP协议，EventSource基于HTTP协议；
- EventSource是单向通信，WebSocket是双向；
- EventSource只能发送文本，WebSocket可以发送二进制数据；
- EventSource相比于WebSocket实现更简单；
- EventSource可以不借助第三方进行自动重连，还具有发送随机事件的能力，而WebSocket需要借助第三方库，如socket.io等；
- WebSocket资源占用过大，而EventSource更轻量；
- WebSocket可以跨域，EventSource基于HTTP，跨域需要服务器端设置请求头；

[https://www.jianshu.com/p/958eba34a5da](https://www.jianshu.com/p/958eba34a5da)

### 参考资料
[HTML5新增标签与删除标签](https://www.cnblogs.com/wn1341/p/6665437.html)
[HTML5新特性总结](https://www.cnblogs.com/binguo666/p/10928907.html)
[HTML5新特性（偏重使用方法）](https://blog.csdn.net/yushuangyushuang/article/details/79177407)
[HTML5 教程——W3school](https://www.w3school.com.cn/html5/index.asp)
