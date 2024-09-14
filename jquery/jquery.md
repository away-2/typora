## 一、DOM操作

**dom 对象转化为 jQuery 对象： $( DOM 对象 ) 就可以转换成为 jQuery 对象**

**jQuery 对象转为 dom 对象 jQuery 对象[下标]取出相应的 DOM 对象**

#### 1.DOM属性操作

- `html()` 它可以设置和获取起始标签和结束标签中的内容。 跟 DOM 属性 `innerHTML` 一样。

- `text()` 它可以设置和获取起始标签和结束标签中的文本。  跟 DOM 属性 `innerText` 一样。

- `val()` 它可以设置和获取表单项的 value 属性值。 跟 DOM 属性 `value` 一样。

  例子：

  ```javascript
    <body>
      <div id="box">
        <h1>Hello World!</h1>
        <p>这是p标签</p>
      </div>
      <div class="form">
          <label class="radio_box">
              <input type="radio" value="111" />
              <span></span>
              <span>111</span>
          </label>
          <label class="radio_box">
              <input type="radio" value="222" />
              <span></span>
              <span>222</span>
          </label>
      </div>
    </body>
    <script>
      console.log($("#box").html());  // <h1>Hello World!</h1>  <p>这是p标签</p>
  	console.log($("#box").text()); 	//  Hello World!  这是p标签
   	console.log($(":radio").val());  // 111
   $("#box").html(`<h2>Hello World!</h2>
        <p>这是标签</p>`)   // 直接改变原有html结构
   $("#box h1").text("改变原有text")  
    </script>
  ```

- `attr()` 可以设置和获取属性的值，不推荐操作 checked、readOnly、selected、disabled 等等 ； attr 方法还可以操作非标准的属性。比如自定义属性:abc，edf。

- `removeAttr('xxx')` 移除xxx属性值。

- `prop()` 可以设置和获取属性的值,只推荐操作 checked、readOnly、selected、disabled 等等。

- `removeProp('xxx')` 移除xxx属性值。

例子：

```javascript
  <body>
    <div id="box" data-id="test">
      <h1>Hello World!</h1>
      <p>这是p标签</p>
    </div>
    <div class="form">
        <label class="radio_box">
            <input type="radio" value="111"  />
            <span></span>
            <span>111</span>
        </label>
        <label class="radio_box">
            <input type="radio" value="222" />
            <span></span>
            <span>222</span>
        </label>
    </div>
  </body>
  <script>
    let box = $("#box");
    console.log(box.attr("data-id"));  // test
 	box.attr("data-id","change");   // box中data-id属性值已由test改变为change
    box.removeAttr("data-id");  // html结构中data-id属性已去除
 	console.log(box.prop("data-id"));   // undefined
	console.log($(":radio").prop("value"));   //  111

  </script>
```



#### 2. attr()和prop()的区别：

当取得checked属性的值时，如果checked属性设置了，attr()会返回checked，prop()会返回true，属性没有设置，attr()会返回undefined，prop()会返回false，undefined到底是什么呢，官方觉得返回undefined是一个错误，所以我们在操作checked属性时，应该使用prop()方法。 同理readOnly、selected、disabled 等等属性与checked是一样的，对它们进行操作时应该使用prop()方法。

```javascript
  <body>
    <div class="form">
        <label class="radio_box">
            <input type="radio" value="111" checked />
            <span></span>
            <span>111</span>
        </label>
        <label class="radio_box">
            <input type="radio" value="222" />
            <span></span>
            <span>222</span>
        </label>
    </div>
  </body>
  <script>
    console.log($(":radio").attr("checked"));  // checked
    console.log($(":radio").prop("checked"));  // true
	console.log($(":radio:last").attr("checked"));   // undefined
     console.log($(":radio:last").prop("checked"));  // false
  </script>
```



#### 3.DOM的增删改

**after():添加元素到元素后边**

- 对象1.after(对象2)： 将对象2添加到对象1后边。对象1和对象2是兄弟关系

**before():添加元素到元素前边**

- 对象1.before(对象2)： 将对象2添加到对象1前边。对象1和对象2是兄弟关系

**append():父元素将子元素追加到末尾**

- 对象1.append(对象2): 将对象2添加到对象1元素内部，并且在末尾

**prepend():父元素将子元素追加到开头**

- 对象1.prepend(对象2):将对象2添加到对象1元素内部，并且在开头

**内部插入：**

- `appendTo()` ，如a.appendTo(b) 把 a 插入到 b 子元素末尾，成为最后一个子元素
- `prependTo()`，如a.prependTo(b) 把 a 插到 b 所有子元素前面，成为第一个子元素

