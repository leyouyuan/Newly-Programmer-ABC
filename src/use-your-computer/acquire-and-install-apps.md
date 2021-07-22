# 获取应用程序

应用程序大概可以分为应用类和游戏类。其中应用类有单纯的实用工具，也有网站为了方便用户使用其服务而开发的应用。

在开始之前，我们希望读者带着下面的问题进行阅读。

我们之前说过，应用程序基本是编译后的可执行程序（可直接执行的机器码）、或是需要其他程序解释的程序脚本。除了程序本身外，应用程序可能还需要支持其运行的其他程序或程序库，以及运行所需资源文件，如图片和音频。

那么，应用程序本身的文件在哪里，其使用的文件在哪里，用户使用应用程序的产生的数据又存放在哪里？

下面我们结合若干实例，讲解若干获取、安装、使用应用程序的方式。

## 从应用商店获取程序

如今的不少操作系统都具有“应用商店”或“应用市场”这一概念。应用商店是一款预先安装在操作系统内部的程序，用户可以在应用商店中搜索需要的应用程序，并以轻松的步骤完成安装。因为涉及到安装程序，应用商店其往往有较高的权限。

应用商店主要面向的是一般用户，因此其中的应用一般需要经过审核和测试，才能提供给用户进行下载，以免恶意程序对用户的数据和设备造成损坏。应用商店一般也支持应用程序的更新，以便用户及时使用到应用的最新版。

开发者可以将其开发的应用程序上传到应用商店中，但是一般需要应用商店的审核。某些应用商店可能还会要求开发者经过认证，这可能需要支付一定的费用。

读者可以看到，应用商店对于应用的控制是相对比较绝对的，应用商店的管理着可以决定应用的上架或下架。

有些操作系统（或某些地区设置下的操作系统）的“商店”，其支持的内容往往更为广泛，比如音视频、书籍等内容。

开发者可能会通过自己开发的应用进行获利。有些系统中通过应用商店来提供付费内容，付费内容包括买断式的应用程序、订阅式的应用程序内部服务（定时扣费）、应用程序内部的付费内容。这种商店往往要求开发者通过其提供的渠道完成应用内购买（In-App Purchase），应用商店往往会从这些支付中收取一定的提成。也有些系统的应用商店不提供这些方式，用户则需要通过开发者自己设定的渠道来完成购买操作，这一步往往会用到现有的在线支付网站。

有些开发者采取用户自愿的付费模式，即“捐赠（donate）”。一个更为接地气的说法为“打赏”。用户可以向开发者支付（捐赠）一定数量的金额（通常由用户决定），来表示对开发者的支持。捐赠可能会帮助开发者继续生产出更优质的内容。

### 移动设备

许多移动设备如智能手机、平板电脑使用的 Andriod 操作系统由 Google 开发，其本身只是一个基础操作系统，各手机厂商可以在其上进行修改，比如加入自定义的功能、修改用户界面（UI，User Interface）等。往往，厂商会开发并在系统中预装自己的应用市场。Google 也有自己的应用市场，即 Google Store，其在 Google 套件中提供。

Apple 公司生产的移动设备中一般预装其开发的 iOS 操作系统，其中预装的应用商店为 App Store。

### Windows

如今的 Windows 系统中也有 Microsoft Store。用户一般可以在开始菜单中找到该程序。

操作系统一般会自带有文本编辑器。用户也可以安装其他的文本编辑器。下面我们尝试在应用商店中搜索一款记事本应用程序：

- 打开 Microsoft Store；
- 在搜索框中输入“Notepads”；
- 点击搜索结果中的“Notepads App”，进入详情页；
- 点击安装。

读者也可以尝试通过关键字搜索自己需要的工具，并进行挑选和安装。

## 获取应用程序的其他渠道

有些时候，应用并未在应用商店中提供，而是通过网络分发给用户，开发者可以选择通过第三方的应用商店、个人网站、网络硬盘等各种方式分享自己开发的程序。通过这样的渠道分发的应用程序主要有下面几种形式。

### 安装器形式

应用分发商可能会分发可执行文件格式的“安装程序”，也称“安装器（Installer）”。安装器是一个可执行程序，其可能在自身中存储有安装程序所需的文件，也可能在线获取其所需的文件。后者通常是因为，软件的数据量较为庞大，不便直接通过 HTTPS 下载，因此软件开发方可能会提供软件下载器，其内部可能包含代理，支持断点续传等功能，可以使用户获得更好的下载体验。

