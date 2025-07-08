# Go 语言入门

## 先决条件

- **一些编程经验。**这里的代码相当简单，但了解一些函数知识会很有帮助。
- **一款用于编辑代码的工具。**任何文本编辑器都可以使用。大多数文本编辑器都对 Go 语言支持良好。最受欢迎的是 VSCode（免费）、GoLand（付费）和 Vim（免费）。
- **命令终端。Go**可以在 Linux 和 Mac 上的任何终端以及 Windows 上的 PowerShell 或 cmd 上顺利运行。

## 下载并安装 Go 语言

1. 下载连接 : https://go.dev/doc/install

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=MzRhZTI4Y2JiNTU1ZTllMGZiMmFjYTVhMWEzOTVkZTNfNUQ0THhzWElrbnZ4aGN4TVRSRkxVdmY4VE1INjhTRTJfVG9rZW46SjNOV2JJdVdXb0I0dEh4aDd4UmNqcGVYbkdmXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=YzUyOGYyMmFlMzQ0Y2VlZmY5YjE3ZGExNzU5ZTg0ZWRfYmQ2aWFJTDkxT0l4bTdGUEFjbkN5MzhyWHFkMzVNdmxfVG9rZW46RFp3ZmJYNEltb1FIdjl4QVNISmNMdzNiblpmXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

选择 **go1.24.4.Windows-amd64.msi** , 适用于 64 位操作系统.

然后点击下载好的软件包进行安装 :

1. 验证您是否已安装 Go

> 在**Windows**中，单击**“开始”**菜单。
>
> 在菜单的搜索框中，输入`cmd`，然后按 **Enter**键。
>
> 在出现的命令提示符窗口中，键入以下命令：
>
> go version
>
> 确认该命令打印已安装的 Go 版本。

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=NTZiYTBhMjRiOTllNDc4MzEzNjIyNGEyYzQyNGIxYmJfMGFZTGxnVzA4NFNZWjBTOENjaW53eTlUcVBJc0pQWVVfVG9rZW46QThxQmJDcEwzb2ZZZ3h4RDdka2N0UTdIblpjXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

## 编写代码

从 Hello, World 开始。

1. 打开命令提示符并 cd 到您的主目录。
2. 为您的第一个 Go 源代码创建一个 hello 目录。

例如，使用以下命令：

```Shell
mkdir hello
```

1. 为您的代码启用依赖项跟踪。

当你的代码导入其他模块中的包时，你可以通过代码自身的模块来管理这些依赖项。该模块由 go.mod 文件定义，该文件跟踪提供这些包的模块。该文件与你的代码（包括源代码仓库）一起保存。

要通过创建 go.mod 文件来为您的代码启用依赖项跟踪，请运行该 `go mod init`命令，并为其提供代码所在模块的名称。该名称是模块的模块路径。

在实际开发中，模块路径通常是保存源代码的仓库位置。例如，模块路径可能是`github.com/mymodule`。如果您计划发布模块供其他人使用，则模块路径*必须*是 Go 工具可以从中下载模块的位置。

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=ZDUyZGU1ODI4MjFmMGQwYmU3NzU2MmFjNzE2ZDQwOTFfTUdSVkRINlcxdXBzdU56RzVTc1Y1ZjdtSUJIeXo5eG9fVG9rZW46VHFTVmJCRGVHb3JGa1d4a040NGNHOE1rblhlXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

1. 在文本编辑器中，创建一个文件 hello.go 来编写代码。

```Shell
notepad hello.go
```

1. 将以下代码粘贴到您的 hello.go 文件中并保存该文件。

```Go
package main

import "fmt"

func main() {
    fmt.Println("Hello, World!")
}
```

这是你的 Go 代码。在此代码中，你：

