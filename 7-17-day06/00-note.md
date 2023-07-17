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