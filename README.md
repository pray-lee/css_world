### 使用margin-left: auto实现右对齐
```
.demo-parent{
    width: 300px
}
.demo{
    width: 200px;
    margin-left: auto
}
```

### 只能使用子元素的marign-bottom来实现滚动容器的底部留白

### margin只能改变左右方向的内部尺寸，垂直方向则无法改变
```
ul-parent{
   width: 200px 
}
ul { /* important */
    /* 实际宽度是210,多余的10px刚好给了li最后一个元素的右边距 */
    margin-right: -10px;
}
ul > li {
    float:left;
    width: 100px;
    margin-right: 10px
}
这样就不用单独处理最后一个元素的margin-right了
```

### padding百分比值无论是水平方向还是垂直方向都是相对于宽度计算的

### 1ex就是一个x元素的高度借助ex单位，我们可以利用默认的baseline基线对齐实现图标和文字垂直居中的效果,把图标设置成1ex

### 行距 = lineHeight - fontSize


### 多行文字垂直居中 借用vertical-align属性实现
```
.box {
    line-height: 120px; /* important */
    background:#ccc
}
.content {
    display:inline-block; /* important */
    line-height: 20px;
    vertical-align: middle  /* important */
}
<div class="box">
    <div class="content">基于行高实现的多行文字垂直居中效果，需要vertical-align属性帮助</div>
</>
```

### line-height 百分比，属性值，数值的区别：
- 百分比继承的是父容器的line-height*font-size计算出来的计算值，子元素的line-height实际就是x% * (parent.line-height * parent.font-size) 
- 属性值的继承是继承的父容器的属性值，实际计算行高是 x * child.font-size
- 数值就是一个定值。不计算