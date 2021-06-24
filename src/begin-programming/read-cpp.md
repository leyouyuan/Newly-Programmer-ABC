# 快速上手阅读 C++ 代码

在开始这个章节前，读者需要：

- 了解信息在计算机中的存储形式
- 有一定的数据结构基础
- 了解文件、目录等概念
- 有一定的命令行基础，理解 CLI 应用。

C/C++ 是很基础的编程语言。因为其编程过程较为贴近计算机运行的实质（相对其他编程语言抽象程度较低），一般执行效率很高，常被用来编写一些提供基础功能的程序。

要想读懂一般的 C/C++ 代码其实不难，我们只需要熟悉若干基本概念以及一些符号的语义即可。我们接下来主要介绍 C++ 的代码。

## 编译

C/C++ 是一种需要经过编译器**编译**（compile）、生成可执行文件才能执行的语言。C/C++ 的源代码是人类可读的、由文本字符组成的，而编译，就是将源代码变成 CPU 能理解并执行的指令的过程。作为普通用户，我们一般不需要了解编译器是如何分析理解源代码，并将其最终变成机器指令的过程。

需要了解，不同的 CPU 平台，由于指令集不尽相同（实现相同的效果所需的指令不同、指令的格式不同），因此针对一个平台生成的可执行的文件，如果不借助其他工具，在另一个平台上可能就是完全不能理解的文件；不同操作系统也是如此——每个系统有自己的可执行文件的格式，不同操作系统格式不同，则无法通用。

幸运的是，大多数情况下，像 C/C++ 这样的高级语言的源代码，只需要经过一些修改，或者甚至不需要修改，就可以通过相应平台上的编译器，生成针对具体平台的可执行文件。也就是说，我们编写的程序针对各个平台的翻译工作，都是在编译器来完成的了。这给我们的开发带来了很大的方便。

> 由于编译器只和文本文件打交道，所以编译器一般都是 CLI 应用，一般需要用户通过命令行来操作（关于命令行和 CLI 应用，读者可以阅读下一章节）。因此，理论上我们只需要一个文本文件编辑器和编译器，就能完成 C/C++ 程序的编写。不过为了方便开发，常用带有图形界面的 IDE（集成开发环境），通常只需要一些简单的配置，IDE 就能帮我们调用编译器、完成编译等操作。通常，IDE 也具有调试、协同开发等其他很多功能。恰当的使用工具能够大幅提升我们的效率。

## 链接

我们可以将一些常用的代码事先编译成机器指令，在需要的时候只需调用即可，这样可以节省编译的时间。这些预先编译好的代码一般称作“库（library）文件”。

> “库”也可以泛指所有事先写好、可以复用/供人调用的代码，不一定是编译好的才叫库。

根据我们编写程序的调用，寻找对应的代码的过程叫做链接（linking）。链接有动态（dynamic）链接和静态（static）链接之分，静态链接可以想象成直接把编译好的代码复制到编译出来的可执行文件中，而动态链接则是在程序执行时才去加载对应的库。

> 由于两种链接方式存在不同，有些代码的许可证可能会限制调用时所能使用链接方式。

## C、C++ 的版本

C/C++ 语言有着不同的版本，每个版本可能会规定一些新的规范、提出一些新的功能。但是这些规范和功能的实现情况，需要看具体的编译器厂商的进度。

常见的编译器有 GNU GCC、Clang、MSVC 等等。

截至目前，最新的 C++ 标准为 C++ 20，之前的标准还有 C++ 11、C++ 14、C++ 17 等。

## C、C++ 的区别

如果要细说两者，其实还是挺复杂的，不能简单的把 C++ 认为成 C 的升级版。可以说，C++ 11 可以算是一门全新的语言了。两者的代码风格上还是有一些共同之处。

另外，C++ 也兼容 C 语言的语法。我们尽可以在 C++ 中使用 C 风格的语句，但是应该尽可能遵守 C++ 的编程规范。

> 如果你之前有其他编程语言的基础，请注意，C++ 可能和他们有着很大的区别，不仅仅是表面上语法的不同，也有概念上的不同之处。

## C++ 代码中常见的符号

下面的这些符号都是 ASCII 码表中对应的符号，也是我们常说的英文符号、半角符号。

