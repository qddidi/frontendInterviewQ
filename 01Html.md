一般在面试中对于 html 的考查占比不是很多,基本就是问几个基础的问题就结束了。但是如果你答不上来,问题就大了,很大可能你在面试官心中的形象就会一落千丈,基本与这个工作无缘了。

这里我列举了一些常见的关于 Html 方面的面试题,大家可以查漏补缺一下

## 谈谈 Html 语义化标签

通过语义化标签,可以让页面有更加完善的结构,让页面的元素有含义,同时利于被搜索引擎解析,有利于 SEO。常见的语义化标签有`header`(头部标签)、`nav`(导航栏)、`aside`(侧边栏)、`section`(区块)、`footer`(底部标签)等等

## HTML5 新特性

1. 语义化标签
2. 增强型表单(如可以通过 input 的 type 属性指定类型是 color 还是 date 或者 url 等)
3. 媒体元素标签(video,audio)
4. canvas,svg
5. svg 绘图
6. 地理等位(navigator.geolocation.getCurrentPosition(callback))
7. 拖放 API(给标签元素设置属性 draggable 值为 true,能够实现对目标元素的拖动)
8. Web Worker(可以开启一个子线程运行脚本)
9. Web Storage(即 sessionStorage 与 localStorage)
10. Websocket(双向通信协议,可以让浏览器接收服务端的请求)
11. dom 查询(document.querySelector()和 document.querySelectorAll())

## DOCTYPE(⽂档类型) 的作⽤

它是 HTML5 中一种标准通用标记语言的文档类型声明,它的目的是告诉浏览器（解析器）应该以什么样（html 或 xhtml）的文档类型定义来解析文档,不同的渲染模式会影响浏览器对 CSS 代码甚⾄ JavaScript 脚本的解析。它必须声明在 HTML ⽂档的第⼀⾏。

## 常⽤的 meta 标签有哪些

`meta` 标签由 `name` 和 `content` 属性定义,用来描述网页文档的属性,比如网页的作者,网页描述,关键词等,

1. charset,用来描述 HTML 文档的编码类型：

```html
<meta charset="UTF-8" />
```

2. keywords,页面关键词

```html
<meta name="keywords" content="关键词1,关键词2,关键词3" />
```

3. description,页面描述

```html
<meta name="description" content="描述内容" />
```

4. refresh,重定向和刷新,比如 3s 之后跳转网页

```html
<meta
  http-equiv="Refresh"
  content="3;url=https://juejin.cn/user/3193422001474199"
/>
```

5. viewport,控制视口宽高缩放等

```html
<meta
  name="viewport"
  content="width=device-width, initial-scale=1, maximum-scale=1"
/>
```

6. 控制搜索引擎索引方式,如不让本页面被检索

```html
<meta name="robots" content="none,nofollow" />
```

其中 content 参数有以下几种

- all：文件将被检索,且页面上的链接可以被查询；
- none：文件将不被检索,且页面上的链接不可以被查询；
- index：文件将被检索；
- follow：页面上的链接可以被查询；
- noindex：文件将不被检索；
- nofollow：页面上的链接不可以被查询。

## 常见的行内元素和块级元素有哪些?

行内元素: < span >、 < a >、< strong >、< b >、< em >、< i >、< del >、< s >、< ins >、< u >、< span >、< img />、< input />、< select >、< textarea >、< br />、等

块级元素:< div >、 < h1 >~< h6 >、< p >、< div >、< ul >、< ol >、< li >、< dd >、< dt >、< dl >等

注意: 行内元素设置宽高无效,设置上下外边距(margin-top,margin-bottom)无效

## img 的 srcset 属性的作⽤?

用于浏览器根据宽、高和像素密度(dpi)来加载相应的图片资源。比如

```html
<img src="small.jpg " srcset="big.jpg 1440w, middle.jpg 800w, small.jpg 1x" />
```

表示浏览器宽度达到 `800px` 则加载 `middle.jpg` ,达到 `1400px` 则加载 `big.jpg`,像素密度为 1 的时候用 `small.jpg`

## iframe 有那些优点和缺点?

优点:

1. 可以在页面上独立显示一个页面或者内容,不会与页面其他元素产生冲突。
2. 可以在多个页面中重用同一个页面或者内容,可以减少代码的冗余。
3. 加载是异步的,页面可以在不等待 iframe 加载完成的情况下进行展示。
4. 方便地实现跨域访问

缺点:

1. 搜索引擎可能无法正确解析 iframe 中的内容
2. 会阻塞主页面的 onload 事件
3. 和主页面共享连接池,影响页面并行加载

