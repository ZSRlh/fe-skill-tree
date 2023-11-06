# 一、CSS布局的基本单位——Box
Box是CSS布局的基本单位，一个页面就是由多个 Box 组成的。
**元素类型**和** `display` 属性**决定了 Box 的类型，不同的 Box 会参与不同的 `**Formatting Context**`（决定如何渲染文档的容器），因此 Box 内的元素会以不同的方式渲染。

- `block-level box`：    `display` 属性为 `block、list-item、table` 的元素，参与 **`Block Formatting Context`**；
- `inline-level box`：    `display` 属性为 `inline、inline-block、inline-table` 的元素，参与 `**Inline Formatting Context**`；
- `run-in box`：CSS 3 新增；
# 二、BFC 定义
直译为：块级格式化上下文。
它是一个独立的渲染区域，有一套属于自己的渲染规则，规定了内部的 `Block-level Box` 如何布局，且**这个布局区域与外部毫不相关。**
# 三、BFC 布局规则
BFC 是页面上一个隔离的独立容器，容器里面的子元素与外界毫不相干，其布局规则如下：

- 内部的 Box 会在垂直方向依次放置；
- Box 垂直方向的距离由 margin 决定，属于同一个 BFC 的两个相邻 Box 的 margin 会发生重叠；
- 每个元素的 margin box 左边，与包含块 border box 的左边接触，即使存在浮动也是如此；
- BFC 的区域不会与 float box 重叠；
- 计算 BFC 高度时，浮动元素也参与；
- BFC就是页面上的一个隔离的独立容器，容器里面的子元素不会影响到外面的元素，反之亦然。
# 四、触发条件
包含但不限于：

