# 欢迎使用 iOS 版 MWeb

MWeb 是专业的 Markdown 写作、记笔记、静态博客生成软件，目前已支持 Mac，iPad 和 iPhone。MWeb 所使用的 Markdown 语法为 Github Flavored Markdown，简称 GFM，这是一种最为广泛使用的 Markdown 语法之一。如果你不知道什么是 Markdown，建议看一下附带的 [Markdown 语法官方说明](Markdown Syntax.md) 文档。GFM 除了支持官方的语法外，还扩展了不少语法。


## iOS 版 MWeb 的主要界面和功能

![mweb-ios-3][image-1]

如上图为 iOS 版 MWeb 的主要界面和功能。需要说明的是，iOS 版本 MWeb 目前仅支持查看、编辑、新增 MWeb for Mac 文档库的文档，管理分类、删除等等都不支持。

## GFM 语法简介和 MWeb 所支持的扩展语法

### 回车转为换行

官方的语法规定结尾加 2 个以上空格加换行才会转成换行，也就是 `<br />` 标签。MWeb 中有个选项可以直接把换行转成 `<br />`，不用加上 2 个以上空格，这个选项默认是开启的。如果要关闭，请在设置页面关闭。

### 任务列表（Task lists）

Markdown 语法：

```
- [ ] 任务一 未做任务 `- + 空格 + [ ]`
- [x] 任务二 已做任务 `- + 空格 + [x]`
```

效果如下：

- [ ] 任务一 未做任务 `- + 空格 + [ ]`
- [x] 任务二 已做任务 `- + 空格 + [x]`

### 图片大小及对齐

官方和 GFM 都不支持图片大小控制及对齐设置，MWeb 引入的特别的语法来设置图片宽度和居左、居右、居中。如：`![图片说明-w450](pic.jpg)` 这样表示设置图片宽度为 450。其中 -w450 为设置语法，生成 HTML 时会自动移除。w 表示设置宽度，居左为：-l400，居右为 -r400，居中为 -c400，比如设置一图片宽度为 500 并居中：`![-c500](pic.jpg)`。 可以看出，MWeb 引入的语法的特点是兼容原来的语法和仅支持设置宽度。

### 多行或者一段代码

Markdown 语法：

	```js
	function fancyAlert(arg) {
	  if(arg) {
	    $.facebox({div:'#foo'})
	  }
	
	}
	```
 
效果如下：

```js
function fancyAlert(arg) {
    if(arg) {
        $.facebox({div:'#foo'})
    }

}
```

这个语法目前在 MWeb 中使用，必须前后空一行，才会正确解析。我觉得，在写 Markdown 文档过程中，运用空行很有必要，基本上，块级元素（标题、列表、引用、代码块、表格、段落等），都建议前后空一行。

### 表格

Markdown 语法：

```
第一格表头 | 第二格表头
--------- | -------------
内容单元格 第一列第一格 | 内容单元格第二列第一格
内容单元格 第一列第二格 多加文字 | 内容单元格第二列第二格
```

效果如下：

第一格表头 | 第二格表头
\--------- | -------------
内容单元格 第一列第一格 | 内容单元格第二列第一格
内容单元格 第一列第二格 多加文字 | 内容单元格第二列第二格


### 删除线

Markdown 语法：

	加删除线像这样用： ~~删除这些~~

效果如下：

加删除线像这样用： \~\~删除这些\~\~

### LaTeX

Markdown 语法：

```
块级公式：
$$  x = \dfrac{-b \pm \sqrt{b^2 - 4ac}}{2a} $$

\\[ \frac{1}{\Bigl(\sqrt{\phi \sqrt{5}}-\phi\Bigr) e^{\frac25 \pi}} =
1+\frac{e^{-2\pi}} {1+\frac{e^{-4\pi}} {1+\frac{e^{-6\pi}}
{1+\frac{e^{-8\pi}} {1+\ldots} } } } \\]

行内公式： $\Gamma(n) = (n-1)!\quad\forall n\in\mathbb N$
```

效果如下（在设置页面中启用 LaTeX 才会看到效果，默认为启用）：

块级公式：
$$  x = \dfrac{-b \pm \sqrt{b^2 - 4ac}}{2a} $$

\\[ \frac{1}{\Bigl(\sqrt{\phi \sqrt{5}}-\phi\Bigr) e^{\frac25 \pi}} =
1+\frac{e^{-2\pi}} {1+\frac{e^{-4\pi}} {1+\frac{e^{-6\pi}}
{1+\frac{e^{-8\pi}} {1+\ldots} } } } \\]


行内公式： $\Gamma(n) = (n-1)!\quad\forall n\in\mathbb N$


### 脚注（Footnote）

Markdown 语法：

```
这是一个脚注：[^sample_footnote]
```

效果如下：

这是一个脚注：[^1]

### 注释和阅读更多

<!-- comment -->
<!-- more -->

**注** 阅读更多的功能只用在文档库生成静态网站或发布到 Wordpress 博客时，插入时注意要后空一行。

### TOC

Markdown 语法：

```
[TOC]
```

效果如下：

[TOC]


[^1]:	这里是脚注信息

[image-1]:	media/mweb-ios-3.png