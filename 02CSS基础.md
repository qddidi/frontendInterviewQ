# Css

一般在基础的面试中对于 CSS 的考查占比还是很多的,一般会考察 CSS 基础,响应式,Flex 布局,以及一些布局的实现方案等

在这里我列举了一些常见的关于 CSS 方面的面试题

首先看一下 **CSS 的基础部分**

## 1.CSS3 中有哪些新特性

1. 新增各种 CSS 选择器 （: not(.input)：所有 class 不是“input”的节点）
2. 圆角 （border-radius:8px）
3. 阴影和反射 （Shadoweflect）
4. 文字特效 （text-shadow）
5. 文字渲染 （Text-decoration）
6. 线性渐变 （gradient）
7. 旋转 （transform）
8. 增加了旋转,缩放,定位,倾斜,动画,多背景等等
9. 多列布局 （multi-column layout）

## 2.CSS 选择器及其优先级

1. ！important 优先级 10000

```css
.wrap {
  color: red !important;
}
```

2. 内联选择器 优先级 1000

```html
<div style="color:red"></div>
```

3. ID 选择器 优先级 100

```css
#wrap {
  color: red;
}
```

4. 类别选择器 优先级 10

```css
.wrap {
  color: red;
}
```

5. 属性选择器 优先级 10

```css
//css
[name]:{ color:red } [name=bb]:{ color:red } //html
<div name="jk"></div>
<div name="bb"></div>
```

6. 伪类 优先级 10

```css
.wrap:hover {
  color: red;
}
```

7. 元素选择器 优先级 1

```css
H1 {
  color: red;
}
span {
  color: red;
}
```

8. 通配符选择器 优先级 0

```css
* {
  color: red;
}
```

9. 继承选择器 没有优先级

```css
//css
p{ color:red }

<p>我是p元素<span>我是p元素中的span元素</span></p>
```

此时 span 的 color 也是 red

## 3. CSS 中可继承与不可继承属性有哪些

**可继承:**

字体系列属性

- font-family：字体族名称或/及类族名称的一个优先表

- font-weight：字体的粗细

- font-size：字体的大小

- font-style：字体的风格

文本系列属性

- text-indent：文本缩进

- text-align：文本水平对齐

- line-height：行高

- word-spacing：单词之间的间距

- letter-spacing：中文或者字母之间的间距

- text-transform：控制文本大小写（就是 uppercase、lowercase、capitalize 这三个）

- color：文本颜色

其它

- visibility：控制元素显示隐藏
- list-style：列表风格，包括 list-style-type、list-style-image 等
- cursor：光标显示为何种形态

**不可继承**

- display：规定元素应该生成的框的类型

文本属性：

- vertical-align：垂直文本对齐

- text-decoration：规定添加到文本的装饰

- text-shadow：文本阴影效果

- white-space：空白符的处理

- unicode-bidi：设置文本的方向

- 盒子模型的属性：width、height、margin、border、padding

- 背景属性：background、background-color、background-image、background-repeat、background-position、background-attachment

- 定位属性：float、clear、position、top、right、bottom、left、min-width、min-height、max-width、max-height、overflow、clip、z-index

- 生成内容属性：content、counter-reset、counter-increment

- 轮廓样式属性：outline-style、outline-width、outline-color、outline

- 页面样式属性：size、page-break-before、page-break-after

- 声音样式属性：pause-before、pause-after、pause、cue-before、cue-after、cue、play-during

## 4. display 的属性值及其作用

- none
  > 隐藏元素，不占据页面空间；visibility:hidden 的元素，也是隐藏元素，但是会占据原来的页面空间。
- inline
  > 将元素设置为行内元素
- block
  > 将元素设置为块元素
- inline-block
  > 将元素设置为行内块元素
- list-item
  > 将元素设置为列表元素(li)
- table
  > 元素作为块级表格来显示
- inline-table
  > 元素作为内联表格来显示
- flex
  > 将元素设置为弹性布局

## 5. 对盒模型的理解

网页中每个元素都具备以下属性:外边距(margin),内边距(padding),边框(border),内容(元素本身的 width,height)。它规范了我们页面的所有所有元素的一个布局规范是由外向内进行布局。一个元素的宽度

## 6. 对 line-height 的理解及其赋值方式

行高指一行文字的高度,。具体来说是指两行文字间基线之间的距离

带有单位的 line-height,如 24px,1.5em

> 会被计算成 px 后继承。子元素的 line-height = 父元素的 line-height \* font-size （如果是 px 了就直接继承）

而不带单位的 line-height,如 1.5,150%