### `#` 井号

通常，我们会在代码中看到以 `#` 符号起始的行：

```cpp
#include <algorithm>
#include "MyClass.h"
```

也有这样的：

```cpp
#ifdef WIN32
    /* some code here */
#endif
```

之前我们说到，C/C++ 是一个需要编译的语言，而跟在 `#` 符号后面的，叫做**预处理指令**，用来告诉预处理器（preprocessor）对代码执行一些预先的处理。预处理（preprocess）过程发生在编译之前。如 `include` 指令，就是将其后所指明的文件复制到对应的位置。比如 `#include <algorithm>` 就是将 `algorithm` 文件中的内容复制到对应的地方；同理，`#include "MyClass.h"` 就是将 `MyClass.h` 文件的内容复制进来。这些文件也叫做**头文件**（headers）。至于 `<>` 和 `""` 的区别，以及其他指令的含义，我们会在 C/C++ 预处理命令的章节具体介绍。

### `;` 分号

英文分号通常用作语句（statement）之间的分割。一个语句通常完成一次**赋值**，**声明**或**调用**等操作，我们将在下面讲解这些操作。

下面的代码就是三条语句。我们可以将其写在一行，也可以分在几行写。

```c
a = 1; b = 2; c = 3;
```

> 在 C/C++ 中，语句之间可以有任意多的分号。语句也可以在一些地方断开，分在两行完成。

### `{}` 花括号

一对花括号（braces）中可以包含若干语句，我们将其称为一个代码块（code block）。

```c
{
    a = 1;
    b = 2.34;
}
```

花括号也可以在变量**初始化**时使用，其中包括的是一个或者一些值。（我们会在下面介绍“变量”的概念）

```c
int a[] = {1,2,3};
```

### `""` 引号

在引号中的文本叫做“字符串（string）”，也就是一连串字符。我们也将这些写在代码中的这些字符串的文本形式称为“字符串字面量（string literal）”，他们其中可能会包含如 `\b` 这样的 `\n` 转义字符。

### `<>` 尖括号

尖括号通常和 C++ 中的**模板**相关。模板是“泛型（generic）编程”中的一个概念，“泛型”即“通用类型”。有些程序的逻辑是和具体数据类型无关的，我们可以使用泛型思想编写程序，然后针对不同的数据类型，实例化出对应的代码，这提高了代码复用性，使得程序员可以编写更少的代码。

尖括号中通常填写数据类型的名称。比如，`some_function` 是一个函数模板。当我们书写 `some_function<int>` 时，编译器则会为我们生成**针对 `int` 类型**（**of** `int` type）的代码。

关于什么是“函数”，我们会在下面进行介绍。

### 注释

有时候，我们可能会希望能够在代码中记录一些说明语句作用的文本。这些文本叫做**注释**（comment）。注释会被编译器忽略掉，对于编译器来说，它们相当于不存在。

也有时候，我们在**调试**代码的过程中，会希望一些语句不被执行，也可以将代码“注释掉（comment out）”。

注释分为单行注释和多行注释。在每一行中，`//` 之后的文本，直到这一行结束，皆为注释（字符串中出现的“`//`”除外），这称为单行注释。多行注释以 `/*` 开始，以 `*/` 为结束，并且不支持嵌套。也就是说，`/*` 会和最近的 `*/` 配对，将其中的内容形成注释，这就会导致嵌套的注释出现错误。

```cpp
// This is a single-line comment.

// int a = 1; // commented out; won't be executed

/* This is a 
   multi-line
   comment.  */
```

### 续行符

单独出现在**行末**的反斜线（back slash）“`\`”会将下一行的内容接续到这一行来，也就是两行并作一行。也就是说，如果在一个单行注释行末添加续行符，则该单行注释的下一行也会变为注释。

```cpp
// this is a single-line comment\
   but acctuall takes two lines
