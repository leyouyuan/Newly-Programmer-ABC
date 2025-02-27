# 如何浏览互联网



## 浏览器——访问互联网上内容的工具

之前我们说到，我们的计算机之间，通过一定的协议，在网上传输数据。而浏览器则可以解析获取到的 HTML 文档（网页），根据 HTML 的标记（以及对应的样式信息），将网页展示在用户使用的设备（计算机）的屏幕上。浏览器也需要能够解码获得到的媒体，这样我们才能看到各种图片。

总的来说，浏览器是一款非常复杂的应用程序。

一般来说，用户使用的操作系统，都会自带浏览器。通常，浏览器会有一个小写英文字母“e”的图标（explore，探索），或者“地球”形状的图标，或者是一个流线型的球状图标，以表示浏览器可以用来访问世界范围的内容，或者“网上冲浪”的含义。

> 得益于互联网，信息得以飞速的传播，信息的量和广度都远超之前的媒体。因此，（曾经）人们常用“冲浪”来形容浏览互联网的体验。

可以说，拥有一款现代浏览器（以及能运行该浏览器的设备和可靠的互联网）之后，就几乎能够了解和学习任何事物了。如今，几乎所有人都会通过互联网分享自己所创造的（包括将以往的资料数字化）的内容。可以说，互联网实在是一项伟大的发明。

## 网页、网站基础

简单的说，用户可以用 HTML 语言记录、表示网页页面上的元素，而 CSS 文件可以说明这些元素该以何种形式渲染，而 JavaScript 则可以让网页动起来——比如获得、处理用户的输入（文字、光标移动），也可以修改页面上元素（形状、大小、位置）。

### 动态网页和静态网页

网页的内容可以是静态的，也可以是根据访问的时间、地点或者用户的不同而变化。

顾名思义，静态网页是不会变的。但它也是可以“变”的。用更确切的话说，静态网页不需要远程服务器来进行运算，所有的运算都由获取到网页的本地计算机进行计算，远程服务器只负责提供网页。而动态网页，则往往需要和远程服务器进行数据的交互。

为了使网页可变，我们需要有一种能操作页面元素的语言。JavaScript 就是这样一种语言。浏览器可以运行 JavaScript 脚本，侦听用户的输入、计算数据、与远程计算机进行交互、修改页面的元素。

HTML、CSS、JavaScript 共同造就了我们如今看到的网络页面。

静态网页往往被用来展示个人网站，而动态网页往往被用来向用户提供如导航、社交、购物等服务。

比如，一个用户可以搭建一个自己的主页（homepage），就好比这名用户在网络上的家、门面。

当然，如果没有人知道这个网站，其存在就无法被感知，也就相当于没有意义。为了使用户能够更方便地索引到互联网上的内容，一种叫做“搜索引擎”的网站会使用一种程序能通过网页之间的链接访问其所能及的整个网络。因为程序不停歇的执行任务，因此也称作“机器人（robot）”，又因其如同蜘蛛在网上爬行，因此也得名“网络爬虫”或“spider”。

## 搜索引擎

通过浏览器，我们可以访问网站，访问网站下的网页。但是，这需要我们记忆每个网站的链接。对于一些常用的网站，我们可以将其地址记录下来。但是，对于未知的网站，我们便几乎无从得知。

可以说，虽然网络上有数不尽的资源，但是由于实在太过浩瀚，每个个体之间仍像一座座孤岛。有没有什么办法能够将他们联系起来，或者能够快速找到我想要的信息？

我们知道，网络上的内容通过 URL 联系在一起。网站发布者可以将自己网站（所在服务器）的地址发布在传统媒介上，网站之间也可以加入“友情链接”，相互扩大自己的影响力和知名度；也有一些网站（书籍）专门收录一些网站供用户查阅——可以类比现实生活中的“黄页（Yellow Pages）”。

不过，这些方法都还是有其局限之处。于是就有了搜索引擎。搜索引擎通过一种计算机程序，不知疲倦地访问互联网上的各个网站，并记录下这些网站（网页）的地址，并提取其中的关键词，建立索引。这样，当用户输入某个关键词后，搜索引擎就得以给出相关的网站的链接，称为搜索结果。

## 使用网络进行通信的应用程序

当然，使用互联网并不一定需要网页或浏览器。开发者可以开发能够进行网络通信功能的程序，也能够使用互联网。

比如，开发者可以使用纯文本，或者使用系统提供的图形界面接口，来搭建出交互的界面，而不是使用 HTML 等来搭建网页，并用浏览器渲染、显示。

