
## 面试题整理：


### 对WEB标准以及W3C的理解与认识

	标签闭合    标签小写    不乱嵌套  使用外连 css 和 js 脚本  结构行为表现的分离    容易维护和改版  

### XHTML 和 html 的区别

	html  是一种基本的 web 网页设计语言 xhtml  是一个基于xml的置标语言
	主要区别： XHTML 元素必须正确的嵌套  元素必须闭合 标签必须小写 文档必须有根元素

### 如何触发 Doctype 的严格模式和混杂，模式

	用于声明文档使用哪种规范（html/zhtml）一般为 严格 过度 基于框架的html文档

### 前端页面有哪三层

	结构层html   表现层css   行为层js

### 一般测试浏览器都有哪些，内核

	Ie（Trident）   火狐（Gecko）   谷歌（webkit）   opear（Blink）  Chrome（blink）

### css reset 的作用和用途。

	Reset重置浏览器的 css 默认属性，浏览器的品种不同，样式不同，然后重置，让他们统一

### css sprites(精灵图) 如何使用。

	Css 精灵 把一堆小的图片整合到一张大的图片上，减轻服务器对图片的请求数量

#### 你如何对网站的文件和资源进行优化?期待的解决方案包括

	文件合并   文件最小化/压缩文件   使用CDN托管   缓存使用

###什么是标签语义化

	直观的认识标签   对搜索引擎的抓取有好处

### 清除浮动的几种方式

	1.使用空标签清除浮动。 clear:both   
	2.使用overflow:auto（使用zoom:1用于兼容IE）。   
	3.是用afert伪元素清除浮动(用于非IE浏览器) 。  

### javascript 的 typeof 返回那些数字类型

	object   number   function   boolean   undefined

### 举例隐式类型转换和强制类型转换

	强制（parseInt、parseFloat、number）
	隐式（==、-、===）

### split()与jion()区别

	split（切割成数组形式）   jion（讲数组转换成字符串）

### 举例数组的方法
	
	push尾部添加   pop尾部删除   Unshift头部添加   shift头部删除

### call 和 apply 区别

	object.call(this,obj1,obj2...)   
	onject.apply(this,arguments)

### ajax 请求数据，如何解析json数据

	eval   parse  鉴于安全，parse更靠谱

### 什么是事件委托
	
	利用冒泡事件的原理。让自己的所触发的事件，让他的父元素代替执行

### 什么是闭包

	闭包就是能够读取其他函数内部变量的函数

### 添加、  删除、  出入  替换、  创建节点

	添obj.appendChild()、   删obj.innerseBefore()、   替obj.replaceChild()、   插obj.removeChild()、
	创建具体元素createElement()、   
	创建文本节点createTextNode()
### javascript的本地对象，内置对象和宿主对象

	本地对象： array、 obj、regexp、 等可以 new 实现实例化。    
	内置对象： gload、 Math 等不可以实例化。   
	宿主对象： 浏览器自带的 document、 window 等。
	
### “==”和“===”的不同

	前置会自动转换类型

### document load 和document ready的区别

	Document.onload 是在结构和样式加载完才执行js。   
	Document.ready原生种没有这个方法，jquery中有 $().ready(function)。

### javascript的typeof返回哪些数据类型

	基本数据类型：string、boolean、number、undefined、null、object。   
	引用数据类型：object
	、data、regexp、function。

### Javascript的事件流模型都有什么？

	事件冒泡：事件开始由最具体的元素接受，然后逐级向上传播。   
	事件捕获：事件由最不具体的节点先接收，然后逐级乡下，一直到最具体的。