```

### `=` 和 `==`

我们常见的等号 `=`，在 C/C++ 中为赋值运算符，用来将等号右边事物的值，赋给左边的事物。

至于 `>`、`<`、`>=`、`<=` 则为常见的比较运算符，用来比较左右两边元素的值的大小。要判断两个元素是否相等，则使用 `==` 运算符。这些式子的结果为 `true`（真） 或者 `false`（假）。


### `::` 作用域范围解析符

我们可能会在 C++ 代码中见到两个连在一起的冒号，它叫做作用域范围解析符。不过它的名字不重要，我们只需要理解它的含义表示**符号的所属**即可。比如 `A::B`，**表示 `A` 中的 `B`**。

我们可能经常见到如同 `using namespace std;` 这样的语句，这个顾名思义，表示“使用 `std` 这个命名空间”。`std` 是 C++ 标准库的命名空间。使用了 `using` 语句后，我们就可以**直接**使用命名空间中的内容了，否则，则需要指明使用的**符号**来自于何命名空间，如 `std::cin`、`std::cout` 等等。

### `cin`、`cout`、`<<`、`>>`

C++ 有为我们提供的标准输入输出流，也就是 `cin`、`cout`。我们可以从输入流中**提取**需要的内容，`>>` 即为“流提取运算符”。比如我们想将从标准输入读入信息，存入“`a`”中，就可以使用如 `cin >> a`（注意箭头的方向）的语句。我们也可以把信息输出到标准输出流中，如 `cout << a`（注意体会箭头的方向）。

### `+`、`-`、`*`、`/`

C/C++ 中的 `+`、`-`、`*`、`/` 符号，分别对应着“加”“减”“乘”“除”四种操作。这些操作可以用于 C/C++ 的各种内建类型（built-in types）上。对于普通的数字类型的数据，这些符号对应的就是“加”“减”“乘”“除”操作。而得益于 C++ 中的“运算符重载”，我们可以赋予这些运算符新的含义。比如，“a”“b”表示两个集合，`a - b` 就可以表示两个集合的求差。

## C++ 代码中常见的语法

### 声明

#### 变量的声明

```cpp
int a;
float b = 12.3;
char c = 'a';
double d = 45.6;
```

代码中，如 `int`、`float` 这样的单词后，跟了一个单词，这叫做**声明**（declare）一个变量（variable）；如同 `int a;` 这样的语句，就是声明了一个 `int` 类型的、名称为 `a` 的变量。顾名思义，变量的值可以变化。当然，我们也可以把变量的声明，理解成“声明用来存储信息的空间”，而具体**存储什么类型的信息**（以及**以何种格式来读取信息**），则由**变量的类型**决定。

> 一般编程语言中，`int` 都代表 32 位带符号整型数，`float` 代表 32 位浮点数，`char` 用来存储字符，在 C/C++ 中长度为 8 位。关于这些基础变量类型（primitive types）具体的说明，这里暂时不展开介绍。
>
> 也有的编程语言不要求指明变量的类型，直接书写如同 `a = 1.1` 这样的语句，即可完成变量的声明以及**赋值**。

当我们想要声明多个元素的空间时，除了声明多个变量，我们也可以声明一个变量的**数组**。

```cpp
// 声明多个变量
int a1, a2, a3; 

// 声明一个数组
int a[3]; // 数组 a 具有 3 个 int 的空间