**外部插入:**

- `insertAfter()` ，如a.insertAfter(b) 得到 ba
- `insertBefore()`，如a.insertBefore(b) 得到 ab

**替换:**

- `replaceWith()`， 如a.replaceWith(b) 用 b 替换掉 a，注意这里是用 b 替换掉 a
- `replaceAll()`，如a.replaceAll(b) 用 a 替换掉所有 b

**删除:**

- `remove()` ，如a.remove(); 删除 a 标签
- `empty()` ，如 a.empty();清空 a 标签里的内容

## 二、CSS样式操作

#### 1.CSS方法

`css()` 读取或写入匹配元素的样式属性

`addClass()` 为元素添加一个或多个class值

`removeClass()` 删除样式，删除元素的class值；传递一个或多个具体的class值，就会删除具体的某个或多个class；不传值就是移除所有的class值。

`toggleClass()` 对被选元素进行添加/删除类的切换操作， 切换就是如果具有该类那么删除，如果没有那么添加上

`offset()` 获取和设置元素的坐标。

例子：

```javascript
a.css('color') //取出a元素的color
a.css('color',"red") //设置a元素的color为red
//实战演示
//addClass() - 向被选元素添加一个或多个类，下述示例添加多个
$('div:first').addClass("redDiv blackDiv");
//removeClass() - 从被选元素删除一个或多个类 ，下述示例删除多个，也就是所有class
$('div:first').removeClass();
//toggleClass() - 对被选元素进行添加/删除类的切换操作 ,切换就是如果具有该类那么删除，如果没有那么添加上
$('div:first').toggleClass("redDiv");
//offset() - 返回第一个匹配元素相对于文档的位置。
var os = $('div:first').offset();
//注意通过offset获取到的是一个对象，这个对象有两个属性top表示顶边距，left表示左边距
alert("顶边距："+os.top+" 左边距："+os.left);

//调用offset设置元素位置时，也需要传递一个js对象，对象有两个属性top和left
//offset({ top: 10, left: 30 });
$('div:first').offset({
	 top:50,
	 left:60
 }); 

```



#### 2.CSS选择器

##### 基本选择器

**标签选择器（元素选择器）**

- 语法： $("html标签名") 获得所有匹配标签名称的元素

**id选择器**

- 语法： $("#id的属性值") 获得与指定id属性值匹配的元素

**类选择器**

- 语法： $(".class的属性值") 获得与指定的class属性值匹配的元素

**并集选择器**

- 语法： $("选择器1,选择器2....") 获取多个选择器选中的所有元素

##### 层级选择器

**后代选择器**

- 语法： $("A B ") 选择A元素内部的所有B元素

**子选择器**

- 语法： $("A > B") 选择A元素内部的所有B子元素

##### 属性选择器

**属性名称选择器**

- 语法： $("A[属性名]") 包含指定属性的选择器

**属性选择器**

- 语法： $("A[属性名='值']") 包含指定属性等于指定值的选择器

**复合属性选择器**

- 语法： $("A[属性名='值'][]...") 包含多个属性条件的选择器

##### 过滤选择器

**首元素选择器**

语法： :first 获得选择的元素中的第一个元素

**尾元素选择器**

语法： :last 获得选择的元素中的最后一个元素

**非元素选择器**

语法： :not(selector) 不包括指定内容的元素

**偶数选择器**

语法： :even 偶数，从 0 开始计数

**奇数选择器**

语法： :odd 奇数，从 0 开始计数

**等于索引选择器**

语法： :eq(index) 指定索引元素

**大于索引选择器**

语法： :gt(index) 大于指定索引元素

**小于索引选择器**

语法： :lt(index) 小于指定索引元素

**标题选择器**

语法： :header 获得标题（h1~h6）元素，固定写法

##### 表单过滤选择器

**可用元素选择器**

语法： :enabled 获得可用元素

**不可用元素选择器**

语法： :disabled 获得不可用元素

**选中选择器**

语法： :checked 获得单选/复选框选中的元素

**选中选择器**

语法： :selected 获得下拉框选中的元素

## 三、jquery效果

#### 1.基本效果

- `show()` 将隐藏的元素显示
- `hide()` 将可见的元素隐藏。
- `toggle()` 可见就隐藏，不可见就显示。

#### 2.滑动效果

- `slideDown()` 方法用于向下滑动元素。
- `slideUp()` 方法用于向上滑动元素。
- `slideToggle()` 方法可以在 slideDown() 与 slideUp() 方法之间进行切换。如果元素向下滑动，则 slideToggle() 可向上滑动它们。如果元素向上滑动，则 slideToggle() 可向下滑动它们。

