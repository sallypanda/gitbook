# 第一课：canvas画布介绍


标签: html5班

> 如何去创建一个画布：

```html
<canvas id="mycanvas">
已经老掉牙的浏览器，赶紧丢了吧。
</canvas>
```


>通常要设置画布大小，可以这样设置：

```html
<canvas id="mycanvas" width="512" height="480"></canvas>
```
表示画布的分辨率为512x480，
也可以通过JavaScript去控制画布分辨率
```javascript
var myCanvas = document.getElementById("mycanvas");
myCanvas.width=300;
myCanvas.height=300;
```

如果要控制canvas展示大小，可以通过css对其进一步的控制

```css
#mycanvas{
    width:1024px;
    height:960px;
}
```
表示画布展示大小为1024X960PX

>如何去控制canvas呢

```javascript
var myCanvas = document.getElementById("mycanvas");
var context = myCanvas.getContext("2d");
```

我们尝试绘制一个正方形
```javascript
context.fillStyle="red";
context.fillRect(0,0,200,200);
```
