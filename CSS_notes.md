层叠（级联）样式表 (Cascading Style Sheets，缩写为 CSS），是一种 样式表语言

# 常用CSS属性
## 一、float属性
float浮动，常用于布局，可以让元素脱离文档流，浮动到指定位置。但是会造成父元素高度塌陷，需要清除浮动。

**float属性的值：**


- left 左浮动
- right 右浮动 
- clear 清除浮动 
- 浮动元素的宽度默认为内容宽度，不在是父元素的宽度。可以通过设置width属性来改变宽度。

**建议：**

1. 使用浮动时，可以给浮动元素的父元素设置好宽高
2. 在浮动元素后紧跟一个清除浮动的元素，可以避免父元素高度塌陷
## 二、overflow属性
overflow 溢出，常用于布局，可以控制元素内容溢出时的显示方式。

**overflow属性值：**

- visible 默认值，内容溢出时不会被隐藏
- hidden 内容溢出时会被隐藏
- scroll 滚动条，内容溢出时会出现滚动条
- auto 自动，内容溢出时会出现滚动条，如果内容不溢出则不会出现滚动条
- 还衍生出overflow-x和overflow-y，分别控制水平方向和垂直方向的溢出。

## position属性
position 定位，常用于布局，可以控制元素的定位方式。

**position属性值：**

- static 默认值，静态定位，元素在文档流中的位置不会改变
- relative 相对定位，元素在文档流中的位置不会改变，但是可以通过top、right、bottom、left属性来控制元素的位置.相对定位是相对于元素本身的位置来定位
- 
- absolute 绝对定位，元素脱离文档流，可以通过top、right、bottom、left属性来控制元素的位置。相对于最近的非static定位的父元素定位
- fixed 固定定位，元素脱离文档流，可以通过top、right、bottom、left属性来控制元素的位置。相对于浏览器窗口定位
- sticky 粘性定位，元素脱离文档流，可以通过top、right、bottom、left属性来控制元素的位置。相对于最近的滚动祖先元素定位. 相对定位和固定定位的结合体
- z-index 层级，常用于布局，可以控制元素的层级。

# CSS 动画
## 2D/3D 转换的动画
> `transform` 属性允许你**旋转，缩放，移动或倾斜**给定元素。
1. rotate()函数：
- `rotate()` 函数定义了一种将元素围绕一个定点（由transform-origin属性指定）旋转而不变形的转换。
    - `rotate()` 方法在参数中规定 rotate 转换。单位为deg(角度)，负值表示逆时针旋转，正值表示顺时针旋转。
    - `rotateX()` 方法在参数中规定 rotateX 转换。单位为deg(角度)，负值表示逆时针旋转，正值表示顺时针旋转。
    - `rotateY() `方法在参数中规定 rotateY 转换。单位为deg(角度)，负值表示逆时针旋转，正值表示顺时针旋转。
    - · 方法在参数中规定 rotateZ 转换。单位为deg(角度)，负值表示逆时针旋转，正值表示顺时针旋转。
2. `scale()` 方法在参数中规定 scale 转换。值小于 1 缩小，值大于 1 放大。
**语法：**`scale(sx, sy)`或者`scale(sx)`
3. translate()属性
- `translate()` 移动属性：
    - translate() 方法在参数中规定 translate 转换。值为像素值或百分比值。
    - translateX() 方法在参数中规定 translateX 转换。值为像素值或百分比值。
    - translateY() 方法在参数中规定 translateY 转换。值为像素值或百分比值。
- `skew() `函数定义了一个元素在二维平面上的倾斜转换。
    - skew() 方法在参数中规定 skew 转换。单位deg(角度)。
    - skewX() 方法在参数中规定 skewX 转换。值为deg(角度)。
    - skewY() 方法在参数中规定 skewY 转换。值为deg(角度)。
## 过渡
> 需要设置 **transition** 属性。
1. `transition`属性可以被指定为一个或多个 CSS 属性的过渡效果，多个属性之间用逗号进行分隔。

2. `transition` 属性是一个简写属性，用于设置四个过渡属性：

- `transition-property` 规定应用过渡的 CSS 属性的名称。
    - all 所有属性都将获得过渡效果。
    - none 没有属性会获得过渡效果。
    - property 定义应用过渡效果的 CSS 属性的名称。
- `transition-duration` 定义过渡效果花费的时间。默认是 0。
- `transiton-function` 过渡效果函数
    - linear 规定以相同速度开始至结束的过渡效果（等于 cubic-bezier(0,0,1,1)）。
    - ease 规定慢速开始，然后变快，然后慢速结束的过渡效果（cubic-bezier(0.25,0.1,0.25,1)）。
    - ease-in 规定以慢速开始的过渡效果（等于 cubic-bezier(0.42,0,1,1)）。
    - ease-out 规定以慢速结束的过渡效果（等于 cubic-bezier(0,0,0.58,1)）。
    - ease-in-out 规定以慢速开始和结束的过渡效果（等于 cubic-bezier(0.42,0,0.58,1)）。
    - cubic-bezier(n,n,n,n) 在 cubic-bezier 函数中定义自己的值。可能的值是 0 至 1 之间的数值。
- `transition-delay` 规定过渡效果何时开始。默认是 0。
## 动画
1. 需要设置 `animation` 属性。动画的定义需要 `@keyframes` 规则。
```css
@keyframes myfirst
{
  0%   {background: red;}
  25%  {background: yellow;}
  50%  {background: blue;}
  100% {background: green;}
}
```
2. animation 属性是一个简写属性，用于设置六个动画属性：

- `animation-name` 规定需要绑定到选择器的 keyframe 名称。
- `animation-duration` 规定完成动画所花费的时间，以秒或毫秒计。
- `animation-timing-function` 规定动画的速度曲线。
- `animation-delay` 规定在动画开始之前的延迟。
- `animation-iteration-count` 规定动画应该播放的次数。
    - `infinite` 规定动画应该无限次播放。
    - `number` 规定动画应该播放的次数。
- `animation-direction `规定是否应该轮流反向播放动画。
    - `normal` 默认值。动画应该正常播放。
    - `alternate` 动画应该轮流反向播放。
    - `reverse` 动画应该反向播放。
    - `alternate-reverse` 动画应该轮流反向播放且第一次是反向的。
## 多列布局
> `column-count` 属性规定元素应该被分隔的列数。
```css
div
{
column-count:3;
}
```
## 响应式布局
> 响应式布局是一种网页设计的技术，它可以使网页在不同的屏幕尺寸下都有良好的显示效果。