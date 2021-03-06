## 理解在Go中的变量类型

### 由Gopher Guides撰写

>数据类型指定在编写程序时特定变量将存储的值的类型。数据类型还决定了可以对数据执行哪些操作。。
>
>在本文中，我们将讨论重要的本地to go数据类型。这不是对数据类型的详尽调查，但将帮助您熟悉在Go中可用的选项。理解一些基本数据类型将使您能够编写更清晰、执行效率更高的代码。


### 背景

>考虑数据类型的一种方法是考虑我们在现实世界中使用的不同类型的数据，现实世界中数据的一个例子是数字：例如我们可以使用数字（0，1，2），整数（-1，0，1）和无理数（π ）
>
>通常，在数学中，我们可以把不同类型的数字组合起来，得到某种答案。我们可能要加5π,例如:5 +π我们可以把方程的答案占无理数,或圆π小数点后的数字有一个缩写的编号,然后把这些数字加起来:5 +π= 5 + 3.14 = 8.14
>
>但是，如果我们开始尝试用另一种数据类型(比如单词)来计算数字，事情就变得不那么有意义了。我们如何解出下面这个方程?对于计算机来说，每种数据类型都是非常不同的——比如单词和数字。因此，我们必须注意如何使用不同的数据类型来分配值，以及如何通过操作操作它们。


### 整形
>与数学一样，计算机编程中的整数是整数，可以是正数、负数或0(…，-1,0,1，…)。在Go中，整数被称为整型数。和其他编程语言一样，你不应该在四位数或四位数以上的数字中使用逗号，所以当你在程序中写1000时，就写成1000。我们可以像这样简单地打印出一个整数:：

```
fmt.Println(-459)
```

输出：

```
-459
```

>或者，我们可以声明一个变量，在本例中，它是我们正在使用或操作的数字的符号，像这样:

```go
var absoluteZero int = -459 fmt.Println(absoluteZero)
```

输出：

```
-459
```

>我们也可以用Go中的整数做数学。在下面的代码块中，我们将使用：=赋值运算符来声明和实例化变量和：
```
sum := 116 - 68 fmt.Println(sum)
```
输出
```$xslt
48
```
> 如输出所示，数学运算符-从116中减去整数68，得到48。 您将在变量的声明数据类型部分了解更多关于变量声明的信息。 积分可以在Go程序中以多种方式使用。 当您继续学习Go时，您将有很多机会与整数一起工作，并在此数据类型的知识基础上再接再厉。


###  浮点数

>浮点数或浮点数用于表示不能表示为整数的实数。 实数包括所有有理数和无理数，正因为如此，浮点数可以包含分数部分，如9.0或-116.42。 为了在Go程序中思考浮点数，它是一个包含小数点的数字。

> 就像我们对整数所做的那样，我们可以这样简单地打印出一个浮点数：

```
fmt.Println(-459.67)
```

输出：

```
-459.67
```

> 我们还可以声明一个变量，它代表一个浮点数，比如：

```
absoluteZero := -459.67 fmt.Println(absoluteZero)
```

输出：

```
-459.67
```

> 就像整数一样，我们也可以用Go中的浮点数做数学：

```
var sum = 564.0 + 365.24 fmt.Println(sum)
```

输出：

```
929.24
```
>对于整数和浮点数，重要的是要记住3=3.0，因为3是指整数，而3.0是指浮点数。

###  数字类型的大小

> 除了整数和浮点数之间的区别外，Go还有两种类型的数字数据，它们通过其大小的静态或动态性质来区分。 第一种类型是与体系结构无关的类型，这意味着数据的位大小不会改变，不管代码运行的是哪台机器。。

> 今天大多数系统架构要么是32位，要么是64位。 例如，您可能正在为现代Windows笔记本电脑开发，操作系统在64位架构上运行。 但是，如果您正在开发像健身表这样的设备，您可能正在使用32位体系结构。 如果您使用像int32这样与体系结构无关的类型，而不管您编译的体系结构如何，该类型将具有恒定的大小。

