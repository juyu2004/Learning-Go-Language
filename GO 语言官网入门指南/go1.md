# Go 语言入门

## 先决条件

- **一些编程经验。**这里的代码相当简单，但了解一些函数知识会很有帮助。
- **一款用于编辑代码的工具。**任何文本编辑器都可以使用。大多数文本编辑器都对 Go 语言支持良好。最受欢迎的是 VSCode（免费）、GoLand（付费）和 Vim（免费）。
- **命令终端。Go**可以在 Linux 和 Mac 上的任何终端以及 Windows 上的 PowerShell 或 cmd 上顺利运行。

## 下载并安装 Go 语言

1. 下载连接 : https://go.dev/doc/install

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=ODkwNTAwMDM3Mzg2YWU5NDk4MTE5YTUyYmRjZjVlNTFfdHVDelF4czl3SWRMVXl5clBrTTJ2M0c5U1FnMEp4a3BfVG9rZW46SjNOV2JJdVdXb0I0dEh4aDd4UmNqcGVYbkdmXzE3NTE5MDg4NDk6MTc1MTkxMjQ0OV9WNA)

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=ZjNhYzFmMWI5NGZhNDEzMjgwNDRmNDllZmNlZGI1ZmNfRkdBdWJjT2UzbFdEcjQ0cXBFY3BZN3RGbTh4dDRLejdfVG9rZW46RFp3ZmJYNEltb1FIdjl4QVNISmNMdzNiblpmXzE3NTE5MDg4NDk6MTc1MTkxMjQ0OV9WNA)

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

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=NmRhODNhZTc1MjZlY2ZiNzQ3ODkwMGVlZjA3ZTM2MjdfaGJQSHRUckc3RUVhdlFYajdGdGRQVWFrdDFtZjVQZ1lfVG9rZW46QThxQmJDcEwzb2ZZZ3h4RDdka2N0UTdIblpjXzE3NTE5MDg4NDk6MTc1MTkxMjQ0OV9WNA)

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

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=MmZiOTlhNGQ0YjNhYzc1ZmFlNDFkMjBkYjZiMGU4ODdfaGZwdUZZQU9BSDJHV0FHUmNIWWRKaDlYUWpseFBlNFZfVG9rZW46VHFTVmJCRGVHb3JGa1d4a040NGNHOE1rblhlXzE3NTE5MDg4NDk6MTc1MTkxMjQ0OV9WNA)

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

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=MjczODgzNjIwMzdiZGNkYmQ0OTUyMGVlYjRmYjgxZWZfVHpEY21FT3A2VDNpQTV6T29KRzQyY1JWN3ZnSnhNUWNfVG9rZW46TG9DeWI0dXlnb085Mzl4alpCMmNGT1dGbmdoXzE3NTE5MDg4NDk6MTc1MTkxMjQ0OV9WNA)

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

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=NjNmOGE5YzJmYjBmN2M2YjQ1MGIyMDQ2Yzc1NjZjN2FfZzFNaWttdlhQTlJMc0s0dkZHc2xxMnBUZXpKOHNrMTFfVG9rZW46RjBrdGJvVWFlb2t1Z3V4NlhQb2NBR3BibnFoXzE3NTE5MDg4NDk6MTc1MTkxMjQ0OV9WNA)

可以设置使用国内的 Go 代理，像 [Goproxy.cn](https://goproxy.cn/) 或者阿里云代理，以此来解决连接超时的问题。在命令提示符中执行以下命令：

```Go
go env -w GOPROXY=https://goproxy.cn,direct
```

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=OTdlMjRhYjAwMWYxYTYwNjRhODc2NGEzYjhiYmIxYmZfcnhoQjVDak9EMGxIU3U4VTdXY0lmRWhFZ3JCb3pGdVZfVG9rZW46TDU4ZGI2M0Zub0FGOG14SFoyZGNCeEUwblpmXzE3NTE5MDg4NDk6MTc1MTkxMjQ0OV9WNA)

1. 运行您的代码以查看您所调用的函数生成的消息。

```Go
$ go run .
不要通过共享内存进行通信，而要通过通信来共享内存。
```

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=MGE4OTU5OWQ2MWY1ZDY2OWYxMmFlZjdkYzhjNDhkNTZfZmk0Zk54MHJaY0x4SVNnZUtqMXQ4aUZpdDRMRk9FSGJfVG9rZW46WmJnZmJvdlNnb1JGSlF4UnlGS2NCR3drblBlXzE3NTE5MDg4NDk6MTc1MTkxMjQ0OV9WNA)

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

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=YmQ5NTg4Nzc2MWEyNDZjNDI0YmFlZTI4OGFkN2JiN2NfRUc3YW5jeDZUSHBFYkNvZ05qYzJNd0NoU0hhVENJblZfVG9rZW46SWhVZGJDcGozb1h6UFB4Mld4eWNmSXRXblpnXzE3NTE5MDg4NDk6MTc1MTkxMjQ0OV9WNA)