> 被继承的是倍数。子元素的 line-height = 子元素的 font-size \* 继承的倍数

## 7. display:inline-block 什么时候会显示间隙？

相邻的 inline-block 元素之间有换行或空格分隔的情况下会产生间距

解决方案:

1. 将 inline-block 元素写在一行可以解决
2. 给父元素设置 font-size:0,缺点是子元素如果里面有文字，文字会消失不见
3. 给元素设置 float:left,缺点高度塌陷，要清除浮动。
4. 设置父元素 display:table;word-spacing:-1em。

## 8. css 隐藏元素的方法有哪些

1. display:none 渲染树不会渲染对象
2. visibility: hidden 元素在页面中仍占据空间，但是不会响应绑定的监听事件。
3. opacity: 0 透明的设置为 0
4. transform: scale(0,0) 元素缩放为 0
5. z-index 设置负值
6. clip/clip-path 使用元素裁剪的方法来实现元素的隐藏，这种方法下，元素仍在页面中占据位置，但是不会响应绑定的监听事件。

## 9. link 和@import 的区别

1. 从属关系：@import 是 css 提供的语法规则，只有导入样式表的作用；link 是 html 提供的标签，不仅可以加载 css 文件，还可以定义 rss、rel 连接属性等
2. 加载顺序：加载页面时，link 标签引入的 css 被同时加载；@import 引入的 css 将在页面加载完毕后被加载
3. 兼容性：@import 是 css2.1 才有的语法，故只可在 ie5+才能识别；link 标签作为 html 元素，不存在兼容性问题
4. DOM 可控性：可以通过 js 操作 DOM，插入 link 标签来改变样式；由于 DOM 方法是基于文档的，无法使用@import 的方式插入样式。
5. link 引入的样式权重大于@import 引入的样式（在 link 标签引入的 css 文件中使用@import 时，相同样式将被该 css 文件本身的样式层叠）

## 10. transition 和 animation 的区别

1. Transition 强调过渡; Animation 强调流程与控制 。

2. 两者的控制粒度不一样

   1. 某种程度上, transition 更加粗一点, 比如过渡的速度进行了封装, 可以控制是匀速改变还是贝塞尔曲线之类的。
   2. animation 提供的 keyframe 方法, 可以让你手动去指定每个阶段的属性; 此外 animation 还封装了循环次数, 动画延迟等功能, 更加自由和强大。

3. 动画状态:
   1. CSS 的 transition 只有两个状态:开始状态 和 结束状态 。
   2. animation 可能是多个状态, 有帧的概念 。
4. 动画触发方式:
   1. CSS 的 transition 需要借助别的方式来触发, 比如 CSS 的状态选择器（如:hover）或 借助 JavaScript 来触发 。
   2. animation 不但可以使用上面的方式触发, 更重要的是可以自动触发 。
5. animation 控制动效上要比 transition 强，因为它具备一些控制动效的属性，比如“播放次数”、“播放方向”、“播放状态”等。

6. 动画实现的范围:
   1. transition 是有一定限制的, 并不是所有 CSS 的属性都具有过渡效果 。
   2. 另外相比而言, CSS 的 animation 要比 transition 强大的多, 几乎所有的 css 属性都可以实现动画效果。
   3. 这也是为什么使用 animation 制作 Web 动画的场景更多 。
7. 动画实现方式
   1. CSS 的 animation 是离不开 @keyframes 的，换句话说，我们需要先使用 @keyframes 来注册一个动画效果，即帧来描述动画效果。当然，只注册也不见得有效果，还是需要使用 animation-name 属性引用 @keyframes 注册好的动画效果。

## 11. display:none 与 visibility:hidden 的区别

1. 是否占据空间 display:none，该元素不占据任何空间，在文档渲染时，该元素如同不存在（但依然存在文档对象模型树中）。 visibility:hidden，该元素空间依旧存在。即一个（display:none）不会在渲染树中出现，一个（visibility :hidden）会。

2. 是否渲染 display:none，会触发 reflow（回流），进行渲染。 visibility:hidden，只会触发 repaint（重绘），因为没有发现位置变化，不进行渲染。

3. 是否是继承属性 display:none，display 不是继承属性，元素及其子元素都会消失。 visibility:hidden，visibility 是继承属性，若子元素使用了 visibility:visible，则不继承，这个子孙元素又会显现出来。

## 12. 伪元素和伪类的区别和作用？

1. 作用不同

   伪类是一种状态，可以看看做是选择器。比如鼠标经过 伪类 :hover , 比如 结构伪类 li:nth-child， 一个冒号。

   伪元素 是 元素， 简单来说，就是用 css 模拟出来了一个盒子。

