# 选择器
CSS选择器是CSS规则的一部分。
它是元素和其他部分组合起来 告诉浏览器哪个HTML元素应当被选为应用规则中的CSS属性 的方式。
> **选择器选择的元素，叫做“选择器的对象”。**


##### 常用的CSS选择器：

- id选择器
- 类选择器
- 标签选择器
- 后代选择器（空格，如：#box div）
- 子选择器 >
- 相邻同胞选择器 +
- 群组选择器 ，

还有一些不太常用：

- 伪类选择器
- 伪元素选择器
- 属性选择器 [attribute]
##### CSS3中新增的选择器

- 层次选择器（p～ul）：选择前面有p的每个ul元素；
- 伪类选择器；
- 属性选择器；
# 优先级
四个权重A、B、C、D：

- A：内联
- B：ID选择器
- C：类、属性、伪类
- D：标签、伪元素
> !important 高于一切，我记得应该是 !important不和其他选择器一起计算，它是在另一个更高的维度上计算。

# 继承属性
在CSS中，继承是指给父级元素设置一些属性，后代元素会自动拥有这些属性。
### 可继承的属性

- 字体系列属性：
   - font
   - font-family
   - font-weight
   - font-size
   - font-style
   - font-variant
- 文本系列属性
   - text-indent
   - text-align
   - line-height
   - word-spacing
   - letter-spacing
   - text-transform
   - direction
   - color
- 元素可见性
   - visibility
- 表格布局属性
   - caption-side
   - border-collapse
   - border-spacing
   - empty-cells
   - table-layout
- 列表属性
   - list-style-type
   - list-style-position
   - list-style
- 引用
   - quotes
- 光标属性
   - cursor
> 特殊的情况：
> - a标签的字体颜色不能被继承；
> - h1-h6标签字体的大小也是不能被继承的；

### 无继承的属性

- display
- 文本属性：vertical-align、text-decoration
- 盒子模型的属性：宽度、高度、内外边距、边框等；
- 背景属性：背景图片、颜色、位置等；
- 定位属性：浮动、清除浮动、定位position等；
- 生成内容属性：content、counter-reset、counter-increment；
- 轮廓样式属性：outline-style、outline-width、outline；
- 页面样式属性：size、page-break-before、page-break-after；

# 参考资料
[JS每日一题——CSS系列 / CSS选择器？优先级？继承？](https://mp.weixin.qq.com/s/hCaRwKswMVdK8ZrYfqcTcA)
