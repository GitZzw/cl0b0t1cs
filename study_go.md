# go

>>> https://golang.google.cn/doc/tutorial/getting-started
>>> https://blog.csdn.net/chenggong2dm/article/details/49364691

>> gopath rootpath不一样

`go get -u url`
>> go get 在gopath路径下安装库


`go env`
>> 查看go环境

`go mod init hello`  
>> go: creating new go.mod: module hello
>> 初始化一个新模块以跟踪依赖关系
  go.mod: 可以理解为包管理文件
  go.sum: 可以理解为包的版本控制文件

``  
package main
import "fmt"
func main() {
    fmt.Println("Hello, World!")
}
``

>> 声明一个主程序包（程序包是一种对功能进行分组的方法，它由同一目录中的所有文件组成）。
导入流行的fmt软件包，该软件包包含用于格式化文本（包括打印到控制台）的功能。 该软件包是安装Go时获得的标准库软件包之一。
实现主要功能，以将消息打印到控制台。 默认情况下，运行主程序包时将执行主功能。

`go run .`
>> 编译并运行命令源码文件

`go build`
>> 编译并生成可执行文件

`go mod tidy`
>> 配置相关程序包


### go 结构体 tag(埋坑)