// 声明一个数组并且赋初始值：
int b[3] = {1,2,3};
```

数组可以通过**下标**访问：`a[0]` 为数组的 0 号元素，也是数组的第 1 个元素（我们也将这称为“C/C++ 中的数组从 0 开始索引”）。在内存中，数组是**一块连续的空间**。我们会在之后介绍数组的相较于单独声明变量的好处。

同样，我们也可以声明出存储字符串的空间。我们知道，字符串就是一串字符，因此我们可以用**字符的数组**来存储一个字符串。

```cpp
char str[6] = {'H','e','l','l','o','\0'};
```

上面的代码中，我们用 6 个 `char` 存储了一个单词“Hello”，以及一个用于**标记字符串结束**的“0 字符”——`\0`。“0 字符”的 ASCII 码为 0，所以我们也可以用数字 0 来表示“0 字符”。

像下面这样的写法也是可以的，因为编译器可以帮我们自动推断存储字符串需要的空间。

```cpp
char str[] = "Hello";
```

像上面两种，**声明一个字符数组**，并**赋初值**的方式在程序中存储的字符串，其内容是可以修改的。但是，我们需要注意，在修改时，所使用的空间，不能超过字符数组本身的大小。为此，一般我们会根据情况，选择声明一个较大的字符数组。

```c
char str[100] = "Hello";
```

以上的方式，称为 C（语言）风格的字符数组。

C/C++ 也允许我们声明其他类型的变量，通常这些变量由其他库提供，或者由用户自行设计定义。

比如，C++ 中存储字符串，一般使用 `string` 类型。这种类型内部采用了**动态内存分配**等设计方式，我们尽可以放心的进行字符串的操作，而不用担心超出预先分配的空间。

```cpp
string interj = "Hello";
string name = "Tom";
string sentence = interj + ", " + name + "!";
cout << sentence; // 输出 Hello, Tom!
```

#### 函数的声明

编程中的函数（function）一般是若干语句的集合。我们也可以将其称作“**子过程**（subroutine）”。函数可以接收若干值，这叫做函数的参数。函数也可以返回某个值，这叫做函数的返回值。

我们在编程中，如果有一些重复的过程，我们可以将其抽象出来，定义一个函数。

声明一个函数，我们需要返回值类型、函数的名称，以及参数列表。

```c
// 返回值类型 int
// 函数的名称 some_function
// 参数列表 int, int
int some_function(int, int);
```

如上图，我们声明了一个名为 `some_function` 的函数，它需要接收两个 `int` 类型的参数，返回值类型也为 `int`。可以认为，这个函数将会对传入的两个整数进行一些操作，并且返回一个同样类型的结果。

只有函数的声明（declaration）还不够，他只能让我们在调用时清楚函数的**接口**类型，但还不能使用，我们还需要函数的**定义**（definition）。我们可以在其他的任何地方**实现**（implement）这个函数（甚至可以是另外的文件，但是需要在分别编译后链接在一起）。

```c
int some_function(int, int);

/* some other code... */

int some_function(int x, int y) {
    int result = 2 * x + y;
    return result;
}
```

注意，在定义时，我们给函数的参数列表的变量起了名字，这样能让我们在定义中使用这些变量了。

函数通过 `return` 语句，将值返回给调用方。函数一旦执行到 `return` 语句，则直接结束当前函数，不再执行后续的语句。

如果是同一个文件中，我们也可以直接将声明和定义合并在一起。

```cpp
int some_function(int x, int y) {
    int result = 2 * x + y;
    return result;
    result = 3; // won't be executed
}

/* some other code... */

b = 1;
a = some_function(b, 12);
```

要调用（call）一个函数，直接用它的名字加上**括号**，里面填上参数即可。

如果函数不需要有返回值，我们可以将函数的返回值类型标为 `void`；如果不需要参数，我们也可以将参数列表置空。

```cpp
void say_hello() {
    cout << "hello!\n";
    cout << "hello!\n";
    cout << "hello!\n";
    return; 
    cout << "hello!\n"; // won't be executed
}
```

我们同样可以用 `return` 语句结束函数的执行。

特别的，每个 C/C++ 程序都需要有一个名为 `main` 的函数。任何程序都将从 `main` 函数开始运行。

下面是一个完整的 C++ 程序的代码：

```cpp
// hello.cpp

#include <iostream>

int main() {
    std::cout << "Hello!\n";
}
```

> 关于代码详细的解释，可以参考这个网页：[C++ "Hello World" Compiling - hacking C++](https://hackingcpp.com/cpp/hello_world.html) @ https://hackingcpp.com/cpp/hello_world.html
>
> `main` 函数也可以有参数，通过 `main` 函数的参数，我们可以获得外界传给这个程序的指令（也就是“命令行参数”），以便做出不同的反应。

下面是一个使用**子过程**的代码：

```cpp
// hello_subroutine.cpp

#include <iostream>

void say_hello() {
    cout << "hello!\n";
    cout << "hello!\n";
    cout << "hello!\n";
}

