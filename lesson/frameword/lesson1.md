# 第一课：JqueryMobile框架


标签: html5班

[下载地址](http://jquerymobile.com/)

如果说Jquery UI是专注于PC端的表现，则JqueryMobile则是手机端的瑞士军刀。


#hello world！

#Page的概念
>jm框架的基础显示单位叫"page"，也就是我们平时所称的页，它的特别之处在于，jm框架是一个HTML页面，可以包含多个“page”。

###page的定义
```html
<div data-role="page" id="page1">
    <!--我是page1-->
</div>
<div data-role="page" id="page2">
    <!--我是page2-->
</div>
<div data-role="page" id="page3">
    <!--我是page3-->
</div>
```
并且，每一个"page"都需要有一个唯一ID来标识身份


###预加载page
一种是添加`data-prefetch`属性来声明预加载
```html
<a href="1.hello-world.html" data-prefetch="true">我是预加载进来的</a>
```

另一种方式是通过js

```javascript
$(function(){
        $( ":mobile-pagecontainer" ).pagecontainer( "load", "2.single_page.html", { showLoadMsg: false } );
    })
```

###关于page的缓存

>一种方式是通过js设置配置参数
```javascript
$.mobile.page.prototype.options.domCache = true;
```

>另一种是给需要缓存的“page”容器，添加`data-dom-cache="true"`






