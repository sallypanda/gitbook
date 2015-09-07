#第一节课：html5介绍


标签: html5班


##html5简介
简单来说就是超文本标记语言（HTML）的第五次重大修改。
HTML5的设计目的是为了在移动设备上支持多媒体。新的语法特征被引进以支持这一点，`如video`、`audio`和`canvas`标记。

HTML5还引进了新的功能，可以真正改变用户与文档的交互方式。

HTML5 仍处于完善之中。然而，大部分现代浏览器已经具备了某些 HTML5 支持。
##HTML5发展历程
HTML5 是 W3C 与 WHATWG 合作的结果。
1. HTML在1999年12月发布后就停止了更新， 之后W3C 专注于 XHTML 2.0。

2. 为了推动web标准化，一些公司在2004年组织了一个叫WHATWG的组织， 致力于 Web 表单和应用程序。

3. 3.2006 年，双方决定进行合作，来创建一个新版本的 HTML。

4. 2007年W3C接纳WHATWG团队编写的HTML5标准,并成立了新的HTML工作团队。

5. 2008年1月22日，第一份正式草案发布。

6. 2012年12月17日W3C发布了HTML5的“候选推荐规范”，以及HTML5.1的首份规范草案。

7. 2013年5月6日， HTML 5.1 正式草案公布。

8. 2014年10月28日，W3C的HTML工作组正式发布了HTML5的正式推荐标准（W3C Recommendation）


**注:**

W3C    指 World Wide Web Consortium，

    万维网联盟

WHATWG 指 Web Hypertext Application Technology Working Group，

    网页超文本应用技术工作小组。

##HTML5标准文档结构:

```html
<!DOCTYPE HTML>
<html>
	<head>
		<meta charset="utf-8"/>
	</head>
	<body>

	</body>
</html>
```
###说明：
`<!DOCTYPE html>` 文档类型声明
`<meta charset="utf-8"/>`指定文档编码

##HTML5元素的调整:
1. 不允许写结束标记的元素有:`area`、`base`、`br`、`col`、`command`、`embed`、`hr`、`img`、`input`、`keygen`、`link`、`meta`、`param`、`source`、`track`、`wbr`。
2. 可以省略结束标记的元素有:`li`、`dt`、`dd`、`p`、`rt`、`rp`、`optgroup`、`option`、`colgroup`、`thead`、`tbody`、`tfoot`、`tr`、`td`、`th`。
3. 可以省略全部标记的元素有：`html`、`head`、`body`、`colgroup`、`tbody`。虽然标记被省略了，但该元素还是以隐式的方式存在。
4. 具有boolean值的属性
```html
<!-- 只写属性不写属性值代表属性为true -->
<input type="checkbox" checked>
<!-- 不写属性代表属性为false -->
<input type="checkbox">
<!-- 属性值=属性名,代表属性为true -->
<input type="checkbox" checked="checked“>
<!-- 属性值=空字符串，代表属性为true -->
<input type="checkbox" checked="">
```
5. 省略引号
\- 在HTML5中，当属性值不包括空字符串,”<“,">","=",单引号,双引号等字符时，属性值两边的引号可以省略
```
<input type="text">
<input type='text'>
<input type=text>
```

