int main() {
    say_hello();
    say_hello();
}
```

#### 命名规则

最基础的规则就是，变量名或者函数名等要有意义，能够让读者快速明白变量或者函数的含义。

更加详细的命名规则我们会在之后的代码规范中讲解。

### 复杂数据类型（自定义数据类型）

#### 结构体

假如我们要存储 3 名同学的语文、数学、外语成绩，该怎么做呢？

要表明三个**数据是相关的**，我们可以将数据存放在一个数组里。然后，我们可以定义 3 个数组，每个数组有 3 个元素，分别是语文、数学、外语成绩。

```cpp
int susan[3] = {89, 90, 91};
int jason[3] = {95, 89, 90};
int kevin[3] = {92, 93, 94};
```

但是，假如我们要存储 20 个学生的成绩，很显然不能这样定义了。这时，我们有两种思路：

一是定义 3 个大小为 20 的数组，分别存储三门成绩：

```cpp
int chinese[20];
int math[20];
int english[20];
```

或者，我们可以定义一个数组的数组：

```cpp
int student_scores[3][20];
```

但假如我们要再假如一个项目，比如学生成绩的等级，这下我们就不能将同一个学生数据放在一个数组里了，因为 C/C++ 要求数组中必须是相同的数据。因此，“定义数组的数组”的方法也不再可行。不过我们仍然可以通过定义多个数组的方式来满足使用需求：

```cpp
int chinese[20];
int math[20];
int english[20];
char grade[20];
```

不过我们也可以看到，定义多个数组的方式，在语义上是割裂的——同一个学生的数据实际上存储在不同数组中，只能通过下标联系起来，比如，Susan 是 0 号学生，她的成绩分别存储在 `chineses[0]`、`math[0]` 和 `english[0]` 中。

在 C/C++ 中，用户可以将若干数据组合在一起，定义自己的数据类型，称为“**结构体**（struct）”。下面，是在 C++ 中定义一个结构体的语句：

```cpp
struct StudentScore {
    int chn;
    int math;
    int eng;
    char grade;
};
```

如此，我们便定义了 `StudentScore` 这种数据类型。我们可以像使用 `int`、`char` 那样，声明**结构体的数组**。

```cpp
StudentScore scores[20];
```

> 一个 `int` 占用 32 位空间，`char` 占用 8 位，因此我们的 `StudentScore` 会占用至少 $3 \times 32 + 8 = 104 $ 位的空间。之所以说“至少”，是因为，编译器可能将数据对齐（align）到整字节处。这样虽然多占用了一些空间，但是读写的效率会提高很多。

我们可以通过 `.` 运算符（成员关系运算符），来访问结构中的**成员**（member）：

```cpp
scores[0].chn   = 89;  // Susan's Chinese score
scores[0].math  = 90;  // Susan's Math score
scores[0].eng   = 91;  // Susan's English score
scores[0].grade = 'A'; // Susan's grade
```

> 对于计算机来说，一个结构体，不过是一个位数更多一点的数据段（data segment）。这也正是我们之前说的，“变量的类型，决定了声明出的空间种具体存储什么类型的信息，以及以何种格式来读取信息”。

#### 类

当我们想要在数据之上规定一些操作方法时，我们可以定义一个“类（class）”，当然，C++ 也允许我们在结构体中定义方法。两者从表面上看只有些微的不同，比如成员默认对外的的可见性。但是类和结构体还是有概念上的区别。一般来说，单纯的“数据 + 方法”，我们就用“结构体”来实现；而当一个结构比较复杂，其中的数据之间作用关系繁多，相对于单纯的数据条目来说更像是一个小系统或者黑盒时，我们则会采用“类”。

语言比较难以解释清楚两者的不同，我们来看具体例子。比如我们刚刚定义的 `StudentScore` 类型，我们只是单纯的把数据放在一起。现在假如我们需要加入计算总分的功能：

```cpp
struct StudentScore {
    int chn;
    int math;
    int eng;
    int calc_tot() { return chn + math + eng; }
};
```

于是，我们可以通过调用成员函数 `calc_tot` 来计算结构体中三个成员的和。

```cpp
StudentScore s{90, 90, 90};
int tot = s.calc_tot(); // tot: 270
```

理论上，我们可以用这个结构来计算任意三个数的和。我们甚至可以将这个结构体改名为 `ThreeInteger`：

```cpp
struct ThreeInteger {
    int int_1;
    int int_2;
    int int_3;
    int calc_tot() { return int_1 + int_2 + int_3; }
};