### http://item.taobao.com/item.htm?a=1&b=2&c=&d=xxx&e，
请写一段JS程序提取URL中的各个GET参数(参数名和 参数个数不确定)，将其按key-value形式返回到一个json结构中，如{a:'1′, b:′2′ , c:′′, d:′xxx′, e:undefined}

	function serilizeUrl(url) {
 		var result = {};
 		url = url.split("?")[1];
		var map = url.split("&");
		for(var i = 0, len = map.length; i < len; i++) {
 			result[map[i].split("=")[0]] = map[i].split("=")[1];
	 	}
		return result;
	}

### 给String对象添加一个方法，传入一个string类型的参数，然后将string的每个字符间加个空格返回，例如：
addSpace(“hello world”) // -> ‘h e l l o  w o r l d’

	String.prototype.spacify = function(){
      	return this.split('').join(' ');
    };

### foo = foo||bar ，这行代码是什么意思？为什么要这样写？

	if(!foo) foo = bar; //如果foo存在，值不变，否则把bar的值赋给foo。

### 写一个function，清除字符串前后的空格。（兼容所有浏览器）

	if (!String.prototype.trim) { 
		String.prototype.trim = function() { 
			return this.replace(/^\s+/, "").replace(/\s+$/,"");
 		} 
 	} 

 	// test the function 
 	var str = " \t\n test string ".trim(); 
 	alert(str == "test string"); // alerts "true"

### Null和Undefined有和区别与联系

	null :表示无值;   
	undefined : 表示一个未声明的变量，或已声明但没有赋值的变量，或一个并不存在的对象属性。

### 每个HTML文件里开头都有个很重要的东西，Doctype，知道这是干什么的吗

	<!DOCTYPE> 声明位于文档中的最前面的位置，处于 <html> 标签之前。此标签可告知浏览器文档使用哪种 HTML 或 XHTML 规范。（重点：告诉浏览器按照何种规范解析页面）

### div+css的布局较table布局有什么优点？

	改版的时候更方便 只要改css文件。
	页面加载速度更快、结构化清晰、页面显示简洁。
	表现与结构相分离。
	易于优化（seo）搜索引擎更友好，排名更容易靠前。

###	6.	你能描述一下渐进增强和优雅降级之间的不同吗?

	渐进增强: progressive enhancement：针对低版本浏览器进行构建页面，保证最基本的功能，然后再针对高级浏览器进行效果、交互等改进和追加功能达到更好的用户体验。
	优雅降级: graceful degradation：一开始就构建完整的功能，然后再针对低版本浏览器进行兼容。

### 为什么利用多个域名来存储网站资源会更有效

	CDN缓存更方便、
	突破浏览器并发限制、
	节约cookie宽带、
	节约主域名的链接数，优化页面响应速度、
	防止不必的安全问题

### 简述一下src与href的区别

	src 用于替换当前元素，herf用于在当前文档和引用资源之间确立联系。
	src是source的缩写，指向外部资源的位置，在请求src资源时会将其指向的资源下载并应用到文档内。
	<script src =”js.js”></script>
	当浏览器解析到该元素时，会暂停其他资源的下载和处理，直到将该资源加载、编译、执行完毕，图片和框架等元素也如此，类似于将所指向资源嵌入当前标签内。这也是为什么将js脚本放在底部而不是头部。
	href是Hypertext Reference的缩写，指向网络资源所在位置，建立和当前元素（锚点）或当前文档（链接）之间的链接，如果我们在文档中添加。
	<link href=”common.css” rel=”stylesheet”/>。
	那么浏览器会识别该文档为css文件，就会并行下载资源并且不会停止对当前文档的处理。这也是为什么建议使用link方式来加载css，而不是使用@import方式。

### 知道的网页制作会用到的图片格式有哪些？

	png-8，png-24，jpeg，gif，svg。   
	科普一下Webp：WebP格式，谷歌（google）开发的一种旨在加快图片加载速度的图片格式。在质量相同的情况下，WebP格式图像的体积要比JPEG格式图像小40%。

### 13.	在css/js代码上线之后开发人员经常会优化性能，从用户刷新网页开始，一次js请求一般情况下有哪些地方会有缓存处理？

	dns缓存，cdn缓存，浏览器缓存，服务器缓存。

### 浏览器默认的天生的inline-black元素都有哪些
	
	input、img、button、texterea、label

### rgba()和opacity的透明效果有什么不同

	rgba()和opacity都能实现透明效果，但最大的不同是opacity作用于元素，以及元素内的所有内容的透明度。
	而rgba()只作用于元素的颜色或其背景色。（设置rgba透明的元素的子元素不会继承透明效果！）。

### Sass、LESS是什么？大家为什么要使用他们？

	Less是一种动态样式语言. 将CSS赋予了动态语言的特性，如变量，继承，运算， 函数. LESS 既可以在客户端上运行 (支持IE 6+, Webkit, Firefox)，也可一在服务端运行 (借助 Node.js)。  
	结构清晰，便于扩展。

### display:none与visibility:hidden的区别是什么？
	
	display : 隐藏对应的元素但不挤占该元素原来的空间。
	visibility: 隐藏对应的元素并且挤占该元素原来的空间。

### CSS中link和@import的区别是：

	Link属于html标签，而@import是CSS中提供的
	在页面加载的时候，link会同时被加载，而@import引用的CSS会在页面加载完成后才会加载引用的CSS。
	Link引入样式的权重大于@import的引用。

### BFC是什么

	BFC（块级格式化上下文）是指浏览器中创建了一个独立的渲染区域，该区域内所有元素的布局不会影响到区域外元素的布局，这个渲染区域只对块级元素起作用。

### Doctype的作用？严格模式与混杂模式的区别？

	<!DOCTYPE>用于告知浏览器该以何种模式来渲染文档。
	严格模式下：页面排版及JS解析是以该浏览器支持的最高标准来执行。
	混杂模式：不严格按照标准执行，主要用来兼容旧的浏览器，向后兼容。

### 40.	对WEB标准以及W3C的理解与认识

	标签闭合、标签小写、不乱嵌套、提高搜索机器人搜索几率、使用外 链css和js脚本、结构行为表现的分离、文件下载与页面速度更快、内容能被更多的用户所访问、内容能被更广泛的设备所访问、更少的代码和组件，容易维 护、改版方便，不需要变动页面内容、提供打印版本而不需要复制内容、提高网站易用性。



	wzm224@163.com
