# 《go语言圣经》笔记

## 入门

**hello world：**

```go
package main

import "fmt"

func main() {
	fmt.Println("Hello world...")
}

```

- 如果不是go单个文件，程序运行的是main包下的某个.go文件的main函数
- .go文件的名字不一定为main.go
- package名字一定是main
- 一个包下只能有一个.go文件有main函数
- `go run`等于`go build`+运行

**for循环几种形式：**

```go
for i := 1; i < len(os.Args); i++ {}	
for condition {}//相当于while
for {}//相当于 while(true)
for _, arg := range os.Args {}//用_的本质原因是go不允许被赋值的变量不使用
```

- ``var a`` + ``a=1`` = ``a:=1``通过右边的参数类型决定等号左边的类型

**4种赋值操作**

```go
s := "" 
var s string 
var s = "" 
var s string = ""
```

- map遍历go做了随机处理

## 声明

关键字

![image-20220605155116621](.\pic\image-20220605155116621.png)



```go
package ch2

import "fmt"

const BoilingF = 212.0 	//整个包都能用
func PrintBoiling(){
	fmt.Print(BoilingF)
}
```

以下两种等价：

```go
//注意，new()是一个函数，不是关键字
func newInt1() *int {
	return new(int)
}
func newInt2()*int {
	var dummy int
	return &dummy
}
```

## 复合数据类型

数组：

```
q := [...]int{1, 2, 3}
q := [3]int{1, 2, 3}
```

## init()和main()

![img](.\pic\SouthEast)