> 第二种类型是特定于实现的类型。 在这种类型中，位大小可以根据程序构建的体系结构而变化。 例如，如果我们使用int类型，当Go编译32位体系结构时，数据类型的大小将是32位。 如果程序是为64位体系结构编译的，则变量的大小为64位。。

> 除了具有不同大小的数据类型外，像整数这样的类型也有两种基本类型：有符号和无符号。 一个int8是一个有符号整数，它的值可以从-128到127。 uint8是无符号整数，只能有0到255的正值。

> 范围基于位大小。 对于二进制数据，8位可以表示总共256个不同的值。 由于int类型需要同时支持正值和负值，所以8位整数(int8)的范围为-128到127，总共有256个唯一的可能值。

> Go具有以下与体系结构无关的整数类型：
>
```$xslt
uint8       无符号8位整数（0到255）
uint16      无符号16位整数（0到65535）
uint32      uint32无符号32位整数（0到4294967295） 
uint64      uint64无符号64位整数（0到18446744073709551615）
int8        有符号8位整数（-128到127）
int16       int16有符号16位整数（-32768到32767）
int32       int32有符号32位整数（-2147483648至2147483647）
int64       int64有符号64位整数（-9223372036854775808至9223372036854775807）
```

> 浮子和复数也有不同的大小：

```$xslt
float32      IEEE-75432位浮点数
float64      IEEE-75464位浮点数
complex64    复数与浮点32实部和虚部 
complex128   复数与浮点64实部和虚部
```

> 还有几种别名类型，它们为特定数据类型分配有用的名称：

```$xslt
byte         uint8的别名 
rune         字节别名的目的是使它 
```
>字节别名的目的是明确当您的程序使用字节作为字符串元素中的常见计算度量时，而不是与字节数据无关的小整数
  测量。 即使在程序编译后，字节和uint8是相同的，字节通常用于以数字形式表示字符数据，而uint8则打算成为程序中的一个数字。

>符文别名有点不同。 其中byte和uint8完全相同的数据，一个符文可以是一个字节，也可以是四个字节，的范围。 符文用于表示Unicode字符，而只有ASCII字符只能由int32数据类型表示。

> 此外，Go具有以下特定于实现的类型：

```$xslt
uint     无符号，32位或64位
int      有符号，32位或64位
uintptr  无符号整数大到足以存储指针值的未解释位
```
>特定于实现的类型将由程序编译的体系结构定义它们的大小。

###  选择数字数据类型

> 选择正确的大小通常与您正在编程的目标体系结构的性能有关，而不是与您正在处理的数据的大小有关。 但是，在不需要知道性能对您的程序的具体影响的情况下，您可以在开始时遵循这些基本指南。

>正如本文前面所讨论的，有独立于体系结构的类型和特定于实现的类型。 对于整数数据，在Go中通常使用int或uint等实现类型，而不是int64或uint64。 这通常会为目标体系结构带来最快的处理速度。 例如，如果您使用int64并编译为32位体系结构，那么处理这些值至少需要两倍的时间，因为在体系结构中移动数据需要额外的CPU周期。 如果使用int，程序将把它定义为32位体系结构的32位大小，并且处理速度会大大加快。


> 如果您知道您不会超过特定的大小范围，那么选择与体系结构无关的类型既可以提高速度，也可以减少内存使用。 例如，如果您知道您的数据不会超过100的值，并且只会是一个正数，那么选择uint8将使您的程序更有效，因为它需要更少的内存。

### 溢出与环绕

> 当您试图存储一个大于设计用于存储的数据类型的值时，Go有可能同时溢出一个数字并环绕一个数字，这取决于该值是在编译时还是在运行时计算的。 当程序在试图构建程序时发现错误时，会发生编译时间错误。 运行时错误发生在程序编译后，而它实际上正在执行。

> 在下面的示例中，我们将maxUint32设置为其最大值：
>
```
package main

import "fmt"

func main() 
{   
    var maxUint32 uint32 = 4294967295 // 最大无符号32位  
    fmt.Println(maxUint32) 
}
```

