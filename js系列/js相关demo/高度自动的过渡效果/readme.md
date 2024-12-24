# 高度自动过渡效果
### 1. 通过height: 0; --> height: auto;
    这种方法虽然使用了transition，但是不会有动画效果，因为有个前提，必须是数字类的变化，才会有动画效果，auto不是数字。
    动画的本质就是数值不断进行变化

### 2. 使用max-height
    max-height: 0; --> max-height: 1000px;(一个超出原本内容的height)
    这个有动画效果，但是感觉有点怪，因为hover的max-height很大，不是原本内容本身的height，
    展开的效果感觉很快，但是收起较慢，是因为收起的内容不是你看到的内容的高度，而是你设置的超出原本内容的高度，但是过度时间都是0.3s，所以看起来收起效果较慢。

### 3. transform: scaleY(0); -->  transform: scaleY(1);
    这个也有动画效果，是通过Y轴的缩放，进行高度过渡效果，但是看上去有一种文字压缩的效果。

### 4. display: grid; 网格布局
     grid-template-rows:  0fr; -->  grid-template-rows:  1fr;
     动画比较丝滑，但是可能有兼容性问题。

### 5. js实现
    通过获取内容高度，动态实现动画效果，在height由0 --> height时，浏览器在执行js不会渲染页面，所以看不到动画效果，
    通过getBoundingClientRect()触发重排，渲染页面后，可观察到动画效果。

