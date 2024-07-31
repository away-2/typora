###### dom节点相关：

创建：
```javascript
document.createElement("ul")    // 创建一个ul标签
document.createDocumentFragment("li")  // 创建一个虚拟dom片段，不会引起回流，可节省性能
```

获取：
```javascript
documnet.getElementById("box")  // 获取id名为box的元素
document.getElementsByTagName("li")  // 获取所有li标签元素
document.getElementByClassName("box")   // 获取类名为box的元素
document.querySelector()  // 可以是任意的选择器，id，类名，标签,并返回匹配的第一个元素
document.querySelector("#box")   // 获取id名为box的元素
document.querySelector(".box")   // 获取第一个类名为box的元素
document.querySelector("li")     // 获取第一个li标签元素
document.querySelectorAll() //可以是任意的选择器 id、标签、类名，并返回匹配的所有元素
document.querySelectorAll(".box")   // 获取所有类名为box的元素集合
document.querySelectorAll("li")     // 获取所有li标签元素集合
```

获取特殊元素(body,html)
```javascript
document.body   // 返回body元素对象
document.documentElement   // 返回html元素对象
```

获取元素节点
`页面中所有的内容都为节点，节点使用 `node`来表示`

- DOM树可以把节点划分为不同的层级关系，常见的是父子兄层级关系
- 元素节点 nodeType 为 1
- 属性节点 nodeType 为 2
- 文本节点 nodeType 为 3 (文本节点包含文字、空格、换行等)
- 实际开发中节点操作一般都是操作元素节点

**父级节点**
node.parentNode  // node表示某个节点，返回指定节点在DOM树中的父节点。

```javascript
<div class="demo"> 
	<div class="box"> 
		<span class="erweima">×</span> 
	</div> 
</div> 
<script> 
// 1. 父节点 parentNode 
let erweima = document.querySelector('.erweima'); 
let box = document.querySelector('.box'); 
// 得到的是离元素最近的父级节点(亲爸爸) 如果找不到父节点就返回为 null 
console.log(erweima.parentNode); 
</script>
```

**父级元素**

node.parentElement 	// 返回当前节点的父级元素，如果该元素没有父节点，或父节点不是一个DOM元素，则返回null

```javascript
// parentNode与parentElement的主要区别在元素是html时才表现出来
html元素的 parentNode   是 document
html元素的 parentElement 是 null
document.documentElement.parentElement  // null
document.documentElement.parentNode === document  	// true
```



**子元素节点**

- parentNode.children (各个浏览器都支持) （不包含 元素节点，文本节点等）
- parentNode.firstElementChild (获取第一个元素节点) 具有兼容问题 ie9才支持
- parentNode.lastElementChild (获取最后一个子元素节点) 具有兼容问题 ie9才支持
- parentNode.children[0] (没有兼容性问题，并且返回第一个子元素)

**兄弟节点**
- node.nexElementSibling //返回当前元素下一个兄弟元素节点，找不到则返回null
- node.previousElementSibling // 返回当前元素上一个兄弟节点，找不到则返回null
- 两种方法都有兼容性的问题，IE9以上支持

添加：
```javascript
ul.appendChild(li)    // 在ul标签中添加li标签
```

删除：
```javascript
ul.removeChild(ul.children[0]);  // 删除ul标签中第一个元素，并返回该元素
```

克隆：
- node.cloneNode() //返回调用 该方法的节点的一个副本，也称为克隆节点/拷贝节点
- 如果括号参数为空或者为 false，则是浅拷贝，即只克隆复制节点本身，不克隆里面的子节点
- 如果括号参数为true，则是深度拷贝，会复制节点本身以及里面所有的子节点

**自定义属性操作**
- 获取属性值
Element.属性 （内置属性可以通过. 直接获取）
Element.getAttribute("属性")（一般用于自定义属性）
```javascript
<div id="box" data="boxData"></div>
<script>
	let box = document.getElementById("box");
	console.log(box.id)  // box
	console.log(box.getAttribute("data"))  // boxData
	console.log(box.getAttribute("id"))   // box
</script>
```
- 设置属性值
Element.属性 = “值”（内置属性可以 直接设置）
Element.setAttribute("属性", "值")（一般用于自定义属性）
```javascript
<div id="box"></div>
<script>
	let box = document.getElementById("box");
	let div = document.createElement("div");
	box.appendChild(div);
	div.id = "boxId";
	div.className = "boxClassName";
	div.setAttribute("index", "1")
</script>
```
![Pasted image 20240117135746](D:\workSoftware\typora\workspace\图片\Pasted image 20240117135746.png)
- 移除属性值
Element.removeAttribute("属性")
```javascript
Element.removeAttribute("index")
```
![Pasted image 20240117141022](D:\workSoftware\typora\workspace\图片\Pasted image 20240117141022.png)

**获取h5自定义属性**
Element.dataset.属性或者Element.dataset["属性"]，  获得的是一个以 data- 开头的自定义属性集合
```javascript
<div id="box" data-index="1" data-list-data="data"></div>
<script>
	let box = element.getElementById("box");
	console.log(box.dataset.index);  // 1
	console.log(box.dataset["index"]);  // 1
	console.log(box.dataset.listData); // data
</script>
```

**设置h5自定义属性**
H5中规定 自定义属性要 以 data-开头做为属性名并且赋值。
Element.setAttribute("属性名",  "值");
```
<div id="box"></div>
<script>
	let box = element.getElementById("box");
	box.setAttribute("data-index", 2);
</script>
```
![Pasted image 20240117142856](D:\workSoftware\typora\workspace\图片\Pasted image 20240117142856.png)

###### 事件对象event相关
事件对象是事件一系列相关数据的集合
```
<div id="box">
	<div class="box1">这是box1</div>
    <div class="box2">这是box2</div>
    <p>这是p标签</p>
    <button>这是按钮</button>
</div>
<script>
let box = documnet.getElemnetById("box");
box.onclick = (e) => {
	console.log(e.target) // 获取点击元素本身
	console.log(e.target.classList.value) // 获取点击元素的类名
	console.log(e.target.nodeName)  // 获取点击元素的标签名
	console.log(e.target.type) //常用于获取表单元素（如 `<input>`、`<textarea>`、`<button>` 等）的类型
	console.log(e.target.style.backgroundColor = "red") // 可用于改变点击元素样式
	
}
</script>
```

###### Element.getBoundingClientRect()
获取元素位置，这个方法没有参数，用于获得页面中某个元素的左，上，右和下分别相对浏览器视窗的位置。
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240117155623.png" alt="Pasted image 20240117155623" style="zoom:67%;" />

```
let box = document.getElementById("box");
let rect = box.getBoundingClientRect();
rect.top：元素上边到视窗上边的距离;	
rect.right：元素右边到视窗左边的距离;	
rect.bottom：元素下边到视窗上边的距离;	
rect.left：元素左边到视窗左边的距离;	
rect.width：是元素自身的宽	
rect.height: 是元素自身的高
```

## 事件操作

| 鼠标事件    | 触发条件         |
| ----------- | ---------------- |
| onclick     | 鼠标点击左键触发 |
| onmouseover | 鼠标经过触发     |
| onmouseout  | 鼠标离开触发     |
| onfocus     | 获得鼠标焦点触发 |
| onblur      | 失去鼠标焦点触发 |
| onmousemove | 鼠标移动触发     |
| onmouseup   | 鼠标弹起触发     |
| onmousedown | 鼠标按下触发     |
