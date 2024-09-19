## 优先级：
**!important>行内样式>ID选择器>类、伪类、属性>元素、伪元素>继承>通配符（*）**

## 2n+1(odd):奇数、2n(even)：偶数

## nth-of-type和nth-child

**nth-of-type** 与**nth-child**都属于**css选择器**，都是在同级别节点中找到第n个元素，前者是先确定元素类型，再计算n的位置；后者是先确定n的位置，再确定元素类型

```html
<div class="box">
	<span>1</span>
	<p>p1</p>
	<p>p2</p>
</div>
```
```css
.box p:nth-of-type(2) {
	background: red;   // p2变红
}
.box p:nth-child(2) {
	background: green;  // p1变绿
}
```
## :nth-last-child(n) 倒数第n个子元素

```html

<style> 
div :nth-last-child(1){
    color:red;  // 父元素div的倒数第一个元素 被选中
}
</style>
    <div>
        <p>第一个段落。</p>
        <p>第二个段落。</p>
        <p>第三个段落。</p>
        <p>第四个段落。</p>
        <p>第五个段落。</p>
    </div>	

```



## :nth-last-of-type(n) 同类型的倒数第n个子元素

```html
<style> 
div p:nth-last-of-type(2){
	color:red; // 处于同类型 p标签 倒数第2个
}
</style>
  <div>
    <h1>h11</h1>
    <p>第一个段落。</p>
    <p>第二个段落。</p>
    <p>第三个段落。</p>
    <h1>h11</h1>
    <p>第四个段落。</p> // 变红
    <p>第五个段落。</p>
    <h1>h11</h1>
  </div>	
```

## 子选择器 element>element

选择父元素为 element 元素的所有 element 子元素。
```css
ul>li>p { 
	border: 1px solid red; 
}
```
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231221135448.png" alt="Pasted image 20231221135448" style="zoom: 67%;" />

## 后代选择器 element element
选择 element 元素内部的所有 element 元素。
```css
ul li{
    border: 1px solid red;
}
```
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231221141520.png" alt="Pasted image 20231221141520" style="zoom:67%;" />

## 相邻兄弟选择器 element+element
选择紧接在 element元素之后的 element 元素。
```html
<div> 
	<h1>h1</h1> 
	<p>p1</p> 
	<p>p2</p> 
	<p>p3</p> 
</div>

h1+p{ 
	color:red; 
}
```
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231221135733.png" alt="Pasted image 20231221135733" style="zoom:67%;" />

## 一般兄弟选择器 element1~element2
选择前面有 element1 元素的每个 element2 元素。
```html
<div> 
	<h1>h1</h1> 
	<p>p1</p> 
	<p>p2</p> 
	<p>p3</p> 
</div>

h1~p { 
	border: 1px solid red; 
}
```
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231221135912.png" alt="Pasted image 20231221135912" style="zoom:67%;" />

## 属性选择器[]
示例html
```html
<ul>
    <li foo>1</li>
    <li foo="abc">2</li>
    <li foo="abc efj">3</li>
    <li foo="abcefj">4</li>
    <li foo="efjabc">5</li>
    <li foo="ab">6</li>
</ul>
```

**[attribute]**
选择所有带 `foo` 属性的元素

```css
[foo] { 
	background-color:red; 
}
```
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231221140333.png" alt="Pasted image 20231221140333" style="zoom: 80%;" />

**[attribute=value]**
选择 attribute=value 的所有元素。

```css
[foo=abc]{
    background-color:red;
}
```
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231221140452.png" alt="Pasted image 20231221140452" style="zoom:80%;" />

**[attribute~=value]**
选择 attribute 属性包含单词 value 的所有元素。

```css
[foo~=abc]{
    background-color:red;
}
```
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231221140607.png" alt="Pasted image 20231221140607" style="zoom:80%;" />

**[attribute^=value]**
选择其 attribute 属性值以 value 开头的所有元素。类似正则的 `^`,以什么开始。
```css
[foo^=abc]{
    background-color:red;
}
```

<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231221140704.png" alt="Pasted image 20231221140704" style="zoom:80%;" />

**[attribute$=value]**
选择其 attribute 属性值以 value 结束的所有元素。类似正则的 `$`,以什么结束。

```css
[foo$=abc]{
    background-color:red;
}
```
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231221140750.png" alt="Pasted image 20231221140750" style="zoom:80%;" />

**[attribute*=value]**
选择其 attribute 属性中**包含** `value` **子串**的每个元素。

```css
[foo*=abc]{
    background-color:red;
}
```
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231221140837.png" alt="Pasted image 20231221140837" style="zoom:80%;" />

**[attribute|=value]**
选择 `attribute` 属性值以 `value` 开头的所有元素。
```css
[foo|=abc]{
    background-color:red;
}
```
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20231221140924.png" alt="Pasted image 20231221140924" style="zoom:80%;" />