int main() {
    ThreeInteger a{12, 34, 56};
    int sum = a.calc_tot();
}
```

而类则更加封闭，通常，类提供一些接口来和外界交互。比如 `std::string` 类就是一个例子。我们完全不用关心它是怎么实现的动态内存分配，也不用关心它是怎么实现字符串的相加等等。我们只需要知道这些接口的含义和用法即可。

```cpp
#include <string>

int main() {
    std::string str = "Hello";
    int size = str.size();  // size: 6
    str = str + str;        // str: "HelloHello"
}
```

### 条件控制与循环

我们编程时，经常会需要根据不同的情况做出不同的选择，这就是“分支”。我们知道，CPU 是逐一执行指令的，若干指令是连续排列的，如果要实现根据不同情况执行不同的指令，或者重复执行一些命令，则需要使用命令告诉 CPU，使其**跳转**到之前或者之后的命令。这不得不说是很麻烦的。而高级语言为此设计了一些方便的语法。

#### `if`、`else`

顾名思义，`if` 意为“如果”，即满足一定条件才能执行相应的代码。`else` 可以和 `if` 配套使用，当不满足条件时，执行 `else` 块中的代码；`else` 块不是必要的，如果不需要可以忽略。

```cpp
// party-entrance.cpp

#include <iostream>

int main() {
    int age = 0;
    std::cout << "What's your age?\n";
    std::cin >> age;
    if (age < 16) {
        std::cout << "Sorry, you're too young.\n";
    } 
    else {
        std::cout << "Welcome to the party!\n";
    }
}
```

#### `for` 循环

常用的循环（loop）有`for` 循环和 `while` 循环。虽然使用 `for` 循环和 `while` 循环可以实现同样的效果，但 `for` 循环通常用于**确定数量**或**确定区间**的循环，比如执行确定次数目的语句，或者遍历（逐个访问）若干项。因此，`for` 循环需要**明确指定循环的起止**，如果不指定，则需要在循环内部判断退出条件，否则会陷入“死循环”（程序一直在循环中执行，不能退出）。

`for` 语句后面跟着一对括号 `()`，其中需要有两个分号，分割出共 3 条语句。第 1 条语句用来给**循环变量**赋初值；每次执行循环前都会执行第 2 条语句，用来判断循环是否继续进行——如果语句的真值为真，则继续，否则则终止循环；每次循环执行后会执行第 3 条语句，一般用来更新循环变量的值。

当然，我们可以在循环体外对循环变量赋初值，也可以在循环体内部更新循环变量的值。如果没有必要，可以将括号中的相应语句留空，但是分割语句用的分号不能省略。如果留空第 2 条语句，则相当于该语句的真值永真，如果没有其他的退出方式，程序一旦进入循环体，则将无法退出，形成死循环。

我们可以使用 `break;` 语句强行退出**当前层次**的循环；使用 `continue;` 语句强行结束当前次循环（进入下一次循环前，依旧要进行条件的判断）。

下面的例子使用 `for` 循环完成常见的两类操作：

```cpp
// for-loop.cpp

#include <iostream>

int main() {
    for (int i = 0; i < 10; i = i + 1) {
        std::cout << "I love C++! \n";
    }

    const int ARRAY_LENGTH = 5;
    int a[ARRAY_LENGTH] = {1, 2, 3, 4, 5};

    for (int i = 0; i < ARRAY_LENGTH; i = i + 1) {
        std::cout << a[i] << " ";
    }
}
```

这里也体现了使用**数组**的好处——我们可以通过循环来访问数组中的每个元素。

##### 区间 `for` 循环

C++ 11 带来了区间 `for` 循环（ranged for-loop）。这使我们可以更方便的**遍历**数据。

```cpp
// ranged-for-loop.cpp

#include <iostream>

