# 常用命令行工具

开始这部分前，读者需要了解：

- Windows 下软件的安装
- 命令行入门基础

## 环境变量

环境变量（environment variable）是计算机中的一些具有名称的值，它可以影响计算机上进程运行的方式。比如，若干程序可以读取一个名为“`HOME`”的变量，而这个变量中存储的是当前用户的“家目录”，比如“`/home/henry/`”，那么应用程序可以通过读取这个变量的值，来实现访问当前用户的家目录。这样，假如用户更换为 Jane，则 `HOME` 的值就更换为 `/home/jane/`，程序仍能正确的访问到当前用户的家目录。

在 Unix、类 Unix 以及 Windows 系统上，每个进程都有一套独立的环境变量。一般来说，当一个进程被创建时，该进程会继承一份其父进程的运行时环境的拷贝。具体来讲，我们可以通过 Shell 程序启动其他程序（包括另外的 Shell 程序），那么这些启动的程序，就会继承当前 Shell 程序中的环境变量。

> 当我们运行 Shell 脚本时（或者其他程序时），其实是创建了一个子进程，我们在其中修改环境变量，并不会影响到其父进程。

在 Unix 系统中，环境变量通常在开机启动时由 `init` 进程加载，以便可以被系统中的其他进程使用，而用户一般会将自己的环境变量（对系统环境变量的添加或修改），放入自己所使用的 Shell 的配置文件中。假设用户使用 `bash`，其会在启动时读取用户家目录下的 `bash.rc`，即 `~/bash.rc`。而在 Windows 下，各个环境变量的初始值一般存储在注册表中。

### 语法

#### 使用

一般在 Shell 命令行界面或者 Shell 脚本中，用户可以通过一些特殊的符号加在环境变量名之上，来访问环境变量的值。按照惯例，环境变量名的应为全大写的英文字母，如 `HOME` 或 `PATH_TO_XXX`。

在 Unix 系统上的 Shell 中，以及，用户可以用 `$VARIABLE_NAME` 或 `${VARIABLE_NAME}` 的方式访问环境变量的值。

```console
$ echo $HOME       # 回显用户家目录的环境变量值，即家目录的路径
/home/henry

$ echo ${HOME}/xyz # 在 HOME 变量值后添加其他内容，并回显
/home/henry/xyz
```

在 Windows 的 PowerShell 中，情况略有不同：

```powershell
echo $Env:HOME
echo ${Env:HOME}
```

#### 赋值

在 bash 中，我们可以这样创建一个可以被其子进程使用的环境变量并为其赋值（使用 `export`）：

```bash
export http_proxy="127.0.0.1:7890"
```

在 PowerShell 中，方式如下：

```powershell
$Env:http_proxy="127.0.0.1:7890"
```

我们也可以在赋值语句中使用环境变量：

bash

```console
$ export abc=123
$ abc="${abc}/123"
$ echo $abc
123/123
```

PowerShell

```console
PS> $Env:abc=12345
PS> $Env:abc="$ENv:abc;123"
PS> echo $Env:abc
12345;123
```

### PATH 变量

`PATH` 变量中存储了一系列目录路径。当用户在 Shell 中键入了未提供全路径的命令，Shell 就会在这个 PATH 中包含的各个路径下查找是否存在该命令。

向 `PATH` 变量中添加一个路径：

**bash**：

```bash
export PATH=$PATH:/path/to/dir
```

或者：

```bash
export PATH=/path/to/dir:$PATH
```

但这样添加之后，用户一旦退出 Shell，修改就会丢失。如果想保留，则应该将该命令添加到用户的 `bash.rc` 中，该文件中的命令会在每次开启 bash 时执行，于是相当于添加了一个用户环境变量。

在 Windows 上，建议用户通过图形界面来修改。用户可以直接在 Windows Search 中输入“环境变量”（或“Environment Variable”），即可打开对应的设置页面。用户也可以右键“此电脑”，选择“属性”，选择“高级”，即可看到“环境变量”选项；也可以在命令行中输入 `sysdm.cpl`，可以打开同样的页面。


参考链接：

- [Environment variable - Wikipedia](https://en.wikipedia.org/wiki/Environment_variable)
- [What is PATH? - definition by The Linux Information Project (LINFO)](http://www.linfo.org/path_env_var.html)

## 包管理器

所谓“包（package）”，可以是我们日常工作中所用到的软件、工具、资源等。而包管理器（package manager）可以帮我们**方便的安装这些软件、工具等**，并且解决他们之间的依赖关系（dependency）。**简单地说，包管理器就是安装程序用的程序**，我们也可以将其与“应用商店”进行类比。包管理器通常也是 CLI 程序，将其可执行文件添加进系统的环境变量中之后，我们就可以在命令行界面中使用这个包管理器了。

我们之前见到的程序的安装方式通常包括：

- 运行一个可执行文件（安装器），这个可执行文件会解压出要安装的程序所需要的文件，或者在线联网下载这些文件。
- 下载的为一个压缩包，解压出来即可运行。这种方式分发的软件也称便携式软件（portable）。

一个软件的安装器通常只能安装一个或几个软件。而包管理器通常可以安装很多软件，一般都是从远程服务器上下载程序包并执行安装操作。这需要软件的开发商将自己的程序发布在对应包管理器的软件仓库上。当然，包管理器会有一些措施来确保软件是由可信任的开发者上传的。

如果通过包管理器安装**可执行程序**，一般情况下，包管理器会负责将这个程序添加到方便用户使用的位置——针对图形应用程序，一般会在“开始”菜单或启动器**创建程序的快捷方式**（或图标）；而对于命令行界面程序，则会在系统可执行文件目录下创建软件的链接，或者将程序的安装目录添加到“环境变量”，**这样使得用户可以使用命令行在各目录下（全局）调用这个程序**。

如果通过包管理器安装“软件库”，则其会将库文件放入系统的链接库目录，或者在相应的位置写入信息，使得程序运行时能够加载到这些库。

> 这里的“库”一般指是一些用来为其他软件提供支持的程序代码集合。我们可以安装“库”，来为应用程序的运行提供支持；也可以安装面向开发人员版本的“库”，这使得我们可以自己编写程序，利用库提供的接口，调用库实现我们想要的功能。

## 文本编辑器

我们之前经常说到文本文件。在现在的计算机上，我们可以通过像 Windows 平台上的记事本这样的程序来存储一些纯文本内容。但是过去的计算机并没有图形界面，因此需要有一些程序来获取用户的键盘输入，并将其转换为数据存储在磁盘上。同时，作为文本**编辑器**，它们也要能够支持文本文件的浏览——将文本文件的内容显示在终端上。

## 编译器

编译器是用来将高级的编程语言翻译成机器能够理解的指令。编译器一般也都是命令行工具。常见的 C/C++ 编译器有 MSVC、Clang、GCC 等。

关于编译器具体的使用，读者可能需要了解一些相应编程语言的基础知识后才能更好理解。这部分内容会在对应语言的章节中介绍。

## 其他有意思的小工具

