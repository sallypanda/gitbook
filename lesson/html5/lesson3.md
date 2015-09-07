#第三节课：html5本地存储


标签: html5班

##HTML的web存储方法
HTML5 提供两种web存储方法，localStorage 与 sessionStorage

localStorage 与 sessionStorage 区别
localStorage没有过期时间，只要不clear或remove，数据会一直保存。
sessionStorage 针对一个session进行数据存储，生命周期与session相同，当用户关闭浏览器后，数据将被删除。

##两者特点：
localStorage和sessionStorage都具有相同的操作方法，例如setItem、getItem和removeItem等

##localStorage和sessionStorage的方法
- setItem存储value
用途：将value存储到key字段
用法：.setItem( key, value)
代码示例：
```javascript
sessionStorage.setItem("key", "value");
localStorage.setItem("site", "js8.in");
```
- getItem获取value
用途：获取指定key本地存储的值
用法：.getItem(key)
代码示例：
```javascript
var value = sessionStorage.getItem("key");
var site = localStorage.getItem("site");
```
- removeItem删除key
用途：删除指定key本地存储的值
用法：.removeItem(key)
代码示例：
```javascript
sessionStorage.removeItem("key");
localStorage.removeItem("site");
```
- clear清除所有的key/value
用途：清除所有的key/value
用法：.clear()
代码示例：
```javascript
sessionStorage.clear();
localStorage.clear();
```


其他操作方法：点操作和[]
web Storage不但可以用自身的setItem,getItem等方便存取，也可以像普通对象一样用点(.)操作符，及[]的方式进行数据存储，像如下的代码：
```javascript
var storage = window.localStorage;
storage.key1 = "hello";
storage["key2"] = "world";
console.log(storage.key1);
console.log(storage["key2"]);
```
localStorage和sessionStorage的key和length属性实现遍历
sessionStorage和localStorage提供的key()和length可以方便的实现存储的数据遍历，例如下面的代码：
```javascript
var storage = window.localStorage;
for (var i=0, len = storage.length; i  <  len; i++){
    var key = storage.key(i);
    var value = storage.getItem(key);
    console.log(key + "=" + value);
}
```
4.如果要保存非字符串的内容，建议使用JSON来处理。

写入数据时用JSON.stringify转成字符串
```javascript
var data = {a:1,b:2,c:3};
localStorage.setItem("data",JSON.stringify(data));
```

读取数据时用JSON.parse把字符串转为之前的格式。
```javascript
var JasonString =localStorage.getItem("data");
console.log(JSON.parse(JasonString));
```
- storage事件
storage还提供了storage事件，当键值改变或者clear的时候，就可以触发storage事件，如下面的代码就添加了一个storage事件改变的监听：

```javascript
//可以通过添加storage侦听，来监测本地存储数据的变化
	if(window.addEventListener){
		window.addEventListener("storage",handle_storage,false);
	}else if(window.attachEvent){
		window.attachEvent("onstorage",handle_storage);
	}
	function handle_storage(e){
		if(!e){e=window.event;}
		var status = {};
	    status.key = event.key;
	    status.oldValue = event.oldValue;
	    status.newValue = event.newValue;
	    status.url = event.url;
	    status.storage = event.storageArea;
	  	console.log(status);
	}

```
- storage事件对象的具体属性如下表：

    - storageArea: 表示存储类型（Session或Local）
    - key:发生改变项的key
    - oldValue: key的原值
    - newValue: key的新值
    - url*: key改变发生的URL



>**PS:**

>1.注意: url 属性早期的规范中为uri属性。有些浏览器发布较早，没有包含这一变更。为兼容性考虑，使用url属性前，你应该先检查它是否存在，如果没有url属性，则应该使用uri属性。

>2.如果调用clear()方法，那么key、oldValue和newValue都会被设置为null。

>3.在静态页面(以file:///"形式)下web storage会失效,必须运用服务器来访问(以http://localhost:8080/...)。

>4.协议 + 域名 + 端口 一样才能算同一起源。
