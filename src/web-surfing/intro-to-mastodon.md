# Mastodon

Mastodon，直译为“长毛象”，是一个旨在构建去中心化的社交网络。

在之前的内容中，我们介绍过，中心化意味着由单独的一方来提供服务，而服务提供者对于用户的数据和使用有着绝对的权利；而另一方面，当服务提供商的服务器出现故障，所有服务便不再可用。

而去中心化的服务意味着，用户的数据并不为一方所掌握，整个服务也不是由一个服务商进行提供。

## 简介

“Mastodon”就是一个这样的项目，任何组织或个人都可以在自己的服务器上运行一个“实例（instance）”，便可以提供用户注册和内容发布的功能，就像如今常见的的微博、推特一样。因此，我们也会将一个运行着的实例的服务器（网站）称作一个站点。不同的站点有相应的站规，也可能会限制用户的注册。

但长毛象的妙处就在于，不同站点的用户可以自由的进行交互——用户尽可以关注其他站点上的用户，也能和其他站点的用户进行讨论。

这是如何实现的呢？其实，当用户发出一条新的“嘟嘟（toot）”时，用户所在站点的系统，就会将这条内容投递到关注了该用户所在的站点，就像群发的电子邮件一样。换句话说，一个站点会接收到来自其中用户所关注的其他站点的消息。当然，用户也可以亲自造访其关注的用户所在的服务器以查看对方的动态。

用户关注某一外站用户时，关注该用户之前的内容不会被转发到用户所在的站点上，需要用户自行前往对应用户所在的站点查看内容。

通过以上这种方式，不同站点之间就联系在了一起。而且，用户的数据便不再那么容易失去了，因为该信息会投递到所有关注者所在的服务器。

虽然用户发布的数据会存储在用户所注册的站点的服务器上，不过，用户有导出自己数据的权利。如果用户想要更换到另一个站点，可以将自己的数据导出，并且在另一个站点进行导入，就可以完成数据的迁移。

## 如何使用

首先，用户需要在一个实例进行注册，之后便可以开始使用了。用户可以以“`用户名@实例地址`”来表示。

有很多用来访问 Mastodon 的应用程序。但事实上，只需要有一台浏览器就可以访问了，并不需要下载额外的客户端。

用户可以自行寻找适合自己的 Mastodon 站点。Mastodon 官方提供了一个站点，即 [mastodon.social](http://mastodon.social)。

只需要在浏览器中输入“`实例地址/@用户名`”就可以访问对应用户的个人页面。

在开始之前，用户也需要注意几点概念：

- **可见范围**：用户可以选择自己的内容是否公开以及是否出现在公共时间轴上。
- **内容警告**：“Content Warning”，简称“CW”，当用户觉得自己的内容可能不会被所有人接受时，还可以选择将内容隐藏起来，只显示提示文字。
- **敏感内容**：类似的，用户可以将上传的媒体标记为“敏感内容”。

详情可以移步 [Mastodon 官方文档 - 发布嘟文](https://docs.joinmastodon.org/zh-cn/user/posting/) 查看。

一般来说，用户需要阅读站点对应的规则，并且衡量自己发布内容该选择何种可见性。


## 参考链接

- [加入长毛象 - joinmastodon.org](https://joinmastodon.org/)
- https://kaix.in/0001/mastodon/
- https://sspai.com/post/46868
- https://cn.o3o.ca/

