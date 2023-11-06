元素类型可以通过css中display属性修改。
# 一、行内元素（inline-element）

- b，big，i，small，tt
- abbr，cite，code，dfn，em，kbd，strong，samp，var
- a，bdo，br，map，object，q，script，span，sub，sup
- button(display: inline-block)，input，label，select，textarea

**块元素特点：**

- 不能独占一行；
- 设置width、height无效，margin上下无效，padding有效；
- 宽度是它的文字、图片的宽度，不可改变；
- 只能容纳文本或者其他内联元素；
# 二、块元素（block-element）
| <address> | 联系方式信息 | <article> | 文章内容 | <aside> | 伴随内容 |
| --- | --- | --- | --- | --- | --- |
| <audio> | 音频播放 | <blockquote> | 块引用 | <canvas> | 绘制图形 |
| <dd> | 列表条目描述 | <div> | 文档分区 | <dl> | 定义列表 |
| <fieldset> | 表单元素分组 | <figcaption> | 图文信息组标题 | <figure> | 图文信息组 |
| <footer> | 页尾 | <form> | 表单 | <h1-h6> | 标题级别 |
| <header> | 页头 | <hgroup> | 标题组 | <hr> | 水平分割线 |
| <noscript> | 不支持/禁用脚本 | <ol> | 有序列表 | <output> | 表单输出 |
| <p> | 行 | <pre> | 预格式化文本 | <section> | 区段 |
| <table> | 表格 | <tfoot> | 表脚注 | <ul> | 无序列表 |
| <video> | 视频 |  |  |  |  |

**块元素特点：**

- 每个块元素都从新的一行开始，其后的元素另起一行；
- 宽高、内外边距都可控；
- 宽度默认为其容器的100%；
- 可容纳内联元素和其他块元素；

# 三、替换元素
替换元素是浏览器根据其标签的**元素与属性**来判断其显示具体的内容。

典型的替换元素有：<img>、<input>、<textarea>、<select>、<object>、表单元素；某些元素只在特殊的情况下表现为而可替换元素，例如：<audio>、<canvas>

一般替换元素有内在尺寸，默认宽高为其内置尺寸。
# 四、内联级块元素
同时具备内联元素和块元素的特点，display: inline-block；<img>、<input>就是这种内联块状标签；

# 五、空元素
没有内容的HTML元素：<br>、<hr>、<img>、<input>、<link>、<meta>


