# CSS
## 常用样式
### 颜色
颜色是CSS中最常用的样式之一，CSS中颜色的表示方法有三种：

- 颜色名 例如：red、green、blue
- rgb() 例如：rgb(255, 0, 0)。rgba() 例如：rgba(255, 0, 0, 0.5) rgba(red, green, blue, alpha)。 see: rgba
- 十六进制 例如：#ff0000, 如果两位相同可以简写为 #f00
- hsl() 例如：hsl(0, 100%, 50%) hsl(hue 色相, saturation 饱和度, lightness 亮度)。 see: hsl
- transparent 透明
### 修饰字体文字的属性
**修饰字体：**

- font-size 字体大小, 默认16px
- font-family 字体，默认为浏览器默认字体
- font-style 字体样式，normal, italic, oblique
- color 颜色

**修饰文本:**

- text-align 文本对齐方式
- text-decoration 文本修饰
- text-indent 文本缩进, 单位建议为 em
- text-wrap 文本换行
- text-overflow 文本溢出
- white-space 文本空白
- line-height 行高
## 内边距和外边距
- 内边距指元素内容与边框之间的距离，使用padding属性设置，padding属性可以设置上下左右四个方向的内边距，也可以设置上下、左右两个方向的内边距。

- 外边距指元素与元素之间的距离，使用margin属性设置，margin属性可以设置上下左右四个方向的外边距，也可以设置上下、左右两个方向的外边距。
```css
    .box{
        /* 上 右 下 左 */
        padding: 10px 20px 30px 40px; 
    }
```
padding/margin的值分为四部分按顺序依次是：上右下左，当缺少某一部分时，缺省的部分为相对面的值。
```css
        .box{
            /* 上 右 下， 缺省了 左边的值，则左边的值为 右边的值即 20px */
            padding: 10px 20px 30px;
        }

        .box1{
            /* 上下 10px 左右 20px */
            padding: 10px 20px;
        }

        .box2{
            /* 上下左右都是 10px */
            padding: 10px;
        }
 ```
margin写法和padding一样。

#### margin特殊情况

- margin的值为auto时，表示自动计算，一般用于块元素居中。
    - 记得设置宽度
    - margin: 值 auto 表示左右外边距为自动计算，上下外边距为值
外边距重叠：当两个元素相邻时，外边距会重叠，重叠的值为两个外边距中较大的值。

外边距塌陷：当父元素和子元素相邻时，子元素的外边距会使父元素的外边距增大，增大的值为子元素外边距的值。 解决方法：

- 给父元素添加overflow: hidden属性。
- 给父元素添加padding属性。
- 给父元素添加border属性。
本质是让父元素形成BFC，BFC不会发生外边距塌陷。

**BFC**

BFC(Block Formatting Context) 块级格式化上下文，是一个独立的渲染区域，让处于 BFC 内部的元素与外部的元素相互隔离，使内外元素的定位不会相互影响。

**如何创建 BFC：**

- 根元素(html)
- 设置position为absolute或fixed
- 设置float属性不为none
- 设置display为inline-block、table-cell、table-caption
- 设置display为flex或inline-flex
- 设置overflow不为visible
## 修饰盒子的属性
盒子是指每个元素都是一个盒子，在CSS中，盒子属性可以由以下几个部分组成：

- width 盒子宽度
- height 盒子高度
- padding 盒子内边距
- border 盒子边框
- margin 盒子外边距
### 盒子模型

根据元素的不同，盒子属性可以分为两类：

- 块级元素：盒子属性可以直接设置
- 内联元素：盒子属性不能直接设置，因为内联元素不能设置宽高。需要设置 display 属性为 block 或 inline-block(后边再讲)
现在我们先讨论块级盒子.

盒子的宽高是由内容宽高、内边距、边框、外边距决定的，盒子的宽高 = 内容宽高 + 内边距 + 边框 + 外边距。 元素实际在网页中的宽度=内容宽度（width） + 左右内边距（padding） + 左右边框（border）。

`box-sizing` 属性用于更改用于计算元素宽度和高度的默认的 CSS 盒子模型。可以设置为 content-box 和 border-box。

`content-box` 是默认值，宽度和高度分别应用到元素的内容框。在宽度和高度之外绘制元素的内边距和边框。 border-box 宽度和高度分别应用到元素的边框盒，即在边框盒内绘制元素的内容，内边距和边框。

