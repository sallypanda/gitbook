#第二节课：html5新增特性


标签: html5班

##HTML5新特性

HTML5 中的一些有趣的新特性：
 - 用于绘画的 canvas 元素

 - 用于媒介回放的 video 和 audio 元素

 - 对本地离线存储的更好的支持

 - 新的特殊内容元素，比如 article、footer、header、nav、section

 - 新的表单控件，比如 calendar、date、time、email、url、search
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

##HTML5新的结构元素

 - article元素
    \- article元素代表文档、页面或应用程序中独立的、完整的、可以独自被外部引用的内容，与上下文不相关的独立内容

 - section元素
    \- section元素表示页面中的一个内容区块，比如章节、页眉、页脚或页面中的其他部分
    \- 不要为没有标题的内容区块使用section元素

 - nav元素
    \- 表示页面中导航链接的部分，例如：传统导航条，侧边栏导航，页内导航，翻页等

 - aside元素
    \- aside元素表示article元素的内容之外的、与article元素的内容相关的辅助信息，它可以包含与当前页面或主要内容相关的引用、侧边栏、广告、导航条，以及其他类似的有别于主要内容的部分

 - header元素
    \- 表示页面中一个内容区块或整个页面的标题

 - hgroup元素
    \- 将标题及其子标题进行分组的元素。hgroup元素通常会将h1-h6元素进行分组，譬如一个内容区块的标题及其子标题算一组。
```html
<hgroup>
<h1>文章主标题</h1>
    <h2>文章子标题</h2>
</hgroup>
```
 - footer元素
    \- 表示整个页面或页面中一个内容区块的脚注。一般来说，它会包含创作者的姓名、创作日期以及创作者联系信息

 - figure元素
    \- 表示一段独立的流内容，一般表示文档主体流内容中的一个独立单元。使用figcaption元素为figure元素组添加标题


##HTML5布局相关注意事项
 - 把新加属性设置为块级元素
```css
article,aside,dialog,figure,footer,headar,legend,nav,section{
    display : block;
}
```
 - 为了兼容旧的IE，需要用js创建标签对象
```html
<script type=“text/javascript”>
    document.createElement("header");
    document.createElement("nav");
    document.createElement("article");
    document.createElement("footer");
    document.createElement("aside");
</script>
```

##html5对于表单的增强
###input标签的增强,新增type属性类型
   1. date - 选取日、月、年
   2. month - 选取月、年
   3. week - 选取周和年
   4. time - 选取时间（小时和分钟）
   5. datetime - 选取时间、日、月、年（UTC 时间）
   6. datetime-local - 选取时间、日、月、年（本地时间）
   7. range－数字范围选择
   8. number－填写数字

###input标签新增属性
 -  autocomplete
autocomplete 属性规定 `form` 或 `input` 域应该拥有自动完成功能。
注释：autocomplete 适用于 `<form>` 标签，以及以下类型的 `<input>` 标签：text, search, url, telephone,email, password, datepickers, range 以及 color。
当用户在自动完成域中开始输入时，浏览器应该在该域中显示填写的选项：
实例
```html
<form action="demo_form.php" method="get" autocomplete="on">
    First name: <input type="text" name="fname" /><br />
    Last name: <input type="text" name="lname" /><br />
    E-mail: <input type="email" name="email" autocomplete="off" /><br />
    <input type="submit" />
</form>
```

-  autofocus
    自动获取焦点
```html
<input type="text" name="fname" autofocus="on"/>
```
- form
form 属性规定输入域所属的一个或多个表单。
注释：form 属性适用于所有 `<input>` 标签的类型。
form 属性必须引用所属表单的 id：
实例
```html
<form action="demo_form.asp" method="get" id="user_form">
First name:<input type="text" name="fname" />
<input type="submit" />
</form>
Last name: <input type="text" name="lname" form="user_form" />
```
- form overrides (formaction, formenctype, formmethod, formnovalidate, formtarget)
表单重写属性（form override attributes）允许您重写 form 元素的某些属性设定。
表单重写属性有：
formaction - 重写表单的 action 属性
formenctype - 重写表单的 enctype 属性
formmethod - 重写表单的 method 属性
formnovalidate - 重写表单的 novalidate 属性
formtarget - 重写表单的 target 属性
注释：表单重写属性适用于以下类型的 `<input>` 标签：submit 和 image。
实例
```html
<form action="form.php" method="get" id="user_form">
    E-mail: <input type="email" name="userid" /><br />
    <input type="submit" value="Submit" />
    <br />
    <input type="submit" formaction="demo_admin.asp" value="Submit as admin" />
    <br />
    <input type="submit" formnovalidate="true" value="Submit without validation" />
</form>
```
- height 和 width
height 和 width 属性规定用于 image 类型的 input 标签的图像高度和宽度。
注释：height 和 width 属性只适用于 image 类型的 `<input>` 标签。
实例
```html
<input type="image" src="img_submit.png" width="100" height="150" />
```
- list
- min, max 和 step
- multiple
- pattern (regexp)
- placeholder
- required
- novalidate
 novalidate 属性规定当提交表单时不对其进行验证。
如果使用该属性，则表单不会验证表单的输入。
注释：`novalidate` 属性适用于：`<form>`，以及以下类型的 `<input>` 标签：text, search, url, telephone, email, password, date pickers, range 以及 color。
```html
<form action="demo_form.php" novalidate="novalidate">
  E-mail: <input type="email" name="user_email" />
  <input type="submit" />
</form>
```
即使邮件格式输入错误，也依然不会有检测信息弹出。





###HTML5 的新的表单元素：
- datalist(兼容性太低)
datalist 元素规定输入域的选项列表。
列表是通过 datalist 内的 option 元素创建的。
如需把 datalist 绑定到输入域，请用输入域的 list 属性引用 datalist 的 id
实例：
```html
Webpage: <input type="url" list="url_list" name="link" />
<datalist id="url_list">
<option label="W3School" value="http://www.W3School.com.cn" />
<option label="Google" value="http://www.google.com" />
<option label="Microsoft" value="http://www.microsoft.com" />
</datalist>
```
- keygen(兼容性太低)
keygen 元素的作用是提供一种验证用户的可靠方法。
keygen 元素是密钥对生成器（key-pair generator）。当提交表单时，会生成两个键，一个是私钥，一个公钥。
私钥（private key）存储于客户端，公钥（public key）则被发送到服务器。公钥可用于之后验证用户的客户端证书（client certificate）。
目前，浏览器对此元素的糟糕的支持度不足以使其成为一种有用的安全标准。
实例
```html
<form action="form.php" method="post">
    Username: <input type="text" name="usr_name" />
    Encryption: <keygen name="security" />
    <input type="submit" />
</form>
```

-  output(兼容性太低)
output 元素用于不同类型的输出，比如计算或脚本输出：
实例
```html
<output id="result" onforminput="resCalc()"></output>
```
