- 根元素：HTML
- 浮动元素：float 值为 left、right
- overflow 值不为visible，为auto、scroll、hidden
- display 值为：inline-block、table-cell、table-caption、table、inline-table、flex、inline-flex、grid、inline-grid
- position 值为 absolute 或 fixed
# 五、应用场景
## 1. 自适应多栏布局
以两栏为例：
```html
<style>
  .aside {
    width: 20vw;
    height: 80vh;
    background-color: seagreen;
    float: left;
  }

  .main {
    height: 100vh;
    background-color: sienna;
  }
</style>

<div class="aside"></div>
<div class="main"></div>
```
效果图：
![image.png](https://cdn.nlark.com/yuque/0/2020/png/1280302/1602039786857-1a14459b-4e0b-4067-bdda-8f7c30bb709b.png#align=left&display=inline&height=377&originHeight=754&originWidth=958&size=17503&status=done&style=none&width=479)
给 `main` 开启 BFC：
```css
.main {
  height: 100vh;
  background-color: sienna;
  overflow: hidden;
}
```
根据规则第4条，效果图：
![image.png](https://cdn.nlark.com/yuque/0/2020/png/1280302/1602039894333-ca4add9e-3b88-4449-b301-b7005a9a0ad1.png#align=left&display=inline&height=377&originHeight=754&originWidth=958&size=17824&status=done&style=none&width=479)
## 2. 高度塌陷（清除内部浮动）
在浮动布局中，父元素的高度默认被子元素撑开，子元素浮动后，由于完全脱离了文档流，因此无法将父元素的高度撑开，导致父元素高度丢失，布局混乱：
```html
<style>
  .father {
    border: 10px solid gold;
  }

  .son {
    height: 200px;
    width: 200px;
    background-color: indianred;
    float: left;
  }
</style>

<div class="father">
  <div class="son"></div>
</div>
```
效果图：
![image.png](https://cdn.nlark.com/yuque/0/2020/png/1280302/1602040330451-9dd20cab-d4c3-47b6-8b1c-daf9c9c4c32a.png#align=left&display=inline&height=221&originHeight=221&originWidth=951&size=5847&status=done&style=none&width=951)
触发 `father` 的 BFC，则在 `div.father` 内部，根据第5条布局规则，父元素高度可以被撑开：
```css
.father {
  border: 10px solid gold;
  overflow: hidden;
}
```
效果图：
![image.png](https://cdn.nlark.com/yuque/0/2020/png/1280302/1602040474251-a2848cd5-9e04-422d-9b53-21ee238c7e5a.png#align=left&display=inline&height=229&originHeight=229&originWidth=950&size=5594&status=done&style=none&width=950)
**更好的一种解决方法**是利用 `clear` 并 给父元素添加**伪类**：
```html
<style>
  .subside::after {
    /* 
    display 设置为 block（table...）后，变为块级元素
    但由于 div.son 的浮动，高度还未被撑开；
    还需清除元素两侧的浮动效果，因此添加 clear: both
    相对完美的解决了高度塌陷的问题
    */
    content: "";
    display: block;
    clear: both;
  }
</style>

<div class="father subside">
  <div class="son"></div>
</div>
```
## 3. 外边距折叠
### （1）子元素越界
```html
<style>
  .father {
    width: 300px;
    height: 300px;
    background-color: hotpink;
  }

  .son {
    height: 100px;
    width: 100px;
    background-color: lightpink;
    margin-top: 100px;
  }
</style>

<div class="father">
  <div class="son"></div>
</div>
```
效果图：
![image.png](https://cdn.nlark.com/yuque/0/2020/png/1280302/1602041357246-22db479c-8358-4073-905a-a9655c5a9da1.png#align=left&display=inline&height=520&originHeight=1039&originWidth=958&size=57122&status=done&style=none&width=479)
利用 BFC 可以解决外边距折叠的问题：
```css
.father {
  width: 300px;
  height: 300px;
  background-color: hotpink;
  overflow: hidden;
}
```
效果图：
![image.png](https://cdn.nlark.com/yuque/0/2020/png/1280302/1602041424207-7928842f-84f6-4116-aaf3-ff40baf21f7a.png#align=left&display=inline&height=520&originHeight=1039&originWidth=958&size=57750&status=done&style=none&width=479)
**更好的解决方法是**给 `div.father` 添加伪类：
```css
  <style>
    .collapsingMargin::before {
      /* 
        相当于给 div.father 前面添加了空的表格元素
        将内外的外边距隔离开
       */
      content: "";
      display: table;
    }
  </style>

  <div class="father collapsingMargin">
    <div class="son"></div>
  </div>
```
### （2）两个相邻元素外边距折叠
```html
<style>
  .up {
    width: 100px;
    height: 100px;
    background-color: lightsalmon;
    margin-bottom: 100px;
  }

  .down {
    width: 100px;
    height: 100px;
    background-color: lightseagreen;
    margin-top: 100px;
  }

</style>
<div class="up"></div>
<div class="down"></div>
```
效果图：
![image.png](https://cdn.nlark.com/yuque/0/2020/png/1280302/1602043076570-93e03807-c5d2-4279-bf2e-a96f69fc919f.png#align=left&display=inline&height=520&originHeight=1039&originWidth=958&size=58265&status=done&style=none&width=479)
给下方元素包裹一层容器，并开启 BFC：
```html
<style>
  .up {
    width: 100px;
    height: 100px;
    background-color: lightsalmon;
    margin-bottom: 100px;
  }

  .down {
    width: 100px;
    height: 100px;
    background-color: lightseagreen;
    margin-top: 100px;
  }

  .out {
    overflow: hidden;
  }

</style>
<div class="up"></div>
<div class="out">
  <div class="down"></div>
</div>
```
效果图：
![image.png](https://cdn.nlark.com/yuque/0/2020/png/1280302/1602043194780-04e4de73-5d13-4b6e-8b86-d04b53d53df6.png#align=left&display=inline&height=520&originHeight=1039&originWidth=958&size=58175&status=done&style=none&width=479)
## _4. 同时解决 高度塌陷 和 外边距折叠_
```css
.clearfix::before,
.clearfix::after {
  content: "";
  display: table;
  clear: both;
}
```

