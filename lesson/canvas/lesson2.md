# 第二课：canvas基础绘图


标签: html5班

`<canvas>`是HTML5的新标签，通常和Script（一般是Javascript）结合来画图，合成图像，制作动画等。

 - Canvas的属性：`width`和`height`
 - 获取canvas对象：

```javascript
document.getElementById()
```
 - 获取canvas上下文（内容）：

```javascript
var ctx = canvas.getContext('2d');
```

 - 判断浏览器兼容：
```javascript
var canvas = document.getElementById('myCanvasßßß');
if (canvas.getContext){
  var ctx = canvas.getContext('2d');
  // drawing code here
} else {
  // canvas-unsupported code here
}
```

- 画线
```javascript

```

- 绘制矩形
    - 实心矩形

            ctx.rect(0,0,200,200);
	        ctx.fillStyle="#ff0000";
	        ctx.fill();
        或

            ctx.fillStyle="#ff0000";
            ctx.fillRect(0,0,200,200);

        以上两段代码作用是等价的。

    - 空心矩形

            ctx.rect(201,201,200,200);
	        ctx.fillStyle="#ff0000";
	        ctx.stroke();
        或

        	ctx.fillStyle = "#000000";
	        ctx.strokeRect(201,201,200,200);

        以上两段代码作用是等价的。


 - 绘制圆形



 - 绘制线条
