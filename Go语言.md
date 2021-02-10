# Go

##### Go 语言环境安装

##### https://www.runoob.com/go/go-environment.html



1.当标识符（包括常量、变量、类型、函数名、结构字段等等）以**一个大写字母开头，如：Group1**，那么使用这种形式的标识符的对象就可以被外部包的代码所使用（客户端程序需要先导入这个包），这被称为**导出（像面向对象语言中的 public）**；标识符如果以**小写字母**开头，则**对包外是不可见**的，但是他们在整个包的内部是可见并且可用的（像面向对象语言中的 private ）。

2.[go build 和 go run区别](https://www.cnblogs.com/guojiayi/p/10464151.html)

## go run

简化了 golang 程序先编译后执行的操作。

例如：

```
go run main.go
```

可以直接运行 golang 程序。但是与 go build 再执行不同的是，不会产出可执行文件。

非常适合本地开发调试。

## go build

编译 golang 程序，但是不执行。

例如：

go build main.go

会生成可执行文件 main。需要手动执行

```
./main
```

## go run 前需要 go build 么？

不需要

![img](https://i.loli.net/2021/02/09/gEpLJaIMhodOzfD.png)

3.关键字

下面列举了 Go 代码中会使用到的 25 个关键字或保留字：

| break    | default     | func   | interface | select |
| -------- | ----------- | ------ | --------- | ------ |
| case     | defer       | go     | map       | struct |
| chan     | else        | goto   | package   | switch |
| const    | fallthrough | if     | range     | type   |
| continue | for         | import | return    | var    |

除了以上介绍的这些关键字，Go 语言还有 36 个预定义标识符：

| append | bool    | byte    | cap     | close  | complex | complex64 | complex128 | uint16  |
| ------ | ------- | ------- | ------- | ------ | ------- | --------- | ---------- | ------- |
| copy   | false   | float32 | float64 | imag   | int     | int8      | int16      | uint32  |
| int32  | int64   | iota    | len     | make   | new     | nil       | panic      | uint64  |
| print  | println | real    | recover | string | true    | uint      | uint8      | uintptr |

程序一般由关键字、常量、变量、运算符、类型和函数组成。

程序中可能会使用到这些分隔符：括号 ()，中括号 [] 和大括号 {}。

程序中可能会使用到这些标点符号：.、,、;、: 和 …。