事实上，有些应用程序采取的是“网页套壳”的方式，即应用程序主体仍是网页，但可能会做一些适配，使得其比网页更为易用。另一方面，毕竟应用程序可以作为一个实体存在于用户使用的操作系统中，这可能会带来一些权限上的优势，比如文件访问、通知推送，也能增加用户看到他的频率。

由于图形化的操作系统往往都会自带系统级的网页渲染工具（称为 System Webview），应用程序开发者可以较容易地将网页转化为操作系统上可使用的“套壳应用程序”。因此“网页套壳”的开发模式比较常见。

## 浏览器与浏览器内核

（待补充）

## 常见浏览器

工欲善其事，必先利其器。要想拥有良好的互联网体验，除了互联网时代的必备知识（本教程的之前和之后都会介绍），一个良好的浏览器是必要的。

### Firefox 

[Firefox 火狐浏览器](http://www.firefox.com.cn/) 是 Mozilla 领导下的开源浏览器，其以“隐私保护”“快速”等特性而闻名。

> 本书会在后边介绍隐私保护相关的知识。

> Firefox 源于著名公司网景（Netscape）的浏览器网景导航者（Netscape Navigator）。网景导航者曾是市占率最高的浏览器，后被 IE（Internet Explorer）借助与 Windows 系统捆绑而击败。Firefox 项目现混合使用 Gecko 和 Servo 两个渲染引擎的组件。

### Chrome

Chrome 是 Google 公司旗下的浏览器，是目前市占率最高的浏览器。Chrome 基于谷歌领导的开源项目 Chromium，该项目的渲染引擎 Blink 是 WebKit 引擎的一个分支，JavaScript 引擎 V8 则是目前性能最好的 JS 引擎。

### Safari

苹果（Apple）旗下的浏览器，使用 WebKit 渲染引擎，该引擎是 KDE Community 开发的 KHTML 引擎的一个分支。苹果在其移动端要求所有上架的浏览器必须使用 Safari 内核。

### Microsoft Edge

微软（Microsoft）开发的浏览器。其有新旧两个版本之分。现在的桌面版 Windows 操作系统预装的为新版 Microsoft Edge 浏览器，其使用 Chromium 内核。

Microsoft Edge 最初的版本使用 EdgeHTML 渲染引擎，该引擎是 IE 使用的 Trident 引擎的一个分支，被微软重写以满足现代浏览器的需求。该版本 Edge 最令人称道的是其 PDF 阅读器，也成为许多人对其念念不忘的理由。

### Internet Explorer

Internet Explorer，简称 IE 浏览器，与 Windows 系统绑定发行的浏览器，支持 ActiveX，因为某些网站依赖其特性而被保留做兼容用途。

## 使用浏览器

### 访问网站

我们在浏览器的**地址栏**中输入地址，按下键盘上的“Enter”键即可访问对应的网站（网页）。

### 标签页

浏览器一般可以打开许多个标签页，其中每个标签页中可以显示一个网页。

### 收藏夹（书签）

如果你在网络上遇到了喜欢的页面，可以将其添加到“**收藏夹**（Favorites）”，其实就是浏览器将这个网页的链接记录了下来。收藏功能一般在地址栏附近（的菜单中），其图标通常为一个“星星”的形状，可以理解为“信息汪洋大海中珍贵的东西”。此外，有些浏览器也会将收藏夹称为“**书签**（bookmarks）”。

Safari 浏览器中同时有“收藏夹”和“书签”的概念。其书签即为普通的链接收藏，而将链接加入到收藏夹中，则会出现在“新建标签页”中，方便用户快速打开。其他浏览器也提供有类似的功能，有时候称为“快速访问”。

[表示收藏的图标为什么普遍用金黄色的星星？ - 知乎](https://www.zhihu.com/question/19633068)

### 阅读列表

有些时候用户可能在网上遇到很多有意思的网页，但是短时间内不能全部阅读，这时可以将其加入阅读列表。相当于一个临时的“书签”功能。

### 剪藏

互联网很大，网络不一定每天都畅通无阻。用户也可以使用“复制”功能，将网站的内容粘贴到富文本编辑器中，存在本地计算机上。

不过，浏览器也会提供保存网页的选项。右键页面空白处，或者按下 `Ctrl`  + `S` 组合键，即可将网页存储在本地。一般，会出现一个网页和与其同名的文件夹，文件夹一般为网页所包含的媒体文件。

有些浏览器也会提供剪辑部分网页的功能。大多数现代浏览器也支持安装插件，提供类似的功能（以及其他各种各样的功能）。

## 常用的搜索引擎

### Baidu

[百度一下，你就知道 - baidu.com](https://www.baidu.com/)

### Bing

[微软 Bing 搜索引擎 - bing.com](https://www.bing.com/)

### Google

（待补充）

