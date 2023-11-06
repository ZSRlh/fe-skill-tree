# 一、CSS文档引入
## 1. 外部样式表
通过<link>标签引入：
`<link rel="stylesheet" type="text/css" href="sheet.css" media="all">`
属性：

   - rel：关系，指定为 `stylesheet`；
   - type：通过 `link` 标签加载的数据类型；
   - href：样式表的url；
   - media：多媒体描述符；
   - title：用于指定候选样式表。

## 2. 内部样式表
通过 `<style>` 标签引入：`<style type="text/css">...</style>`

## 3. 内联样式表
如果只需要为单个元素提供少量的样式，不值得动用其他样式表，可以直接在html元素的style属性中编写样式：
`<div style="color: red; ..."></div>`

## 4. @import 指令
使用@import指令可以在style标签或.css文档中引入外部样式表：`@import url(style.css) [media]`
使用@import引入的样式表都会使用，无法指定候选样式表。

## 5. HTTP 链接*
可以使用HTTP首部为文档关联CSS样式表。
在Apache中，可以配置.htaccess文件来引用，还可以在服务器的httpd.conf文件中添加规则。

# 二、样式表内容
## 1. 规则结构
## 2. 厂商前缀
| **前缀** | **厂商** |
| --- | --- |
| -epub- | 国际数字出版论坛定制的ePub格式 |
| -moz- | 基于Mozilla的浏览器（如：Firefox） |
| -ms- | 微软Internet Explorer |
| -o- | 基于Opera的浏览器 |
| -webkit- | 基于WebKit的浏览器（如：Safari、Chrome） |


# 三、媒体查询
通过媒体查询来定义浏览器在何种媒体环境中使用指定的样式表。
## 1. 用法

- link 元素的 media 属性；
- style 元素的 media 属性；
- @import 声明的媒体描述符部分；
- @media 声明的媒体描述符部分。

**
**示例：**
```css
@media all {
  h1 {color: maroon;}
  body {background: yellow;}
}
```

## 2. 媒体类型

- all：用于展示所有媒体；
- print：打印预览时使用；
- screen：在屏幕媒体上展示文档时使用，在桌面计算机上运行的所有Web浏览器都是屏幕媒体用户代理。

