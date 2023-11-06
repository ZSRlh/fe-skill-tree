# 一、文档声明
`<!DOCTYPE>` 声明位于文档中最前面的位置，处于 `<html>` 标签之前，**它是声明而非HTML标签**：用来告知Web浏览器页面使用了哪种HTML版本。`<!DOCTYPE>` 标签**没有结束标签，不区分大小写**。

- HTML 4.01 中，`<!DOCTYPE>` 声明需要引用 DTD（文档类型声明），因为HTML 4.01是基于 SGML（Standard Generalized Markup Language 标准通用标记语言），DTD 指定了标记语言的规则，确保浏览器能够解析正群的渲染内容；
   - HTML 4.01 Strict：这个DTD包含所有HTML元素和属性，但不包括表象或过时的元素（如font），不允许框架集；
```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01//EN" "http://www.w3.org/TR/html4/strict.dtd">
```

   - HTML 4.01 Transitional：这个DTD包含所有HTML元素和属性，包括表象或过时的元素（如font），不允许框架集；
```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Transitional//EN" "http://www.w3.org/TR/html4/loose.dtd">
```

   - HTML 4.01 Frameset：这个DTD与Transitional相同，但允许使用框架集内容；
```html
<!DOCTYPE HTML PUBLIC "-//W3C//DTD HTML 4.01 Frameset//EN" "http://www.w3.org/TR/html4/frameset.dtd">
```

- HTML 5 不是基于 SGML，因此不要求引用DTD；
```html
<!DOCTYPE html>
```

# 二、meta标签

**定义和用法：**
`<meta>` 元素可提供有关网页的元信息（meta-information），比如针对搜索引擎和更新频度的描述和关键词；`<meta>` 标签位于文档头部，不包含任何内容，其属性定义了与文档相关联的键值对。

**属性：**

| **属性** | **值** | **描述** |
| --- | --- | --- |
| name | author | 网页的作者 |
|  | description | 告诉搜索引擎 网站的主要内容 |
|  | keywords | 为搜索引擎提供的关键字列表 |
|  | generator | 制作网站使用的编辑器 |
|  | copyright | 版权信息 |
|  | viewport | 优化移动端显示 |
| http-equiv | content-type | 设定页面使用的字符集(h5中可用charset代替) |
|  | expires | 指定网页在缓存中的过期时间 |
|  | refresh | 重定向 |
| content | [content] | 上述属性取值对应的内容 |


**示例：**
```html
<!-- keywords -->
<meta name="keywords" content="程序猿 工程师 程序员">
<!-- description -->
<meta name="description" content="<meta>元素可提供有关网页的元信息（meta-information）">
<!--
 viewport:
 - width：控制viewport的大小，可以设置固定值或特殊值（如：device-width为设备宽度）
 - height：和width相对，指定高度
 - initial-scale：初始缩放比例，页面第一次加载时的缩放比例
 - maximum-scale：允许用户缩放到的最大比例，0-10.0
 - minimum-scale：允许用户缩放到的最小比例，0-10.0
 - user-scalable：用户是否可以手动缩放
 -->
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- expires -->
<meta http-equiv="expires" content="Wed, 26 Feb 1997 08:21:57 GMT"/>
<!-- 
 refresh
 - 5s后重定向到百度页面
-->
<meta http-equiv="refresh"content="5; url=http://www.baidu.com/"/>
<!-- content-Type -->
<meta http-equiv="content-Type" content="text/html;charset=utf-8"/>
<meta charset="utf-8"/>
```


参考文档：
[https://www.w3school.com.cn/tags/tag_doctype.asp](https://www.w3school.com.cn/tags/tag_doctype.asp)
[https://www.w3school.com.cn/tags/tag_meta.asp](https://www.w3school.com.cn/tags/tag_meta.asp)
[https://blog.csdn.net/zhangank/article/details/94014629](https://blog.csdn.net/zhangank/article/details/94014629)
[https://www.cnblogs.com/chuanjian/p/5162185.html](https://www.cnblogs.com/chuanjian/p/5162185.html)