- 声明一个`main`包（包是一种对函数进行分组的方式，它由同一目录中的所有文件组成）。
- 导入常用 `fmt包`，其中包含用于格式化文本（包括打印到控制台）的函数。此包是 安装 Go 时获得的 [标准库包之一。](https://pkg.go.dev/std)
- 实现一个`main`函数，用于将消息打印到控制台。`main`运行`main`包时，该函数会默认执行。

1. 运行您的代码来查看问候语。

```Go
$ go run .
Hello, World!
```

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=MDAxZjI2ZjcyYTI0MWYzZGM4MDM2NTdkOTBkZDY1OGVfUVhRdkkxNVJzTUNVZXpaN0pHamh5ZzNnaWJTTXZYVlRfVG9rZW46TG9DeWI0dXlnb085Mzl4alpCMmNGT1dGbmdoXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

## 调用外部包中的代码

当您需要自己的代码执行其他人可能已经实现的操作时，您可以寻找一个包含您可以在代码中使用的功能的包。

1. 使用外部模块的功能使打印的消息更有趣。
   1. 访问 pkg.go.dev 并 [搜索“quote”包](https://pkg.go.dev/search?q=quote)。
   2. 在搜索结果中，找到并单击该包的 v1 `rsc.io/quote`（它应该与的“其他主要版本”一起列出`rsc.io/quote/v4`）。
   3. 在**“文档”部分的“索引”**下，记下您可以从代码中调用的函数列表。您将使用这些 `Go`函数。
   4. 在此页面的顶部，请注意包`quote`包含在`rsc.io/quote`模块中。

您可以使用 pkg.go.dev 网站查找已发布的模块，这些模块的软件包中包含您可以在自己的代码中使用的函数。软件包以模块的形式发布，`rsc.io/quote`以便其他人使用。模块会随着时间的推移不断改进，并推出新版本，您可以升级代码以使用改进的版本。

1. 在您的 Go 代码中，导入`rsc.io/quote`包并添加对其`Go`函数的调用。

添加突出显示的行后，您的代码应包含以下内容：

```Go
package main

import "fmt"

import "rsc.io/quote"

func main() {
    fmt.Println(quote.Go())
}
```

1. 添加新的模块要求和总数。

Go 会将该`quote`模块添加为依赖项，并添加一个用于验证该模块的 go.sum 文件。

```Go
$ go mod tidy 
go：查找包 rsc.io/quote 的模块
go：在 rsc.io/quote v1.5.2 中找到 rsc.io/quote
```

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=YWU2NTJjMjllYTY4ZDk2NDZlYTc1ZDU5OWUwZmU0ODdfbGU2YUdRamJRRzhROGduVXdoeDRPS3kyOGdUempNTzJfVG9rZW46RjBrdGJvVWFlb2t1Z3V4NlhQb2NBR3BibnFoXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

可以设置使用国内的 Go 代理，像 [Goproxy.cn](https://goproxy.cn/) 或者阿里云代理，以此来解决连接超时的问题。在命令提示符中执行以下命令：

```Go
go env -w GOPROXY=https://goproxy.cn,direct
```

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=OTc3YjY5NDVkZWEzODQ1OWQ2YjUwNWExMjQzNThhOGJfOXRwUXJxdkFzTUtlQnhXUndVNHJGTmNDY21Hc2NacTNfVG9rZW46TDU4ZGI2M0Zub0FGOG14SFoyZGNCeEUwblpmXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

1. 运行您的代码以查看您所调用的函数生成的消息。

```Go
$ go run .
不要通过共享内存进行通信，而要通过通信来共享内存。
```

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=NWM3MTcwNTRmYzk5YjkxYjJhNWUwZjhjODFiMzQ1YTNfek41aFY1VUw1c0lJcUxwRGdWYVVqUVREQ3pJZ0w4T3VfVG9rZW46WmJnZmJvdlNnb1JGSlF4UnlGS2NCR3drblBlXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

请注意，您的代码调用该`Go`函数，打印有关通信的巧妙消息。

当你运行 时`go mod tidy`，它会定位并下载 `rsc.io/quote`包含你导入的包的模块。默认情况下，它会下载最新版本——v1.5.2。

# 创建 Go 模块

在本教程中，您将创建两个模块。第一个模块是一个库，旨在供其他库或应用程序导入。第二个模块是一个调用方应用程序，它将使用第一个模块。

本教程的序列包括七个简短的主题，每个主题都说明了语言的不同部分。

1. 创建模块——编写一个小模块，其中包含可以从另一个模块调用的功能。
2. [从另一个模块调用您的代码](https://go.dev/doc/tutorial/call-module-code.html)——导入并使用您的新模块。
3. [返回并处理错误](https://go.dev/doc/tutorial/handle-errors.html)——添加简单的错误处理。
4. [返回随机问候语](https://go.dev/doc/tutorial/random-greeting.html)——处理切片中的数据（Go 的动态大小数组）。
5. [向多人回复问候](https://go.dev/doc/tutorial/greetings-multiple-people.html) ——将键/值对存储在映射中。
6. [添加测试](https://go.dev/doc/tutorial/add-a-test.html)——使用 Go 的内置单元测试功能来测试您的代码。
7. [编译并安装应用程序](https://go.dev/doc/tutorial/compile-install.html)——在本地编译并安装您的代码。

## 先决条件

- **一些编程经验。**这里的代码非常简单，但了解一些函数、循环和数组的知识会很有帮助。
- **一款用于编辑代码的工具。**任何文本编辑器都可以使用。大多数文本编辑器都对 Go 语言支持良好。最受欢迎的是 VSCode（免费）、GoLand（付费）和 Vim（免费）。
- **命令终端。Go**可以在 Linux 和 Mac 上的任何终端以及 Windows 上的 PowerShell 或 cmd 上顺利运行。

## 启动一个其他人可以使用的模块

首先创建一个 Go 模块。在模块中，您可以收集一个或多个相关的包，用于实现一组独立且实用的功能。例如，您可以创建一个包含财务分析函数的模块，以便其他编写财务应用程序的人可以使用您的成果。有关开发模块的更多信息，请参阅 [开发和发布模块](https://go.dev/doc/modules/developing)。

Go 代码被分组到包中，包又被分组到模块中。模块指定了运行代码所需的依赖项，包括 Go 版本以及它所需的其他模块集。

当您添加或改进模块中的功能时，您可以发布模块的新版本。编写调用模块中函数的代码的开发者可以导入模块的更新包，并在新版本投入生产使用之前进行测试。

这一次我使用 VSCode 来进行编写代码 :

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=OWEzYjEyNTQ4NWU5MDAxMTQxZTExZjE4MzA2ODcwMDFfZXI4YVY1MUZVekcyb0pDeTlFZ2pLUXRhNEpyNkNNc09fVG9rZW46SWhVZGJDcGozb1h6UFB4Mld4eWNmSXRXblpnXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

下载好扩展

1. `greetings`为您的 Go 模块源代码 创建一个目录。
2. `go mod init使用命令` 启动您的模块 。

运行该`go mod init`命令，并指定模块路径——此处使用`example.com/greetings`。如果您发布模块，则此路径*必须*是 Go 工具可以下载模块的路径。该路径应为您的代码仓库。

有关使用模块路径命名模块的更多信息，请参阅 [管理依赖项](https://go.dev/doc/modules/managing-dependencies#naming_module)。

```Go
$ go mod init example.com/greetings 
go: 创建新的 go.mod: 模块 example.com/greetings
```

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=OGQyZTVkNDgxM2Y3NmNiMDNiNTBmNDM2N2UyNGIwZTVfRWFKQ1dOR1lXUFN5MjlEMkVhRkhIWkFQUWZDRnBFZXJfVG9rZW46TldrVGJhdzlGb2UyWHl4bng4R2MyVDA5bkhmXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

该`go mod init`命令会创建一个 go.mod 文件来跟踪代码的依赖项。目前为止，该文件仅包含模块名称和代码支持的 Go 版本。但是，随着依赖项的添加，go.mod 文件将列出代码所依赖的版本。这使得构建可重复，并让您直接控制要使用的模块版本

1. 在文本编辑器中，创建一个文件来编写代码，并将其命名为greetings.go。
2. 将以下代码粘贴到您的greetings.go文件中并保存该文件。

```Go
package Greetings 

import "fmt" 

// Hello 返回对指定人员的问候。
func Hello(name string) string { 
    // 返回将姓名嵌入消息中的问候语。
    message := fmt.Sprintf("Hi, %v. Welcome!", name) 
    return message 
}
```

这是模块的第一段代码。它会向任何请求问候的调用者返回问候语。下一步，你将编写调用此函数的代码。

在此代码中，您：

- 声明一个`greetings`包来收集相关函数。
- 实现一个`Hello`函数来返回问候语。
- 此函数接受一个`name`类型为 的参数 `string`。该函数还返回一个`string`。在 Go 中，名称以大写字母开头的函数可以被不在同一包中的函数调用。

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=ZDEzNjUwZjgzOThkMzJjYzIyNGU5Y2UwOWVlOTgzMWRfa1NNNkRhMDVZOGdVbWhoR3BOSjZKb0xReGtaWVFiU3RfVG9rZW46WmF0NWJsYWFNb25yMGt4bXl2bGM0SW9jbkFnXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

- 这在 Go 中称为导出名称。有关导出名称的更多信息，请参阅 Go 导览中的 [导出名称。](https://go.dev/tour/basics/3)
- 声明一个`message`变量来保存您的问候语。
- 在 Go 中，`:=`运算符是一种快捷方式，用于在一行内声明并初始化变量（Go 使用右侧的值来确定变量的类型）。更简单的方法是，你可以这样写：

```Go
var message string 
message = fmt.Sprintf("嗨，%v。欢迎！", name)
```

- 使用`fmt`包中的[函数](https://pkg.go.dev/fmt/#Sprintf)创建问候消息。第一个参数是格式字符串，它将参数的值替换为格式动词。插入参数的值即可完成问候文本。 `Sprintf``Sprintfname%vname`
- 将格式化的问候语文本返回给呼叫者。

在下一步中，您将从另一个模块调用此函数。

## 从另一个模块调用您的代码

1. 为你的 Go 模块源代码创建一个`hello`目录。你将在这里编写调用者。

创建此目录后，您应该在层次结构的同一级别上同时拥有 hello 和 greets 目录，如下所示：

```Go
<主页>/
 |-- 问候/
 |-- 你好/
```

1. 为您即将编写的代码启用依赖关系跟踪。

要为您的代码启用依赖项跟踪，请运行 `go mod init命令`，并为其提供代码所在模块的名称。

出于本教程的目的，使用`example.com/hello` 模块路径。

```Go
$ go mod init example.com/hello
go：创建新的 go.mod：模块 example.com/hello
```

1. 在文本编辑器的 hello 目录中，创建一个文件来编写代码，并将其命名为 hello.go。
2. 编写代码来调用该`Hello`函数，然后打印该函数的返回值。

为此，请将以下代码粘贴到 hello.go 中。

```Go
package main

import (
    "fmt"

    "example.com/greetings"
)

func main() {
    // Get a greeting message and print it.
    message := greetings.Hello("Gladys")
    fmt.Println(message)
}
```

1. 在此代码中，您：

   1. 声明一个`main`包。在 Go 中，作为应用程序执行的代码必须位于`main`包中。
   2. 导入两个包：`example.com/g``reetings`和`fmt包`。这样你的代码就可以访问这两个包中的函数。导入 `example.com/greetings`（你之前创建的模块中包含的包）可以让你访问`Hello` 函数。你还可以导入`fmt`，其中包含用于处理输入和输出文本（例如将文本打印到控制台）的函数。
   3. `greetings`通过调用包的 函数 来获取问候`Hello`。

2. 编辑`example.com/hello`模块以使用您的本地 `example.com/greetings`模块。

3. 对于生产环境，您需要`example.com/greetings` 从模块的仓库发布该模块（模块路径应与发布位置一致），以便 Go 工具能够找到并下载该模块。目前，由于您尚未发布该模块，因此需要对其进行调整，使其能够在本地文件系统上 `example.com/hello`找到 代码。`example.com/greetings`

4. 为此，使用 `go mod edit命令`编辑`example.com/hello` 模块以将 Go 工具从其模块路径（模块不在的位置）重定向到本地目录（模块所在的位置）。

   1. 从 hello 目录中的命令提示符运行以下命令：

   2. ```Go
      go mod edit -replace example.com/greetings=../greetings
      ```

该命令指定`example.com/greetings`应将 替换为 ，`../greetings`以便定位依赖项。运行该命令后，hello目录中的go.mod文件应包含一条[指令](https://go.dev/doc/modules/gomod-ref#replace)： `replace`

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=YjI3ZWJlOTQ1MzE0MzY0NTRmMzE2MzFkMTRlMWYwYTNfcmxFZ1VxOEtQUUtiOWJhOEIyZjh4Q3Z3aWM1VzFiSDdfVG9rZW46WEcxdmJ3cHFVb3Zsczd4TDh0MGM2dlNUblFGXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

1. 从 hello 目录中的命令提示符运行 [命令](https://go.dev/ref/mod#go-mod-tidy)来同步 模块的依赖项，添加代码所需但尚未在模块中跟踪的依赖项。 `go mod tidy``example.com/hello`

命令完成后，`example.com/hello` 模块的 go.mod 文件应如下所示：

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=OTYyYTk5YTRhOGU2ODExNjhiOTcxMTNmZDAwMzJjOWFfTEdySmpFdG91SVpGb3ljQ2xEQUNud2JMdThSZkF2blNfVG9rZW46QmhyS2JveEtjbzFTV0h4aVpZZGN5MzNybkZnXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

 该命令在 greets 目录中找到了本地代码，然后添加了一条`require 指令`来指定`example.com/hello` 需要的依赖项`example.com/greetings`。您`greetings`在 hello.go 中导入包时创建了此依赖项。

 模块路径后面的数字是*伪版本号* ——用来代替语义版本号（模块尚无）的生成数字。

 要引用*已发布的*模块，go.mod 文件通常会省略该`replace`指令，并 `require`在末尾使用带有标记本号的指令。

 有关版本号的更多信息，请参阅 [模块版本编号](https://go.dev/doc/modules/version-numbers)。

1. 在目录中的命令提示符下`hello`，运行您的代码以确认其有效。

```Go
go rnun .
```

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=M2FkZTJiNjVlNjNiMTdmYmM1YjA1MDc0OGFiMzliY2ZfMFVtbnpJRHlyVFhrR2ZpdnZjckRFTURBMklpNFJHem1fVG9rZW46WHBCVmJUbHVCb0NyVGd4UXBZTmNJVzZKbmxiXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

# 返回并处理错误

1. 在greetings/greetings.go中，添加下面突出显示的代码。

如果您不知道该问候谁，那么回复问候就毫无意义。如果名称为空，则向调用者返回错误。将以下代码复制到greetings.go并保存文件。

```Go
package greetings

import (
    "errors"
    "fmt"
)

// Hello returns a greeting for the named person.
func Hello(name string) (string, error) {
    // If no name was given, return an error with a message.
    if name == "" {
        return "", errors.New("empty name")
    }

    // If a name was received, return a value that embeds the name
    // in a greeting message.
    message := fmt.Sprintf("Hi, %v. Welcome!", name)
    return message, nil
}
```

在此代码中，您：

- 修改函数，使其返回两个值： a `string`和 an `error`。调用者将检查第二个值以判断是否发生错误。（任何 Go 函数都可以返回多个值。更多信息，请参阅 [《Effective Go](https://go.dev/doc/effective_go.html#multiple-returns)》。）
- 导入Go标准库`errors`包以便使用其 `errors.New功能`。
- 添加一个`if`语句来检查请求是否无效（名称应为空字符串），如果请求无效，则返回错误。该`errors.New`函数返回一个 `error`包含您消息的 。
- 在成功返回时添加`nil`（表示没有错误）作为第二个值。这样，调用者就可以看到函数执行成功了。

1. 在您的 hello/hello.go 文件中，处理函数现在返回的错误 `Hello`以及非错误值。

将以下代码粘贴到 hello.go 中。

```Go
package main

import (
    "fmt"
    "log"

    "example.com/greetings"
)

func main() {
    // Set properties of the predefined Logger, including
    // the log entry prefix and a flag to disable printing
    // the time, source file, and line number.
    log.SetPrefix("greetings: ")
    log.SetFlags(0)

    // Request a greeting message.
    message, err := greetings.Hello("")// If an error was returned, print it to the console and
    // exit the program.
    if err != nil {
        log.Fatal(err)
    }

    // If no error was returned, print the returned message
    // to the console.
    fmt.Println(message)
}
```

在此代码中，您：

- 配置 `log包`以在其日志消息的开头打印命令名称（“greetings：”），而不打印时间戳或源文件信息。
- 将两个`Hello`返回值（包括 `error`）分配给变量。
- 将参数从 Gladys 的名字更改`Hello`为空字符串，以便您可以尝试错误处理代码。
- 查找非零`error`值。在这种情况下，继续下去毫无意义。
- 使用标准库中的函数`log package`输出错误信息。如果遇到错误，可以使用 `log`包中的 `Fatal函数` 打印错误并停止程序。

1. 在目录的命令行中`hello`，运行 hello.go 来确认代码是否有效。

现在您传递的是一个空名称，您将收到一个错误。

```Go
$ go run .greetings 
: 空名称
退出状态 1
```

这是 Go 中常见的错误处理：将错误作为值返回，以便调用者可以检查它。

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=MmIwZGNhYWE5NTM1ZTM1ZWEzNzJlYzQ1YjE0NTdhOTRfVFlXMkZjWTBuMDBmN1gzbXNyVDFUVHZUMjJUajFBdmdfVG9rZW46VmNMOGJNbzROb0VHRjB4T09ZaGNRN0M1bkNoXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

接下来，您将使用 Go 切片返回随机选择的问候语。下一章见!

# 回复随机问候

在本节中，将更改代码，以便它不是每次都返回一条问候语，而是返回几条预定义的问候语之一。

> **注意：本主题是从**[创建 Go 模块](https://go.dev/doc/tutorial/create-module.html)开始的多部分教程的一部分。

为此，你需要使用 Go 切片。切片类似于数组，不同之处在于其大小会随着元素的添加和删除而动态变化。切片是 Go 中最常用的类型之一。

您将添加一个小切片来包含三条问候消息，然后让您的代码随机返回其中一条消息。有关切片的更多信息，请参阅Go 博客中的 [Go 切片。](https://go.dev/blog/slices-intro)

1. 在greetings/greetings.go中，更改您的代码，使其看起来像下面这样。

```Go
package greetings

import (
    "errors"
    "fmt"
    "math/rand"
)

// Hello returns a greeting for the named person.
func Hello(name string) (string, error) {
    // If no name was given, return an error with a message.
    if name == "" {
        return name, errors.New("empty name")
    }
    // Create a message using a random format.
    message := fmt.Sprintf(randomFormat(), name)
    return message, nil
}

// randomFormat returns one of a set of greeting messages. The returned
// message is selected at random.
func randomFormat() string {
    // A slice of message formats.
    formats := []string{
        "Hi, %v. Welcome!",
        "Great to see you, %v!",
        "Hail, %v! Well met!",
    }

    // Return a randomly selected message format by specifying
    // a random index for the slice of formats.
    return formats[rand.Intn(len(formats))]
}
```

在此代码中，您：

- 添加一个`randomFormat`函数，用于返回随机选择的问候消息格式。注意， `randomFormat`以小写字母开头，因此只能在其自身包中的代码中访问（换句话说，它不会被导出）。
- 在 中`randomFormat`，声明一个`formats`具有三种消息格式的切片。声明切片时，请在括号中省略其大小，如下所示：`[]string`。这告诉 Go，切片底层数组的大小可以动态更改。
- 使用该 `math/rand包` 生成一个随机数，用于从切片中选择一个项目。
- 在中`Hello`，调用`randomFormat`函数来获取您将返回的消息的格式，然后使用该格式和 `name`值来创建消息。
- 像之前一样返回消息（或错误）。

在 hello/hello.go 中，更改您的代码，使其看起来像下面这样。

您只需将 Gladys 的名字（或者如果您愿意，可以添加其他名字）作为参数添加到`Hello`hello.go 中的函数调用中。

```Go
package main

import (
    "fmt"
    "log"

    "example.com/greetings"
)

func main() {
    // Set properties of the predefined Logger, including
    // the log entry prefix and a flag to disable printing
    // the time, source file, and line number.
    log.SetPrefix("greetings: ")
    log.SetFlags(0)

    // Request a greeting message.
    message, err := greetings.Hello("Gladys")
    // If an error was returned, print it to the console and
    // exit the program.
    if err != nil {
        log.Fatal(err)
    }

    // If no error was returned, print the returned message
    // to the console.
    fmt.Println(message)
}
```

在命令行中，在 hello 目录中，运行 hello.go 来确认代码是否正常工作。运行多次，注意问候语是否发生变化。

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=OWU1ODIxYjUwNTI4NjkyMTM2MjA4NmUwODUwMjJlYWNfck1vNGxVYTlPN1VmbVF0aFlQVUppSmhOM2Rqam5QMWpfVG9rZW46TXEyWWJnMmk1b2l4NmJ4YTJKU2NCZWFpbnNiXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

接下来，您将使用切片来问候多个人。

# 回复多人问候

在模块代码的最后修改中，您将添加对在一个请求中获取多个人的问候语的支持。换句话说，您将处理一个多值输入，然后将该输入中的值与一个多值输出配对。为此，您需要将一组名称传递给一个可以为每个名称返回问候语的函数。

> **注意：本主题是从**[创建 Go 模块](https://go.dev/doc/tutorial/create-module.html)开始的多部分教程的一部分。

但有一个问题。将`Hello`函数的参数从单个名称更改为一组名称会更改函数的签名。如果您已经发布了该`example.com/greetings` 模块，并且用户已经编写了调用的代码`Hello`，那么这种更改会破坏他们的程序。

在这种情况下，更好的选择是编写一个具有不同名称的新函数。新函数将接受多个参数。这样可以保留旧函数以实现向后兼容性。

1. 在greetings/greetings.go中，更改您的代码，使其看起来像下面这样。

```Go
package greetings

import (
    "errors"
    "fmt"
    "math/rand"
)

// Hello returns a greeting for the named person.
func Hello(name string) (string, error) {
    // If no name was given, return an error with a message.
    if name == "" {
        return name, errors.New("empty name")
    }
    // Create a message using a random format.
    message := fmt.Sprintf(randomFormat(), name)
    return message, nil
}

// Hellos returns a map that associates each of the named people
// with a greeting message.
func Hellos(names []string) (map[string]string, error) {
    // A map to associate names with messages.
    messages := make(map[string]string)
    // Loop through the received slice of names, calling
    // the Hello function to get a message for each name.
    for _, name := range names {
        message, err := Hello(name)
        if err != nil {
            return nil, err
        }
        // In the map, associate the retrieved message with
        // the name.
        messages[name] = message
    }
    return messages, nil
}

// randomFormat returns one of a set of greeting messages. The returned
// message is selected at random.
func randomFormat() string {
    // A slice of message formats.
    formats := []string{
        "Hi, %v. Welcome!",
        "Great to see you, %v!",
        "Hail, %v! Well met!",
    }

    // Return one of the message formats selected at random.
    return formats[rand.Intn(len(formats))]
}
```

在此代码中，您：

- 添加一个`Hellos`函数，其参数是一组名称，而不是单个名称。此外，将其返回类型之一从 a 更改`string`为 a `map`，以便返回映射到问候消息的名称。
- 让新`Hellos`函数调用现有 `Hello`函数。这有助于减少重复，同时保留两个函数。
- 创建一个`messages`映射，将接收到的每个名称（作为键）与生成的消息（作为值）关联起来。在 Go 中，可以使用以下语法初始化映射： 。函数会将此映射返回给调用者。有关映射的更多信息，请参阅Go 博客上的 [Go 映射实战。](https://go.dev/blog/maps)`make(map[`*`key-type`*`]`*`value-type`*`)Hellos`
- 循环遍历函数接收到的名称，检查每个名称是否为非空值，然后将每个名称与一条消息关联起来。此 `for`循环`range`返回两个值：循环中当前项的索引以及该项值的副本。由于不需要索引，因此可以使用 Go 的空白标识符（下划线）来忽略它。更多信息，请参阅《 Effective Go》中的[空白标识符](https://go.dev/doc/effective_go.html#blank)。

1. 在您的 hello/hello.go 调用代码中，传递一组名称，然后打印您返回的名称/消息映射的内容。

在 hello.go 中，更改您的代码，使其看起来像下面这样。

```Go
package main

import (
    "fmt"
    "log"

    "example.com/greetings"
)

func main() {
    // Set properties of the predefined Logger, including
    // the log entry prefix and a flag to disable printing
    // the time, source file, and line number.
    log.SetPrefix("greetings: ")
    log.SetFlags(0)

    // A slice of names.
    names := []string{"Gladys", "Samantha", "Darrin"}

    // Request greeting messages for the names.
    messages, err := greetings.Hellos(names)
    if err != nil {
        log.Fatal(err)
    }
    // If no error was returned, print the returned map of
    // messages to the console.
    fmt.Println(messages)
}
```

通过这些更改，您可以：

- 创建一个`names`包含三个名称的切片类型的变量。
- 将`names`变量作为参数传递给 `Hellos`函数。

1. 在命令行中，切换到包含 hello/hello.go 的目录，然后使用它`go run`来确认代码是否有效。

输出应该是将名称与消息关联起来的映射的字符串表示形式，类似于以下内容：

```Plain
$ go run .
map[Darrin:Hail, Darrin! Well met! Gladys:Hi, Gladys. Welcome! Samantha:Hail, Samantha! Well met!]
```

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=Zjg0NDI4ZGU3MWMzMGI4NTgzY2Y5YzZkNzMwZjExYjFfUmt3Q1FIMHkxdE5ndVM2REZpM0MzYXFVY0F0MklYektfVG9rZW46WUJ6VmJJY3U3b3ZpaDV4SmRlNmNRTjdQbm9kXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

本主题介绍了用于表示名称/值对的映射。此外，还介绍了通过为模块中的新功能或变更功能实现新函数来保持向后兼容性的理念。有关向后兼容性的更多信息，请参阅 [保持模块兼容性](https://go.dev/blog/module-compatibility)。

接下来，您将使用内置的 Go 功能为您的代码创建单元测试。

# 添加测试

现在，您已将代码稳定地保存下来（顺便说一句，做得不错），接下来添加一个测试。在开发过程中测试代码可以发现在更改代码时出现的错误。在本主题中，您将为该 `Hello`函数添加一个测试。

> **注意：本主题是从**[创建 Go 模块](https://go.dev/doc/tutorial/create-module.html)开始的多部分教程的一部分。

Go 内置的单元测试支持让您可以更轻松地进行测试。具体来说，使用命名约定、Go 的`testing`包和`go test`命令，您可以快速编写和执行测试。

1. 在greetings目录中，创建一个名为greetings_test.go的文件。
2. 文件名以 _test.go 结尾告诉`go test`命令该文件包含测试函数。
3. 在greetings_test.go中，粘贴以下代码并保存文件。

```Go
package greetings

import (
    "testing"
    "regexp"
)

// TestHelloName calls greetings.Hello with a name, checking
// for a valid return value.
func TestHelloName(t *testing.T) {
    name := "Gladys"
    want := regexp.MustCompile(`\b`+name+`\b`)
    msg, err := Hello("Gladys")
    if !want.MatchString(msg) || err != nil {
        t.Errorf(`Hello("Gladys") = %q, %v, want match for %#q, nil`, msg, err, want)
    }
}

// TestHelloEmpty calls greetings.Hello with an empty string,
// checking for an error.
func TestHelloEmpty(t *testing.T) {
    msg, err := Hello("")
    if msg != "" || err == nil {
        t.Errorf(`Hello("") = %q, %v, want "", error`, msg, err)
    }
}
```

1. 在此代码中，您：
   1. 在与您正在测试的代码相同的包中实现测试函数。
   2. 创建两个测试函数来测试该`greetings.Hello` 函数。测试函数名称采用 的形式，其中*Name*表示特定测试的内容。此外，测试函数接受指向包 [类型](https://go.dev/pkg/testing/#T)的指针作为参数。您可以使用此参数的方法从测试中报告和记录日志。 `Test`*`Name`*`testing``testing.T`
   3. 实施两个测试：
      - `TestHelloName`调用该`Hello`函数，并传递一个`name`值，该值应使函数能够返回有效的响应消息。如果调用返回错误或意外的响应消息（不包含您传入的名称），则可以使用`t`参数的 [方法](https://go.dev/pkg/testing/#T.Errorf)将消息打印到控制台。 `Errorf`
      - `TestHelloEmpty`使用空字符串调用该`Hello`函数。此测试旨在确认错误处理是否有效。如果调用返回非空字符串或没有错误，则使用`t`参数的 `Errorf 方法`将消息打印到控制台。
2. 在greetings目录的命令行中，运行 `go test命令` 执行测试。
3. 该`go test`命令执行测试文件（名称`Test`以 _test.go 结尾）中的测试函数（名称以 开头）。您可以添加`-v`标志以获取列出所有测试及其结果的详细输出。测试应该能通过。

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=ZGJmNzUxYzZlOThkMzEzMjBlYzM4NDljYmM0MjY1MDlfeFJTbFhtb2VVT1puUXpDY29UaXZSMlQ3V0YyWlF2OGVfVG9rZW46UDQzNGJBYjNDbzZOUnZ4aXQ2Q2NHSmFJbkZmXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

1. 中断该`greetings.Hello`功能以查看失败的测试。

测试`TestHelloName`函数会检查您指定为函数参数的名称的返回值`Hello`。要查看失败的测试结果，请更改函数，`greetings.Hello`使其不再包含该名称。

在greetings/greetings.go文件中，将以下代码粘贴到 `Hello`函数的位置。请注意，突出显示的行会更改函数的返回值，就像`name`参数被意外删除了一样。

```Go
// Hello returns a greeting for the named person.
func Hello(name string) (string, error) {
    // If no name was given, return an error with a message.
    if name == "" {
        return name, errors.New("empty name")
    }
    // Create a message using a random format.
    // message := fmt.Sprintf(randomFormat(), name)
    message := fmt.Sprint(randomFormat())
    return message, nil
}
```

1. 在greetings目录下的命令行中，运行`go test`即可执行测试。

这次，运行的时候`go test`不要带上这个`-v`标志。输出将仅包含失败的测试结果，这在测试数量较多时非常有用。测试`TestHelloName`应该失败，但`TestHelloEmpty`实际上仍然通过。

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=YTY5YmNmYjkzNGNjNDNjN2FiYTA2NzEzYjViMzIxNjBfa3lLRFFIakJrRDVRQlpueTFCaklkTHZKQ3lmNk1VOURfVG9rZW46SHRDSGJKekc1b3R4dFZ4R0tpU2NqRnhBbnlkXzE3NTE5ODU5NzA6MTc1MTk4OTU3MF9WNA)

在下一个（也是最后一个）主题中，您将了解如何编译和安装代码以在本地运行它。

# 编译并安装应用程序

在最后一个主题中，您将学习几个新`go`命令。虽然该`go run`命令是您在频繁更改程序时编译和运行程序的实用快捷方式，但它不会生成二进制可执行文件。

本主题介绍了两个用于构建代码的附加命令：

- 该`go build命令`编译软件包及其依赖项，但不会安装结果。
- 该`go install命令`编译并安装软件包。

> **注意：本主题是从**[创建 Go 模块](https://go.dev/doc/tutorial/create-module.html)开始的多部分教程的一部分。

1. 从 hello 目录中的命令行运行`go build` 命令将代码编译为可执行文件。

```Plain
$ go build
```

1. 从 hello 目录中的命令行运行新的`hello` 可执行文件以确认代码有效。

请注意，您的结果可能会有所不同，具体取决于您在测试后是否更改了greetings.go代码。

在 Linux 或 Mac 上：

```Plain
$ ./hello
map[Darrin:Great to see you, Darrin! Gladys:Hail, Gladys! Well met! Samantha:Hail, Samantha! Well met!]
```

在 Windows 上：

```Plain
$ hello.exe
map[Darrin:Great to see you, Darrin! Gladys:Hail, Gladys! Well met! Samantha:Hail, Samantha! Well met!]
```

您已将应用程序编译为可执行文件，因此可以运行它。但要运行它，您的提示符必须位于可执行文件的目录中，或者指定可执行文件的路径。

接下来，您将安装可执行文件，以便无需指定其路径即可运行它。

1. 发现 Go 安装路径，`go`命令将在此安装当前包。

[您可以通过运行命令](https://go.dev/cmd/go/#hdr-List_packages_or_modules) 来发现安装路径 ，如下例所示： `go list`

```Plain
$ go list -f '{{.Target}}'
```

例如，命令的输出可能会显示`/home/gopher/bin/hello`，表示二进制文件已安装到 /home/gopher/bin。下一步您将需要此安装目录。

1. 将 Go 安装目录添加到系统的 shell 路径。

这样，您将能够运行程序的可执行文件，而无需指定可执行文件的位置。

- 在 Linux 或 Mac 上，运行以下命令：

```Plain
$ export PATH=$PATH:/path/to/your/install/directory
```

- 在 Windows 上，运行以下命令：

```Plain
$ set PATH=%PATH%;C:\path\to\your\install\directory
```

另外，如果您 `$HOME/bin`的 shell 路径中已经有这样的目录，并且想要在那里安装 Go 程序，则可以 `GOBIN`通过使用以下 [命令](https://go.dev/cmd/go/#hdr-Print_Go_environment_information)设置变量来更改安装目标： `go env`

```Plain
$ go env -w GOBIN=/path/to/your/bin
```

或者

```Plain
$ go env -w GOBIN=C:\path\to\your\bin
```

1. 更新 shell 路径后，运行`go install`命令来编译和安装该包。

```Plain
$ go install
```

1. 只需输入应用程序名称即可运行。为了更有趣，请打开一个新的命令提示符，并`hello`在其他目录中运行可执行文件名称。

```Plain
$ hello
map[Darrin:Hail, Darrin! Well met! Gladys:Great to see you, Gladys! Samantha:Hail, Samantha! Well met!]
```

本 Go 教程到此结束！