1. 权重不相同

   伪类 是 10 （类、属性选择器 [type=submit]）

   伪元素 是 1 (标签选择器 )

1. 使用场景不同

   比如:鼠标经过盒子，盒子里面的样式会有变化，则需要使用 伪类

   如果想在盒子内部插入一个小盒子，此时可以使用伪元素。

## 13. 为什么有时候⽤ translate 来改变位置⽽不是定位？

改变元素的 transform 不会触发重排或重绘，只会触发复合。使用改变元素定位的方式可能会触发重排。

而且在修改 transform 来变更元素位置时会更加顺滑，使用修改元素定位比如说 left、right 之类的属性是在一些场景下即使元素脱离了文档流，也会出现卡顿的情况。

## 14. li 与 li 之间有看不见的空白间隔是什么原因引起的？如何解决？

**原因**

浏览器默认会把 display 属性为 inline 或者 inline-block 元素间的空白字符（空格换行 tab）渲染成一个空格。也就是我们上面 li 元素换行产生的换行符，而它会变成一个空格，当然空格就占用一个字符的宽度。

**解决方法**(参考问题 7)

## 15. 替换元素的概念及计算规则

**概念:**

替换元素是浏览器根据元素标签的属性，来决定元素的具体显示内容。比如 img 元素,你可以更换 src 属性来让浏览器展示不同内容

**计算规则**

替换元素的尺寸结构分为三种：依次是固有尺寸、HTML 尺寸以及 CSS 尺寸。 其中计算规则为 `CSS 尺寸>HTML 尺寸>固有尺寸`

## 16. 常见的图片格式及使用场景

- JPEG(JPG)

JPEG 图片支持的颜色比较多，图片可以压缩，但是不支持透明

一般用来保存照片等颜色丰富的图片

- GIF

GIF 支持的颜色少，只支持简单的透明，支持动态图

图片颜色单一或者是动态图时可以使用 gif

- PNG

PNG 支持的颜色多，并且支持复杂的透明，不支持动图

可以用来显示颜色复杂的透明的图片

- webp

谷歌新推出的专门用来表示网页的一种格式

它具有其他图片格式的所有优点，而且文件格式还很小

缺点：兼容性不好

- base64

图片使用 base64 编码，这样可以将图片转换为字符，通过字符形式来引入

一般都是需要和网页一起加载的图片才会使用 base64

## 17. 对 CSS Sprites 的理解

它成为`精灵图`,也可以叫`雪碧图`,原理是将一个页面涉及到的所有图片都包含到一张大图中去，然后利用 CSS 的 background-image，background-repeat，background-position 属性的组合进行背景定位。

**优点**

1.利用 CSS Sprites 能很好地减少网页的 http 请求，从而大大提高了页面的性能，这是 CSS Sprites 最大的优点；

2.CSS Sprites 能减少图片的字节，把 3 张图片合并成 1 张图片的字节总是小于这 3 张图片的字节总和。

**缺点**

1. 在图片合并时，要把多张图片有序的、合理的合并成一张图片，还要留好足够的空间，防止板块内出现不必要的背景。在宽屏及高分辨率下的自适应页面，如果背景不够宽，很容易出现背景断裂；

2. CSSSprites 在开发的时候相对来说有点麻烦，需要借助 photoshop 或其他工具来对每个背景单元测量其准确的位置。

3. 维护方面：CSS Sprites 在维护的时候比较麻烦，页面背景有少许改动时，就要改这张合并的图片，无需改的地方尽量不要动，这样避免改动更多的 CSS，如果在原来的地方放不下，又只能（最好）往下加图片，这样图片的字节就增加了，还要改动 CSS。

## 什么是物理像素,逻辑像素和像素密度,为什么在移动端开发时需要用到@3x, @2x 这种图片？

**像素密度(ppi)**是指每英寸的长度上排列的像素点数量

**物理像素** 设备屏幕实际拥有的像素点

**逻辑像素** 可以认为是计算机坐标系统中得一个点，这个点代表一个可以由程序使用的虚拟像素(比如: css 像素)

**css 像素** 指的是 CSS 样式代码中使用的逻辑像素，在 CSS 规范中，长度单位可以分为两类，绝对(absolute)单位以及相对(relative)单位。px 是一个相对单位，相对的是设备像素(device pixel) 。(浏览器使用的抽象单位(逻辑像素的一种)， 主要用来在网页上绘制内容。)

**像素比 dpr** 物理像素与逻辑像素之间的比例,一个逻辑像素等于多少个物理像素是由设备本身决定的

