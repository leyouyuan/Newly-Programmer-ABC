# 程序员入门指南

开始此项目的一个动机是深感国内计算机教育之不平衡，有些学生初中即能熟练掌握计算机的使用，对编程也略知一二，而另一方面，很多走出高中、踏入高校的学生甚至不知计算机为何物。此外，纵使身边有熟悉计算机使用的亲人朋友，由于知识背景不同，普通用户也很难与之沟通（即“知识的诅咒”）；这一情景也同样发生在国内诸多大学的新生群体中。当今时代，计算机的使用十分普遍，许多常用的操作应为大众所掌握。同时，编程也日渐成为信息时代的生活必备技能，懂得编程者，可以利用计算机更高效的处理信息。本项目就计划为刚刚进入计算机专业/编程领域者提供一个参考性的入门指南，同时也是信息时代的敲门砖。

另一方面，笔者也希望将自己自开始计算机专业的学习以来所掌握的的知识进行一定的整理。独立的文章并不易于记录有体系和学习过程的知识，而通过一本书，则可以将知识形成框架。

编写一份指南并非易事，另一方面也不希望进行重复劳动，可是目前并没有见到切入点和编写方式都比较符合笔者个人想法的资料——大多数都需要使用者有一定的计算机基础（即知识背景要求高，不贴近普通用户），或者限于篇幅只能略谈一二，不得深入其中原理。而作者认为，计算机作为一种人造产物，其发展是有规律可循的，大致按照计算机的发展历史来认识计算机，也许更为科学，更能了解其中的所以然，以便能以更好的方式打开计算机这个领域。

之所以将本项目称作《程序员入门指南》，是因为笔者认为，凡是正在使用计算机的人，都可以称为程序员。计算机本身就是为了方便人类处理信息而作，而人们使用计算机，就需要编程。哪怕是使用现有的、编写好的程序，也算是“编程”的过程——因为这也需要将多个程序有机的串联起来。而我们平时所谓的编程人员，不过是能够用代码将这些过程表述出来、调用计算机进行更精细、复杂的工作。本书的目的，是希望读者对自己身边的计算机能够拥有更好的了解，以及能够更好、更高效的使用计算机。

奈何作者才疏学浅，心有余而力不足，很多内容的表述多有不专业、错误之处，还请多多指正！

## 项目地址

|代码托管平台|链接|
|:---:|:---:|
|GitHub|[tsagaanbar/Newly-Programmer-ABC](https://github.com/tsagaanbar/Newly-Programmer-ABC)|
|Gitee|[tsagaanbar/Newly-Programmer-ABC](https://gitee.com/tsagaanbar/Newly-Programmer-ABC)|

目录：[src/SUMMARY.md](src/SUMMARY.md)

在线阅读地址：[GitHub Pages](https://tsagaanbar.github.io/Newly-Programmer-ABC/) 

## 构建

使用 [mdBook](https://github.com/rust-lang/mdBook) 构建静态页面。

### 为什么使用 Markdown？

Markdown 语法虽然简陋、方言多，但自发明以来经久不衰，必然有其原因。笔者认为，Markdown 语言**简单**、够用（某种程度上），更复杂的内容——如合并了单元格的表格——可以嵌入 HTML 代码。

### 关于使用 MathJax 渲染数学公式

mdBook 本身具有对 MathJax 的支持，但目前需要使用 `\( \)` 和 `\[ \]` 包裹公式（而不是较为通行的 `$` 和 `$$`），且公式代码中的反斜线、下划线等还需要转义，才能在正常通过 Markdown 渲染器（renderer）后不被丢失。参见 [官方技术文档](https://rust-lang.github.io/mdBook/format/mathjax.html)。

关于 MathJax，有人认为通过这种方式在网页上显示公式十分缓慢，提倡在构建期就将数学公式转化为 HTML 代码或是 SVG 图像。对此，笔者有两点思考：首先 MathJax 还是会保留公式源码的，方便读者复制和重复利用；另外，MathJax 有无障碍支持。笔者大学在读时，身边的同学中就有一位视障人士，虽然由于不同学院不同专业而从未与之交流过，但是还是经常能在校园中见到这位同学。总之，遇到这位同学令笔者深有感触。比如，笔者现在写文档时配图基本都要加说明文字（caption），对于特殊符号尽量说明，比如“连续的两根反斜线 `\\`”；虽然，不知道他们使用的读屏设施有多高级，也不知道有没有机会看到这些文字。但是，如果我们每个人都尽自己的一份绵薄之力改变现状，那么未来一定会更好。

## 友情链接

- [计算机入门指南](https://github.com/Computer-Literacy-Primer/Computer-Literacy-Primer)：一个同类项目
- [OI Wiki](https://oi-wiki.org) 项目仓库地址：[GitHub](https://github.com/OI-wiki/OI-wiki/)
- [浅見沙織的笔记](https://t.me/NoteOfAsamiSaori)（Telegram 频道）
- @空忧居士 - [CSDN](https://me.csdn.net/qq_45871272)
- @Par - [Github](https://github.com/ouoqwq1)

## 参考资料

- 《计算机教育中缺失的一课（The Missing Semester of Your CS Education）》[中文版网站](https://missing-semester-cn.github.io/)、[中文版 GitHub 仓库地址](https://github.com/missing-semester-cn/missing-semester-cn.github.io)
- [编程入门指南 v1.5 - 知乎专栏](https://zhuanlan.zhihu.com/p/19959253)

除特别注明外，项目中除代码外的部分均在 [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/deed.zh) 协议之条款下提供。

