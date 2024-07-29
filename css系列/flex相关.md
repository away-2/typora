#### 轴(主轴为x轴，交叉轴为y轴)
##### flex-direction
`flex-direction`决定主轴方向，交叉轴方向由主轴决定，主轴沿逆时针方向旋转 90° 就得到了交叉轴，交叉轴的起始端和末尾段也由 `flex-start` 和 `flex-end` 表示。

**向右：`flex-direction: row`**
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240102171218.png" alt="Pasted image 20240102171218" style="zoom:67%;" />

**向下：`flex-direction: column`**
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240102171404.png" alt="Pasted image 20240102171404" style="zoom:67%;" />

**向左：`flex-direction: row-reverse`**
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240102171445.png" alt="Pasted image 20240102171445" style="zoom:67%;" />

**向上：`flex-direction: column-reverse`**
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240102171626.png" alt="Pasted image 20240102171626" style="zoom:67%;" />





#### 容器
父容器可以统一设置子容器的排列方式，子容器也可以单独设置自身的排列方式，如果两者同时设置，以子容器的设置为准。
##### 父容器相关
###### 设置子容器沿主轴(x)排列：**justify-content**

**flex-start**：起始端对齐
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109101631.png" alt="Pasted image 20240109101631" style="zoom:67%;" />

**flex-end**：末尾段对齐
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109101729.png" alt="Pasted image 20240109101729" style="zoom:67%;" />

**center**：居中对齐
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109101749.png" alt="Pasted image 20240109101749" style="zoom:67%;" />

**space-around**：子容器沿主轴均匀分布，位于首尾两端的子容器到父容器的距离是子容器间距的一半。
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109102116.png" alt="Pasted image 20240109102116" style="zoom:67%;" />

**space-between**：子容器沿主轴均匀分布，位于首尾两端的子容器与父容器相切。
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109102137.png" alt="Pasted image 20240109102137" style="zoom:67%;" />

###### 设置子容器如何沿交叉轴(y)排列：**align-items**

**flex-start**：起始端对齐
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109102339.png" alt="Pasted image 20240109102339" style="zoom:67%;" />

**flex-end**：末尾段对齐
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109102410.png" alt="Pasted image 20240109102410" style="zoom:67%;" />

**center**：居中对齐
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109102434.png" alt="Pasted image 20240109102434" style="zoom:67%;" />

**baseline**：基线对齐，这里的 `baseline` 默认是指首行文字，即 `first baseline`，所有子容器向基线对齐，交叉轴起点到元素基线距离最大的子容器将会与交叉轴起始端相切以确定基线。也就是使元素内容处于同一基线上
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109102946.png" alt="Pasted image 20240109102946" style="zoom:67%;" />

**stretch**：子容器沿交叉轴方向的尺寸拉伸至与父容器一致。
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109103146.png" alt="Pasted image 20240109103146" style="zoom:67%;" />

###### 设置换行方式：**flex-wrap**
决定子容器是否换行排列，不但可以顺序换行而且支持逆序换行。
**nowrap**：不换行
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109104528.png" alt="Pasted image 20240109104528" style="zoom:67%;" />

**wrap**：换行
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109104550.png" alt="Pasted image 20240109104550" style="zoom:67%;" />

**wrap-reverse**：逆序换行(沿着交叉轴的反方向换行)
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109104623.png" alt="Pasted image 20240109104623" style="zoom:67%;" />


###### 轴向与换行组合设置：**flex-flow**
low 即流向，也就是子容器沿着哪个方向流动，流动到终点是否允许换行，比如 `flex-flow: row wrap`，`flex-flow` 是一个复合属性，相当于 flex-direction 与 flex-wrap 的组合，可选的取值如下：

- `row`、`column` 等，可单独设置主轴方向
  
- `wrap`、`nowrap` 等，可单独设置换行方式
  
- `row nowrap`、`column wrap` 等，也可两者同时设置

###### 多行沿交叉轴对齐：**align-content**
当子容器多行排列时，设置行与行之间的对齐方式。
**flex-start**：起始端对齐
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109105654.png" alt="Pasted image 20240109105654" style="zoom:67%;" />

**flex-end**：末尾段对齐
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109105714.png" alt="Pasted image 20240109105714" style="zoom:67%;" />

**center**：居中对齐
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109105732.png" alt="Pasted image 20240109105732" style="zoom:67%;" />

**space-around**：等边距均匀分布
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109105751.png" alt="Pasted image 20240109105751" style="zoom:67%;" />

**space-between**：等间距均匀分布
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109105813.png" alt="Pasted image 20240109105813" style="zoom:67%;" />

**stretch**：拉伸对齐
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109105833.png" alt="Pasted image 20240109105833" style="zoom:67%;" />



  




##### 子容器相关
###### 在主轴上如何伸缩：**flex**
子容器是有弹性的（flex 即弹性），它们会自动填充剩余空间，子容器的伸缩比例由 `flex` 属性确定。

`flex` 的值可以是无单位数字（如：1, 2, 3），也可以是有单位数字（如：15px，30px，60px），还可以是 `none` 关键字。子容器会按照 `flex` 定义的尺寸比例自动伸缩，如果取值为 `none` 则不伸缩。
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109103810.png" alt="Pasted image 20240109103810" style="zoom:80%;" />

###### 单独设置子容器如何沿交叉轴排列：**align-self**
每个子容器也可以单独定义沿交叉轴排列的方式，此属性的可选值与父容器 `align-items` 属性完全一致，如果两者同时设置则以子容器的 `align-self` 属性为准。

  

###### 设置基准大小：**flex-basis**
`flex-basis` 表示在不伸缩的情况下子容器的原始尺寸。主轴为横向时代表宽度，主轴为纵向时代表高度。
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109110323.png" alt="Pasted image 20240109110323" style="zoom:67%;" />
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109110337.png" alt="Pasted image 20240109110337" style="zoom:67%;" />

###### 设置扩展比例：**flex-grow**
子容器弹性伸展的比例。如图，剩余空间按 1:2 的比例分配给子容器。
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109110448.png" alt="Pasted image 20240109110448" style="zoom:67%;" />


###### 设置收缩比例：**flex-shrink**
子容器弹性收缩的比例。如图，超出部分按 1:2 的比例从给子容器中减去。
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109110550.png" alt="Pasted image 20240109110550" style="zoom:67%;" />


###### 设置排列顺序：**order**
改变子容器的排列顺序，覆盖 HTML 代码中的顺序，默认值为 0，可以为负值，数值越小排列越靠前。
<img src="D:\workSoftware\typora\workspace\图片\Pasted image 20240109110625.png" alt="Pasted image 20240109110625" style="zoom:67%;" />