下载好扩展

1. `greetings`为您的 Go 模块源代码 创建一个目录。
2. `go mod init使用命令` 启动您的模块 。

运行该`go mod init`命令，并指定模块路径——此处使用`example.com/greetings`。如果您发布模块，则此路径*必须*是 Go 工具可以下载模块的路径。该路径应为您的代码仓库。

有关使用模块路径命名模块的更多信息，请参阅 [管理依赖项](https://go.dev/doc/modules/managing-dependencies#naming_module)。

```Go
$ go mod init example.com/greetings 
go: 创建新的 go.mod: 模块 example.com/greetings
```

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=NTYwNjgwNWU5NmZkNzc4ZjI1ZDBlNzljZjNiNmU0ZDFfQTZUYkQwUXNJNWRENHM2NEFBS1M4SWVFa1o2b1psUW5fVG9rZW46TldrVGJhdzlGb2UyWHl4bng4R2MyVDA5bkhmXzE3NTE5MDg4NDk6MTc1MTkxMjQ0OV9WNA)

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

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=ODVmZDhkYTM2MmM2ZWIzYTVmM2NiYWNjOGQ1YjcxMjlfWWkzaHZuSGM0VDV3NVNDQXVSWjQxTEdRUnRvWDRkVTFfVG9rZW46WmF0NWJsYWFNb25yMGt4bXl2bGM0SW9jbkFnXzE3NTE5MDg4NDk6MTc1MTkxMjQ0OV9WNA)

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

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=NGY1OGViOTIxZWQzNGEyN2M5OTgwMTgxNDJhYjEzNDJfYmFGZXpzdnZxeG5oUzJVcXlDTVBEWTRyZG53cWN3VGdfVG9rZW46WEcxdmJ3cHFVb3Zsczd4TDh0MGM2dlNUblFGXzE3NTE5MDg4NDk6MTc1MTkxMjQ0OV9WNA)

1. 从 hello 目录中的命令提示符运行 [命令](https://go.dev/ref/mod#go-mod-tidy)来同步 模块的依赖项，添加代码所需但尚未在模块中跟踪的依赖项。 `go mod tidy``example.com/hello`

命令完成后，`example.com/hello` 模块的 go.mod 文件应如下所示：

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=MDRmNTQzMzIyMjIxZjBkNTEzNTIxMjJjZDk3NDI5M2JfTGNOOEdmcE94TUtMRlo1dXBTbERKODZOSlpzY3RqU0hfVG9rZW46QmhyS2JveEtjbzFTV0h4aVpZZGN5MzNybkZnXzE3NTE5MDg4NDk6MTc1MTkxMjQ0OV9WNA)

 该命令在 greets 目录中找到了本地代码，然后添加了一条`require 指令`来指定`example.com/hello` 需要的依赖项`example.com/greetings`。您`greetings`在 hello.go 中导入包时创建了此依赖项。

 模块路径后面的数字是*伪版本号* ——用来代替语义版本号（模块尚无）的生成数字。

 要引用*已发布的*模块，go.mod 文件通常会省略该`replace`指令，并 `require`在末尾使用带有标记本号的指令。

 有关版本号的更多信息，请参阅 [模块版本编号](https://go.dev/doc/modules/version-numbers)。

1. 在目录中的命令提示符下`hello`，运行您的代码以确认其有效。

```Go
go rnun .
```

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=OWZmZGVmZDQzMDMwNTRlZmY5YWU2ZjAzZDRkYzU3ZDlfVE9kMGE3YWFZTk5iZWJsWGUwdkdVdzJHTFZhZzZvTUVfVG9rZW46WHBCVmJUbHVCb0NyVGd4UXBZTmNJVzZKbmxiXzE3NTE5MDg4NDk6MTc1MTkxMjQ0OV9WNA)

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

![img](https://in4zh9vdv3.feishu.cn/space/api/box/stream/download/asynccode/?code=M2E2MDhjYWNjZmI4Y2M5NTU5MWI3ZWNmNGRhZWI1ZjVfSEJuNXdsc0pra2daVkxvandiZ0xYUXlROXlOSUNIUEdfVG9rZW46VmNMOGJNbzROb0VHRjB4T09ZaGNRN0M1bkNoXzE3NTE5MDg4NDk6MTc1MTkxMjQ0OV9WNA)

接下来，您将使用 Go 切片返回随机选择的问候语。下一章见!