根据上面的概念可以得知,像素比 dpr 越高,一个逻辑像素占用的物理像素就越多。如果我们要保证图片不失真,我们需要图片的一个像素对应一个物理像素,所以需要根据不同的 dpr 选用不同的图片

## CSS 优化和提高性能的方法有哪些？

1. 合并 css 文件
2. 减少 css 嵌套
3. 建立公共样式类，把相同样式提取出来作为公共类使用
4. 减少通配符\*或者类似[hidden="true"]这类选择器的使用
5. 巧妙运用 css 的继承机制，如果父节点定义了，子节点就无需定义
6. 不用 css 表达式
7. 使用 cssSprite(雪碧图)处理某些图片,比如 Icon 图标
8. CSS 压缩

## CSS 预处理器/后处理器是什么？为什么要使用它们？

**预处理器** 如：less，sass，stylus，用来预编译 sass 或者 less，增加了 css 代码的复用性。层级，mixin， 变量，循环， 函数等对编写以及开发 UI 组件都极为方便

**后处理器** 如： postCss，通常是在完成的样式表中根据 css 规范处理 css，让其更加有效。目前最常做的是给 css 属性添加浏览器私有前缀，实现跨浏览器兼容性的问题。

**使用原因**

- 结构清晰， 便于扩展
- 可以很方便的屏蔽浏览器私有语法的差异
- 可以轻松实现多重继承
- 完美的兼容了 CSS 代码，可以应用到老项目中

## ::before 和 :after 的双冒号和单冒号有什么区别？

1. 冒号(:)用于 CSS3 伪类，双冒号(::)用于 CSS3 伪元素。
2. ::before 就是以一个子元素的存在，定义在元素主体内容之前的一个伪元素。并不存在于 dom 之中，只存在在页面之中。

## 单行、多行文本溢出隐藏

**单行**

```css
overflow: hidden; // 溢出隐藏
text-overflow: ellipsis; // 溢出用省略号显示
white-space: nowrap; // 规定段落中的文本不进行换行
```

**多行**

```css
overflow: hidden; // 溢出隐藏
text-overflow: ellipsis; // 溢出用省略号显示
display: -webkit-box; // 作为弹性伸缩盒子模型显示。
-webkit-box-orient: vertical; // 设置伸缩盒子的子元素排列方式：从上到下垂直排列
-webkit-line-clamp: 3; // 显示的行数
```

## 对媒体查询的理解？

使用媒体查询可以让元素在不同页面大小下展示不同样式,用于让我们的页面适配不同设备,比如在设备宽度大于 600px 时隐藏类名为 sidebar 的元素

```css
@media (max-width: 600px) {
  .sidebar {
    display: none;
  }
}
```

## 对 CSS 工程化的理解?

CSS 工程化是为了解决以下问题：

- 宏观设计：CSS 代码如何组织、如何拆分、模块结构怎样设计？
- 编码优化：怎样写出更好的 CSS？
- 构建：如何处理我的 CSS，才能让它的打包结果最优？
- 可维护性：代码写完了，如何最小化它后续的变更成本？如何确保任何一个同事都能轻松接手？

以下三个方向都是时下比较流行的、普适性非常好的 CSS 工程化实践：

- 预处理器：Less、 Sass 等；
- 重要的工程化插件： PostCss；
- Webpack loader 等 。

## 如何判断元素是否到达可视区域

- window.innerHeight 是浏览器可视区的高度；
- document.body.scrollTop || document.documentElement.scrollTop 是浏览器滚动的过的距离；
- el.offsetTop 是元素顶部距离文档顶部的高度（包括滚动条的距离）；
- 内容达到显示区域的：el.offsetTop < window.innerHeight + document.body.scrollTop;

## z-index 属性在什么情况下会失效

1. 父元素 position 为 relative 时，子元素的 z-index 失效。解决：父元素 position 改为 absolute 或 static；
2. 元素没有设置 position 属性为非 static 属性。解决：设置该元素的 position 属性为 relative，absolute 或是 fixed 中的一种；
3. 元素在设置 z-index 的同时还设置了 float 浮动。解决：float 去除，改为 display：inline-block；

## CSS 中的 transform 有哪些属性

1. 旋转（rotate）

```css
transform: rotate(40deg);
```

2. 扭曲（skew）

```
transfrom: skew(30deg,30deg);
```

3. 缩放（scale）

```
transform: scale(2,1.5);
```

4. 平移（translate）

```
translate: translate(100px, 20px);
```

5. 矩阵变形（matrix）

```
transform: matrix(1,0,0,1,50,50);
```