`box-shadow `属性用于向元素添加一个或多个阴影。语法：

```css
box-shadow: none | [inset? && [ <offset-x> <offset-y> <blur-radius>? <spread-radius>? <color>? ] ]
```
## 背景
`background` 属性用于设置元素的背景，包括背景颜色、背景图片、背景重复方式、背景位置等。

### 背景颜色

background-color 属性用于设置元素的背景颜色。

### 背景图片

background-image 属性用于设置元素的背景图片。值可以是图片的路径，也可以是 url() 函数。
```css
background-image: url("paper.gif");
```
如果背景图片比元素小，会重复显示，可以使用 background-repeat 属性设置背景图片的重复方式。如果背景图片比元素大，会被裁剪，可以使用 background-size 属性设置背景图片的大小。

**特殊用法：**

> **渐变色：** background-image: linear-gradient(to right, red, yellow); 
渐变色有两种：线性渐变和径向渐变。
> - 线性渐变使用 linear-gradient() 函数，
> - 径向渐变使用 radial-gradient() 函数。 [渐变色](https://lingdaima.com/jianbianse/)

1. `background-repeat` 属性用于设置背景图片的**重复方式**。值可以是 `repeat`、`repeat-x`、`repeat-y`、`no-repeat`。 也可以分别通过`background-repeat-x`和`background-repeat-y`设置水平和垂直方向的重复方式。

2. `background-position` 属性用于设置背景图片的**位置**。值可以是 `top`、`bottom`、`left`、`right`、`center`，也可以是具体的像素值或百分比。

3. `background-size` 属性用于设置背景图片的**大小**。值可以是 `auto`、`cover`、`contain`，也可以是具体的像素值或百分比。 如果背景图片比元素小，可以使用**cover**平铺，会拉伸图片但会保持图片的比例。如果背景图片比元素大，可以使用**contain**平铺。

4. `background-attachment` 属性用于设置背景图片**是否固定**。值可以是 scroll、fixed。

5. `background-cli`p 属性用于设置背景图片的裁剪方式。值可以是 `border-box、padding-box、content-box`。

> 如果一个元素同时设置了背景颜色和背景图片，背景图片会显示在背景颜色的上面。可以使用 background-blend-mode 属性设置背景颜色和背景图片的混合模式。值可以是 normal、multiply、screen、overlay、darken、lighten、color-dodge、saturation、color、luminosity。

### 背景复合写法：
```css
background: <background-color> <background-image> <background-repeat> <background-attachment> <background-position> / <background-size> <background-origin> <background-clip> <background-blend-mode>;
```
## display
>display 属性用于设置元素的显示方式。值可以是 block、inline、inline-block、none。

>什么是块元素？什么是内联元素？

其实就是浏览器默认给元素设置的 display 属性值不同。当display值是 block时就是块级元素，元素独占一行，可以设置宽高，可以设置内外边距，可以设置文本属性，可以设置背景属性。当display值是 inline时就是内联元素(行元素)，元素不会独占一行，宽高由内容决定，不能设置内外边距，不能设置宽高，不能设置背景属性。

`inline-block` 值可以让元素既具有内联元素的特点且宽高属性生效。

none 值可以让元素不显示。visibility 属性也可以让元素不显示(hidden)，但是元素还会占据空间。opacity 属性也可以让元素不显示(0)，但是元素还会占据空间。

#### opacity和visibility的区别：

- opacity可以设置过渡动画，visibility不能。
- opacity可以设置子元素不透明，visibility不能。
#### opacity透明和rgba透明的区别：

- opacity透明会继承父元素的透明度，rgba透明不会继承父元素的透明度。
- opacity会让整个元素透明，rgba只会让元素的背景/字体透明。
## cursor
cursor设置鼠标指针样式。可以有以下值：

- auto 浏览器自动选择光标
- default 默认光标
- none 隐藏光标
- context-menu 上下文菜单光标
- help 帮助光标
- pointer 手指光标
- progress 进度光标
- wait 等待光标
- cell 单元格光标
- 也可以自定义鼠标样式，语法：

> cursor: url("some-cursor.png"), auto;
注意：自定义鼠标样式必须是图片，不能是文字。其次，图片大小不能超过 128x128 像素。