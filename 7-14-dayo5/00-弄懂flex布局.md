# 弄懂flex布局
## 一：关于flex布局
例如我们让多个div横向排列，传统做法是使用浮动，但浮空后因为脱离文档流的缘故，父元素会失去高度，这又涉及了清除浮动等一系列的问题。
而flex布局相对简单很多，修改父元素`display:flex`，你会发现div自动就排列成了一行，而且没有浮动之后的副作用，从回流角度考虑，flex的性能更优于float。
## 概念
1. 容器

       设置 display:flex 的元素
2. 项（item）

        容器的子元素就是 flex 项
3. 轴

        在 flex 容器中有两条轴线（主轴和交叉轴）
4. 起始线和终止线

flex布局属性主要由容器属性和项目属性构成，下面我会分开讨论这两类属性。
## 二：容器属性
### 1.flex-direction属性
**取值：**

`row(默认) | row-reverse | column | column-reverse`

用于设置主轴方向（控制项目排列方向与顺序），默认row，即横向排列（从左到右排列，主轴在 X轴），项目排列顺序为正序1-2-3；row-reverse同为横向排列（从右到左排列，主轴在 X 轴），但项目
顺序为倒序3-2-1。

column 与row相反，为纵向排列(主轴在 Y 轴，从上到下)，项目顺序为正序1-2-3，column-reverse同为纵向排列(主轴在 Y 轴，从下到上），项目顺序为倒序3-2-1。
### 2.flex-wrap属性
**取值：**

`    nowrap(默认) | wrap | wrap-reverse`

- 用于控制项目是否换行，`nowrap`表示不换行；

- `wrap`表示换行，即项目不会等分容器宽度，而是根据自身宽度进行排列，如果超出父容器宽度则自然换行。
- `wrap-reverse`同样表示换行，需要注意的是第一排会紧贴容器底部，而不是我们想象的项目6紧贴容器顶部，效果与wrap相反。
### 3.flex-flow属性
**flex-flow属性**是`flex-deriction`与`flex-wrap`属性的简写集合;
- 默认属性为`row nowrap`，即横向排列，且不换行，如果需要控制项目排列与换行，推荐使用此属性，而非单独写两个。
### 4.justify-content属性
**取值：**
`flex-start(默认) | flex-end | center | space-between | space-around | space-evenly;`

- 用于控制项目在主轴的对齐方式，默认flex-start即起始线对齐;
- `center` 为居中，对应的flex-end为终止线对齐。
- `space-between`为左右两端对齐，即左右两侧项目都紧贴容器，且项目之间间距相等。
- `space-around`为项目之间间距为左右两侧项目到容器间距的2倍，比较特别的布局，日常使用不太多。
- `space-evenly`为项目之间间距与项目与容器间距相等，相当于除去项目宽度，平均分配了剩余宽度作为项目左右margin。
### 5.align-items属性
**取值：**

`flex-start | flex-end | center | baseline | stretch(默认)`

- 用于控制项目在交叉轴的排列方式，默认stretch即如果项目没设置高度，或高度为`auto`，则占满整个容器。
- `flex-start`会让项目在交叉轴紧贴容器顶部，`flex-end`与之相反：
- `center`使用最多，自然不会陌生，在交叉轴中心位置排列：
- `baseline`比较特殊，它让项目以第一行文字的基线为参照进行排列：
注意，常理来说`justify-content与align-items`默认分别处理项目横轴，纵轴的对齐方式，但如果我们修改了flex-direction为column，它们处理的轴向会交换，也就是justify-content处理纵轴，align-items处
理横轴。
### 6.align-content
**取值：**

`flex-start | flex-end | center | space-between | space-around | space-evenly | stretch(默认);`


用于控制多行项目（交叉轴上）的对齐方式，如果项目只有一行则不会起作用，多行项目需要设置flex-warp:warp；默认`stretch`，即在项目没设置高度，或高度为auto情况下让项目填满整个容器，与align-items类似。

flex-start ，center，flex-end 与align-items属性表现一致：
space-around与justify-content保持一致，即项目之间间距为上下两端项目与容器间距两倍。

`space-evenly`同理，项目之间间距与项目到容器之间间距相等，

`space-between`为上下两侧项目紧贴容器。

`align-content`其实也有baseline等其它可用值，表现与上面介绍过的属性一致，只是单行项目或多行项目的区别。
## 三：项目属性
介绍完容器属性，简单介绍下项目属性。容器属性是加在容器上的，那么项目属性呢，就是写在项目上的，就好比容器属性给ul，项目属性给li差不多一个意思。
### 1.order
**取值：**

默认0，用于决定项目排列顺序，数值越小，项目排列越靠前。
### 2.flex-grow
**取值：**

默认0，用于决定项目在有剩余空间的情况下是否放大，默认不放大；注意，即便设置了固定宽度，也会放大。


### 3.flex-shrink
**取值：**

默认1，用于决定项目在空间不足时是否缩小，默认项目都是1，即空间不足时大家一起等比缩小；注意，即便设置了固定宽度，也会缩小。

但如果某个项目flex-shrink设置为0，则即便空间不够，自身也不缩小。
上图中第二个项目flex-shrink为0，所以自身不会缩小。
### 4.flex-basis
**取值：**

默认auto，用于设置项目主轴的大小。默认auto时，项目会保持默认大小（width/height），或者以width为自身的宽度，但如果设置了flex-basis，权重会width/height属性高，因此会覆盖width/height属性。

### 5.flex
**取值：**

默认0 1 auto，flex属性是flex-grow，flex-shrink与flex-basis三个属性的简写，用于定义项目放大，缩小与宽度。

该属性有两个快捷键值，分别是auto(1 1 auto)等分放大缩小，与none(0 0 auto)不放大不缩小。
### 6.align-self
**取值：**

`auto(默认) | flex-start | flex-end | center | baseline | stretch，`

表示继承父容器的align-items属性。如果没父元素，则默认stretch。
用于让个别项目拥有与其它项目不同的对齐方式，各值的表现与父容器的align-items属性完全一致。