## label 的作用是什么?如何使用?

定义表单控制间的关系,当用户选择该标签时,浏览器会自动将焦点转到和标签相关的表单控件上。它两种用法：一种是 id 绑定,一种是嵌套

```html
/**id绑定 */
<label for="Name">Number:</label>
<input type="“text“" name="Name" id="Name" />

/**嵌套 */
<label>Date:<input type="text" name="B" /></label>
```

## head 标签有什么作用,其中什么标签必不可少?

它是 `HTML` 文档中的一个重要元素,它不会出现在浏览器显示的页面中,而是用于声明文档的元信息。包含了多个子标签,其中最重要的是 `title` 标签,它是必不可少的。他还包含一些常用标签,如 `meta` 标签和 `link` 标签`script`标签等,`meta` 标签可以定义一些文档的元信息,如文档的描述、关键字和作者等,`link` 标签则用于引入外部资源,如 CSS 样式表、图标等,`script`则是引入 js 脚本文件

## 浏览器乱码的原因是什么?如何解决?

1. 编码格式不匹配

> 浏览器打开网页时,需要根据网页源代码的编码格式来解码。如果网页的编码格式与浏览器的编码格式不匹配,就会出现乱码。比如,网页的编码格式为 UTF-8,而浏览器的编码格式是 GB2312,那么就会出现乱码。

2. 网页编码错误

> 在编写网页的时候,如果编码出现错误,也会导致浏览器打开网页时出现乱码。比如,在写 HTML 代码时,如果忘记给中文字符指定编码格式,就会出现乱码。

3. 字体缺失

> 有些网页会使用比较特殊的字体,如果浏览器中没有这个字体,就会找不到对应的字符,从而出现乱码。

## 你听说过渐进增强和优雅降级吗?它们之间的区别是什么?

**渐进增强**:针对低版本浏览器进行构建页面,保证最基本的功能,然后再针对高级浏览器进行效果、交互等改进和追加功能达到更好的用户体验。

**优雅降级**:一开始就构建完整的功能,然后再针对低版本浏览器进行兼容

## Canvas 和 SVG 的区别?

1. `Canvas` 绘制出来的图形或传入的图片都依赖分辨率,能够以 .png 和 .jpg 格式保存存储图像,可以说是位图,`SVG` 可以在`H5`中直接绘制,绘制的是矢量图
2. `Canvas` 不支持事件处理器,`SVG` 支持事件处理器
   > `Canvas` 绘制的图像 都在 Canvas 这个画布里面,是`Canvas`的一部分,不能用 js 获取已经绘制好的图形元素。而 SVG 绘图时,每个图形都是以 DOM 节点的形式插入到页面中,可以用 js 或其他方法直接操作
3. 工作机制不同
   > Canvas 是逐像素进行渲染的,一旦图形绘制完成,就不会继续被浏览器关注。而 SVG 是通过 DOM 操作来显示的。SVG 适合带有大型渲染区域的应用程序,比如地图。而 Canvas 适合有许多对象要被频繁重绘的图形密集型游戏。

## script 标签中 defer 和 async 的区别

defer 和 async 都可以让浏览器异步加载 js 文件,不同的是 defer 仅仅是异步加载 js 脚本,并不会立刻执行,而是等到文档所有元素解析完成之后,DOMContentLoaded 事件触发执行之前。如果存在多个有 defer 属性的脚本,那么它们是按照加载顺序执行脚本的；而对于 async,它的加载和执行是紧紧挨着的,无论声明顺序如何,只要加载完成就立刻执行

## 简述 HTML5 离线储存

在线情况下,浏览器发现 HTML 头部有 manifest 属性,它会请求 manifest 文件,第一次访问,那么浏览器就会根据 manifest 文件的内容下载相应的资源,进行离线存储。

在页面头部加入 manifest 属性,如下:

```html
<html manifest="cache.manifest"></html>
```

然后在 cache.manifest 文件中编写离线存储的资源规则,比如

```
CACHE MANIFEST
# 2021-06-26 14:01 V0.1.2.42634241855282310056  hash 以便做版本控制
# 默认部分，显式缓存这些文件

CACHE:
#需要缓存的列表，如字体、图片、脚本、css
./assets/images/favicons/32x32.png
./assets/fonts/VideoJS.eot
./assets/fonts/VideoJS.svg
./assets/fonts/VideoJS.ttf
./assets/fonts/VideoJS.woff

# 启动页资源
./index.html

NETWORK:
#不需要缓存的
*

FALLBACK:
#访问缓存失败后，备用访问的资源，第一个是访问源，第二个是替换文件 *.html /offline.html
```