> 它将编译并运行以下结果：

输出:
```
4294967295
```

> 如果我们在运行时将1添加到值中，它将被包装为0：

输出:
```
0
```
> 另一方面，让我们在编译时间之前，将程序更改为在变量中添加1：


```go
package main

import "fmt"

func main() 
{   
    var maxUint32 uint32 = 4294967295 + 1   
    fmt.Println(maxUint32)
}
```

> 在编译时，如果编译器能够确定一个值将太大，无法保存在指定的数据类型中，它将抛出溢出错误。 这意味着计算的值对于您指定的数据类型来说太大了。

> 因为编译器可以确定它会溢出这个值，所以它现在会抛出一个错误：


输出：

prog.go
```go
6:36: constant 4294967296 overflows uint32
```

> 了解数据的边界将帮助您在未来避免程序中的潜在错误。  

> 现在我们已经讨论了数字类型，让我们看看如何存储布尔值。


### 布尔型
>布尔数据类型可以是true或false两个值之一，在声明为数据类型时定义为bool。 布尔值被用来表示与数学逻辑分支相关的真值，它为计算机科学中的算法提供信息。

> 值true和false将始终分别具有小写t和f，因为它们是Go中预先声明的标识符。

> 数学中的许多运算给我们的答案是正确的或错误的：
* 大于
    - 500 > 100 true 
    - 1 > 5 false
* 小于
    - 200 < 400 true 
    - 4 < 2 false
* 等于
    - 5 = 5 true 
    - 500 = 400 false

> 就像数字一样，我们可以在变量中存储一个布尔值：

`myBool := 5 > 8`     
>然后，我们可以用函数fmt.Println()来打印布尔值：

`fmt.Println(myBool)`

> 由于5不大于8，我们将收到以下输出：

输出:
`false`

### 字符串

>  字符串是一个或多个字符（字母、数字、符号）的序列，可以是常量或变量。 字符串存在于Go中的后引号`或双引号”中，并且根据您使用的引号具有不同的特性。

> 如果使用后引号，则创建原始字符串文字。 如果使用双引号，则创建一个解释字符串文字。

#### 原始字符串文字

> 原始字符串文字是背引号之间的字符序列，通常称为背蜱。 在引号中，任何字符都会出现，就像它显示在后面的引号之间一样，除了后面的引号字符本身。

``a := `Say "hello" to Go!` fmt.Println(a)``

输出:

```
Say "hello" to Go!
```

>通常，反斜杠用于表示字符串中的特殊字符。 例如，在解释字符串中，\n将表示字符串中的新行。 然而，反斜杠在原始字符串文字中没有特殊的含义：

```go
a := `Say "hello" to Go!\n` fmt.Println(a)
```

> 因为反斜杠在字符串文字中没有特殊的含义，它实际上会打印出\n的值，而不是新建一行：

输出:

```
Say "hello" to Go!\n
```

> 原始字符串文字也可用于创建多行字符串：

```go
a := `This string is on multiple lines within a single back quote on either side.` fmt.Println(a)
```

输出：

```
This string is on  multiple lines within a single back  quote on either side.
```

> 在前面的代码块中，新行从输入到输出的字面意义。

#### 解释的字符串文本
>解释字符串文本插入字符串文本是双引号之间的字符序列，如“bar”。在引号内，除换行符和非转义双引号外，可以出现任何字符。要在解释字符串中显示双引号，可以将反斜杠用作转义字符，如下所示：


```go
a := "Say \"hello\" to Go!" fmt.Println(a)
```

输出:

`Say "hello" to Go!`
>您几乎总是使用解释字符串文字，因为它们允许转义字符在其中。有关使用字符串的更多信息，请查看Go中[使用字符串的介绍](https://www.digitalocean.com/community/tutorials/an-introduction-to-working-with-strings-in-go)。

#### 带UTF-8字符的字符串
>UTF-8是一种编码方案，用于将可变宽度字符编码为1到4个字节。Go支持现成的UTF-8字符，不需要任何特殊的设置、库或包。罗马字符（如字母A）可以用ASCII值（如数字65）表示。但是，对于特殊字符，如国际字符世，则需要UTF-8。Go对UTF-8数据使用rune别名类型。

`a := "Hello, 世界"`

>可以在for循环中使用range关键字索引Go中的任何字符串，甚至是UTF-8字符串。for循环和range将在本系列后面更深入地讨论；现在，重要的是要知道我们可以使用它来计算给定字符串中的字节数：

```go
package main
import "fmt"
func main() 
{   
    a := "Hello, 世界"   
    for i, c := range a {       
        fmt.Printf("%d: %s\n", i, string(c))   
    }   
    fmt.Println("length of 'Hello, 世界': ", len(a)) 
}
```

>在上面的代码块中，我们声明了变量a并为其赋值Hello，世界。指定的文本中包含UTF-8字符。

>然后我们使用标准的for循环以及range关键字。在Go中，range关键字将索引一次返回一个字符的字符串，以及该字符在字符串中的字节索引。

>使用 fmt.Printf 函数，我们提供了格式字符串%d:%s\n.%d是数字的打印谓词（在本例中是整数），%s是字符串的打印谓词。然后我们提供i的值，它是for循环的当前索引，c是for循环中的当前字符。

>最后，我们使用内置len函数打印变量a的整个长度。

>前面我们提到过rune是int32的别名，可以由1到4个字节组成。世字符需要三个字节来定义，并且索引在UTF-8字符串范围内进行相应的移动。这就是我打印出来时没有顺序的原因。

输出：

```go
0: H
 1: e 
