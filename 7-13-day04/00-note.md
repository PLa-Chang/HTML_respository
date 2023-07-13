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