#### 3.淡入淡出效果

- `fadeIn()`  淡入(慢慢可见)
- `fadeOut()` 淡出(慢慢消失)
- `fadeTo()`  在指定时长内慢慢的将透明度修改到指定的值。0 透明，1 完成可见，0.5 半透明
- `fadeToggle()` 淡入/淡出 切换

#### 4.上述三组方法的共同点

以上方法都可以添加参数。

- 第一个参数是动画 执行的时长，以毫秒为单位
- 第二个参数是动画的回调函数 (动画完成后自动调用的函数）

## 四.`$( function(){} )`和`window.onload = function(){}`区别

#### 1.他们分别是在什么时候触发?

- `$( function(){} )`是在jQuery 的页面加载完成之后，也就是浏览器的内核解析完页面的标签，创建好 DOM 对象之后就会马上执行。
- `window.onload = function(){}`是在原生 js 的页面加载完成之后，也就是除了要等浏览器内核解析完标签创建好 DOM 对象，还要等标签显示时需要的内容加载完成。（如iframe和img等标签）

#### 2.他们触发的顺序?

- `$( function(){} )`是在 jQuery 页面加载完成之后先执行
- `window.onload = function(){}`是在原生 js 的页面加载完成之后
- 也就是说`$( function(){} )`比`window.onload = function(){}`早执行

#### 3.他们执行的次数?

- `$( function(){} )`是jQuery 的页面加载完成之后是全部把注册的 function 函数，依次顺序全部执行。
- `window.onload = function(){}`是原生 js 的页面加载完成之后，只会执行最后一次的赋值函数。

例子：

```javascript
<script type="text/javascript">
	$(function(){
		console.log(1);
	});

	$(document).ready(function () {
        console.log(2);
    });

    jQuery(function () {
        console.log(3);
    });

    window.$(function () {
        console.log(4);
    });

	window.jQuery(function () {
        console.log(5);
    });

	window.onload= function () {
        console.log(6);
    };

	onload = function (ev) {
        console.log(7);
	};

	// 执行顺序 1 2 3 4 5 7
</script>

```

## 五.jQuery 事件操作

- `click()` 它可以绑定单击事件，以及触发单击事件。后来添加的元素不会绑定事件
- `mouseover()` 鼠标移入事件。后来添加的元素不会绑定事件
- `mouseout()` 鼠标移出事件。后来添加的元素不会绑定事件
- `bind()` 可以给元素一次性绑定一个或多个事件。后来添加的元素不会绑定事件
- `one()` 使用上跟 bind 一样。但是 one 方法绑定的事件只会响应一次。
- `unbind()` 跟 bind 方法相反的操作，解除事件的绑定
- `live()` 也是用来绑定事件。它可以用来绑定选择器匹配的所有元素的事件。哪怕这个元素是后面动态创建出来的也有效

例子：

```javascript
$("h5").click(function () { // 传function是绑定事件
	alert('h5单击事件 == click方法绑定')
});
$("h5").click(); // 不传function是触发事件
//鼠标移入
$("h5").mouseover(function () {
	console.log("你进来了")
});
//鼠标移出
$("h5").mouseout(function () {
console.log("你出去了")
});
// 给元素绑定事件，绑定事件可以链式操作
// jquery对象.事件方法(回调函数(){ 触发事件执行的代码 }).事件方法(回调函数(){ 触发事件执行的代码 }).事件方法(回调函数(){ 触发事件执行的代码 })
$(".head").click(function(){
	$(".content").toggle();
}).mouseover(function(){
	$(".content").toggle();
}); 
//jQuery提供的绑定方式：bind(type,[data],fn)函数把元素和事件绑定起来
//type表示要绑定的事件   [data]表示传入的数据   fn表示事件的处理方法
//bind(事件字符串,回调函数),后来添加的元素不会绑定事件
//使用bind()绑定多个事件   type可以接受多个事件类型，使用空格分割多个事件
$(".head").bind("click mouseover",function(){
	$(".content").toggle();
});
//one()只绑定一次,绑定的事件只会发生一次 one(type,[data],fn)函数把元素和事件绑定起来
//type表示要绑定的事件   [data]表示传入的数据   fn表示事件的处理方法
$(".head").one("click mouseover",function(){
	$(".content").toggle();
}); 
//live方法会为现在及以后添加的元素都绑定上相应的事件
$(".head").live("click",function(){
	$(".content").toggle();
});
$("#panel").before("<h5 class='head'>什么是jQuery?</h5>"); //之后动态添加元素

```