int main() {
    int a[5] = {1, 2, 3, 4, 5};
    
    for (int val : a) {
        std::cout << val << " ";
    }
}
```

语句 `for (int val : a)` 可以解释成：对于 `a` 中的每一个元素，我们将其称为 `val`。每次循环，我们都可以通过 `val` 这个名字访问容器中的一个元素。

C++ STL（Standard Template Library，标准模板库）中提供有各种“容器”，模拟了常用的一些数据结构，可以用来存放数据。

之前我们说到，像 `int a[5];` 这样的语句声明的是一块**固定大小**的空间，而 `std::string` 这种类型采用动态内存分配，我们在使用时大可不必担心空间的问题。同样，STL 中有一种名为 `vector` 的容器，我们可以将其理解为“动态数组”，其内部有一定的机制，可以实现随着用户的使用而自动扩充空间，不必担心超出空间的问题。

```cpp
// for-loop-demo-with-vector.cpp

#include <vector>
#include <iostream>

int main() {
    std::vector<int> a; 
    // 'a' is a 'vector' of 'int's
    a.push_back(1); // a: 1
    a.push_back(2); // a: 1, 2
    a.push_back(3); // a: 1, 2, 3

    for (auto val : a) {
        std::cout << val << " ";
    }
    std::cout << "\n";

    a.pop_back(); // a: 1, 2
    a.pop_back(); // a: 1
    a.pop_back(); // a: <empty>

    std::cout << a.size();
}
```

注：`for (auto val : a)` 中的 `auto` 为“自动类型推断关键字”，也就是将推断类型的工作交给了编译器。合理的使用 `auto` 可以简化我们的代码编写——比如，同样的代码也能用于遍历存放 `float` 的 `vector` 容器。

#### `while` 循环

`while` 循环通常用于不定范围的循环——只要满足一个条件就一直执行。

```cpp
// while-loop-demo-with-stack.cpp

#include <vector>
#include <stack>
#include <iostream>

int main() {
    std::vector<int> a = {1, 2, 3, 4, 5};

    std::stack<int> s;

    for (auto val : a) { s.push(val); }
    // s: [] -> [1] -> [1, 2] -> ... -> [1, 2, 3, 4, 5]

    while (s.empty() == false) {
        auto val = s.top(); // 栈顶元素
        std::cout << val << " ";
        s.pop(); // pop: 弹出（栈顶元素）
    }
    std::cout << "\n";
    // s: [1, 2, 3, 4, 5] -> [1, 2, 3, 4] -> [1, 2, 3] -> ... -> []
}
```

语句 `s.empty() == false` 和 `!s.empty()` 是等价的。`!` 运算符表示对真值求反。这两个语句都表示“`s` 不为空（empty）”的含义。

##### `do while` 循环

有些时候，我们希望无论如何都执行（或者说，至少执行一次） `while` 循环中的语句，可以使用 `do while` 循环。

假如我们编写一个程序，不断获取用户输入，直到用户输入不满足条件后程序才会退出。

使用普通的 `while` 循环编写，我们可以采用不满足条件即跳出的方式：

```cpp
#include <iostream>

int main() {
    std::cout << "Input a integer less than 10 to quit.\n";
    int val;
    
    while (true) {
        std::cin >> val;
        std::cout << "You inputed " << val << "." << std::endl; // endl: end of line
        if (val > 10) {
            std::cout << val << " is less than 10. Bye! \n"; 
            break; // break 用于直接终止当前层的循环
        }
    }
}
```

由于我们无论如何都需要先获得一次用户的输入，于是我们可以采用 `do while` 循环：

```cpp
#include <iostream>

int main() {
    std::cout << "Input a integer less than 10 to quit.\n";
    int val;
    do {
        std::cin >> val;
        std::cout << "You inputed " << val << "." << std::endl;
    } while (val > 10);
    std::cout << val << " is less than 10. Bye! \n"; 
}
```

可以看到，采用了 `do while` 循环的代码更加简洁。

### 一些其他的小细节

在 `{} ` 包裹的代码块后，一般不需要加分号；但是，定义类和结构体的语句末则需要添加分号。另外，`do while` 语句后因为不是 `}` 结尾，所以也需要加分号。

因为 C++ 对语句之间分号的数量没有要求，如果不考虑美观要求，其实可以在任何不确定的地方加上分号 `;`。

## 结语

现在，你可以开始自己的学习之旅了。相信以上的内容能给你带来足够的知识！



> [C++ Beginner's Guide for Python/Java/... Programmers - hacking C++ - hackingcpp.com](https://hackingcpp.com/cpp/beginners_guide.html)