在 Windows 操作系统，我们常见以 `exe` 或 `msi` 为扩展名的“安装包”。这些文件为可执行文件，严格来说属于“安装器”。

### 安装包形式

安装包常见于移动设备所使用的操作系统。安装包一般需要用户手动下载，也可以从一些第三方的应用商店或网站获得。用户需要**使用系统相关的应用程序**打开安装包，以便将其中的内容复制到计算机中，并进行相应的配置，完成安装操作。

应用程序安装包，即为包含了应用程序的可执行文件、相应资源文件以及安装信息的一个文件。

### 安装介质形式

某些时候，我们得到的软件是实体的光盘，或者是计算机中的“光盘映像文件”。这种情况通常是由于软件本身庞大，但又不得不考虑离线安装（用户无法连接互联网）的情况。安装介质中通常包含若干用于安装程序的可执行文件（也可以称之为安装器），以及应用程序相关的其他文件。

### 便携式应用

即应用程序及其运行所需文件通过压缩文件的形式发布（方便传输），这种程序只需解压即可运行。

通过安装器安装的应用一般需要通过应用程序提供的卸载器来卸载；通过安装包安装的程序可以通过系统提供的功能来卸载。至于便携式应用，用户不需要该应用程序时，直接删除即可。

### 总结

总的来说，应用程序需要被放置在正确的位置、经过正确的配置，才能使用，这一般会通过安装器来实现，或者需要用户手动配置。

一般，需要使用安装器的应用的安装较为复杂，比如涉及较多的文件、或者需要修改许多系统设置。对于提供安装器的应用，一般首选使用安装器安装，并使用卸载器卸载。使用便携式应用，用户需要自行管理软件的安装与卸载。

### 风险

我们之前说到，安装器属于可执行应用，且一般需要较高的权限，这就给流氓程序了可乘之机。开发者可以选择在用户运行安装程序时，强行为用户安装不需要的应用程序，甚至可以对用户的电脑造成破坏。因此，请读者在可信的来源获取应用程序。

### 应用程序签名

（待补充）

### 应用程序的版本

有些时候，用户可以获得到应用程序的不同版本。

#### 版本号

应用程序的版本可能会以类似“\[主版本号\].\[次版本号\].\[补丁号\]”的方式命名。补丁号的迭代通常是由于解决了程序中的小问题；次版本号的迭代一般是加入了新的功能，但不影响旧功能的使用；主版本号的迭代通常意味着大的改动。

#### 稳定版与测试版

一般来说，提供给用户的应用程序应该是稳定的、不容易出问题的。但是，有些时候应用程序开发的新的功能，需要较多的用户来测试，以便更快地发现问题；也有些用户倾向于测试新功能，帮助软件的开发，或者单纯希望“尝鲜”。

同时提供应用程序稳定和测试版本的厂商通常会对其加以标识，如“稳定（stable）”。普通用户接触到的测试版，一般为“公测版”，一般以“beta”表示；相对的，在“公测版”推出之前的称为“内测版”，也称作“alpha”版。“内测版”一般比“公测版”更不稳定，因此使用内测版并进行测试的，往往是开发者组织内部用户，也可能包括筛选后的一批用户。

#### 平台

很多应用程序往往会为多个平台提供相对应的版本。这些版本往往会称为不同的“build”。在这里，“build”作动词将是构建的意思，即从源代码等素材变成具体可用的软件。

### 动手尝试

下面，读者可以尝试自行获取病安装一些软件。

#### Firefox 浏览器

读者可以尝试访问 [Firefox 火狐浏览器](https://www.firefox.com.cn/) 下载火狐浏览器。

#### Visual Studio Code

Visual Studio Code 是一款代码编辑器，简称 Code，其支持多种多样的插件，可以扩展出丰富的功能。开发者可以使用它来编写代码，普通用户也可以将其当作一款纯文本编辑器来使用它。读者可以尝试从 [code.visualstudio.com](https://code.visualstudio.com) 在线获取 Visual Studio Code。

打开 Code 后，用户可以直接将单个或多个文件拖入其中进行编辑，也可以打开一个或多个文件。更常见的情况是新建一个目录或者打开一个现有的目录，也就是“工作目录”，目录中的文件会在界面旁展示出来，方便用户处理多个文档。

#### 7-Zip

读者可以尝试在搜索引擎中搜索 7-Zip 并完成程序的下载和安装。