2: l 
3: l 
4: o 
5: , 
6: 
7: 世 
10: 界 
length of 'Hello, 世界':  13

```

>正如您所看到的，这个长度比它在字符串范围内所用的次数要长。

>您不一定总是使用UTF-8字符串，但是当您使用UTF-8字符串时，您将了解它们为什么是符文而不是一个int32。

### 声明变量的数据类型
>现在您已经了解了不同的原始数据类型，接下来我们将讨论如何在go中将这些类型分配给变量。

>在Go中，我们可以定义一个带有关键字var的变量，后跟变量的名称和所需的数据类型。

>在下面的示例中，我们将声明一个名为pi的float64类型的变量。

>关键字var是声明的第一件事：

`var pi float64` 

>后面是变量的名称pi：

`var pi float64
`

>最后是数据类型float64：


`var pi float64
`

>我们也可以选择指定初始值，例如3.14：

`var pi float64 = 3.14
`

>Go是一种静态类型语言。静态类型化意味着在编译时检查程序中的每个语句。这也意味着数据类型绑定到变量，而在动态链接语言中，数据类型绑定到值。

>例如，在Go中，声明变量时声明类型：

```
    var pi float64 = 3.14 
    var week int = 7
```

>如果声明不同，这些变量中的每一个都可能是不同的数据类型。

>这与PHP等语言不同，PHP的数据类型与值相关联：

```php
$s = "sammy";         // $s 直接自动是字符串类型
$s = 123;             // $s i直接自动是整数类型
```

>在前面的代码块中，第一个$s是一个字符串，因为它被赋值为“sammy”；第二个是一个整数，因为它的值是123。

>接下来，让我们看看更复杂的数据类型，比如数组。

### 数组
>数组是元素的有序序列。阵列的容量在创建时定义。一旦一个数组分配了它的大小，它的大小就不能再改变了。因为数组的大小是静态的，这意味着它只分配一次内存。这使得数组在某种程度上难以使用，但提高了程序的性能。因此，在优化程序时通常使用数组。接下来介绍的切片更灵活，它构成了其他语言中您认为的数组。

>数组是通过声明数组的大小来定义的，然后是在花括号{}之间定义值的数据类型。

>字符串数组如下所示：

`[3]string{"blue coral", "staghorn coral", "pillar coral"}`

>我们可以将数组存储在变量中并打印出来：

`coral := [3]string{"blue coral", "staghorn coral", fmt.Println(coral)`

输出:

`[blue coral staghorn coral pillar coral]
`

>如前所述，切片类似于数组，但更灵活。让我们来看看这个可变的数据类型。

### 切片
>切片是元素的有序序列，其长度可以改变。切片可以动态增加其大小。在向切片添加新项时，如果切片没有足够的内存来存储新项，它将根据需要从系统请求更多内存。因为切片可以在需要时展开以添加更多元素，因此它们比数组更常用。

>切片是通过声明数据类型来定义的，数据类型前面有一个左右方括号[]，并且值在花括号{}之间。

>整数片段如下所示：

`[]int{-3, -2, -1, 0, 1, 2, 3}`

>浮点数片段如下所示：

`[]float64{3.14, 9.23, 111.11, 312.12, 1.05}
`

>字符片段如下所示：

`[]string{"shark", "cuttlefish", "squid", "mantis sh"}
`

>让我们把我们的弦片段定义为海洋生物：

`seaCreatures := []string{"shark", "cuttlefish", "squid", "mantis shrimp"}`

>我们可以通过调用变量将它们打印出来：

`fmt.Println(seaCreatures)`

>输出将与我们创建的列表完全相同：

输出:

`[shark cuttlefish squid mantis shrimp]`

>我们可以使用append关键字将项添加到切片中。以下命令将向切片中添加seahorse的字符串值：

`seaCreatures = append(seaCreatures, "seahorse")`

>您可以通过打印出来验证它是否已添加：

`fmt.Println(seaCreatures)`

输出:

`
 [shark cuttlefish squid mantis shrimp seahorse]`

>如您所见，如果您需要管理未知大小的元素，则切片将比数组更通用。

### 映射
>映射是Go的内置哈希或字典类型。映射将键和值作为一对来存储数据。这在编程中很有用，可以通过索引或在本例中使用键快速查找值。例如，您可能希望保存一个用户映射，并按其用户ID编制索引。键将是用户ID，用户对象将是值。映射的构造方法是使用关键字map，后跟方括号[]中的键数据类型，后跟大括号中的值数据类型和键值对。

`map[key]value{}`

>通常用于保存相关的数据，例如ID中包含的信息，映射如下所示:

```
map[string]string{"name": "Sammy", "animal": "shark", "color": "blue", "location": "ocean"} 
```

>您会注意到，除了大括号之外，整个映射中还有冒号。冒号左边的单词是键。在Go中，键可以是任何可比较的类型。可比类型是基本类型，如字符串、int等。基本类型是由语言定义的，而不是通过组合任何其他类型而构建的。虽然它们可以是用户定义的类型，但最好保持它们的简单性以避免编程错误。上面字典里的关键字是：名字、动物、颜色和位置。

>冒号右边的单词是值。值可以由任何数据类型组成。上面字典中的值是：Sammy、shark、blue和ocean。

>让我们将映射存储在变量中并打印出来：

```go
sammy := map[string]string{"name": "Sammy", "animal": "shark", "color": "blue", "location": "ocean"}
fmt.Println(sammy)
```

输出:

`map[animal:shark color:blue location:ocean name:Sammy]`

>如果我们想隔离Sammy的颜色，可以通过调用Sammy[“color”]来实现。我们把它打印出来：

`fmt.Println(sammy["color"])`

输出：

`blue`

>由于映射提供用于存储数据的键值对，因此它们可能是Go程序中的重要元素。

 主包装
``go run greeting.go``

>这次，在输入名称并按Enter之后，您将获得预期的输出：

输出：

```bash
    >"Please enter your name."
    >Sammy
    >"Hi, Sammy! I'm Go!"
```

>现在，您有了一个Go程序，该程序可以接受用户的输入并将其打印回屏幕。

### 结论

>此时，您应该更好地了解一些可供您在Go中使用的主要数据类型。在用Go语言开发编程项目时，这些数据类型中的每一种都将变得非常重要。

>一旦掌握了Go中可用的数据类型，就可以学习如何转换数据类型，以便根据情况更改数据类型。