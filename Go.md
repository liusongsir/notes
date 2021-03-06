### package
1. 一个包定义一组编译过的代码，包的名字类似命名空间，可以用来间接访问包内声明的标识符，这个特性可以把不同包中定义的同名标识符区别开。
2. 所有处于同一个文件夹里的代码文件，必须使用同一个包名。

### main包和main函数
main 函数保存在名为main 的包里。如果main 函数不在main 包里，构建工具就不会生成可执行的文件。另外，init函数都会在main函数执行前调用。程序编译时，会使用声明main 包的代码所在的目录的目录名作为二进制可执行文件的文件名。

### import
1. 与第三方包不同，从标准库中导入代码时，只需要给出要导入的包名。编译器查找包的时候，总是会到GOROOT 和GOPATH 环境变量引用的位置去查找。
2. import _ "github.com/user/stringutil"  这个技术是为了让Go语言对包做初始化操作，但是并不使用包里的标识符。为了让程序的可读性更强，Go 编译器不允许声明导入某个包却不使用。下划线让编译器接受这类导入，并且调用对应包内的所有代码文件里定义的init 函数
3. 标识符要么从包里公开，要么不从包里公开。当导入了一个包时，程序可以直接访问这个包中任意一个公开的标识符。这些标识符以大写字母开头。以小写字母开头的标识符是不公开的，不能被其他包中的代码直接访问。

### 函数func
func 函数名(参数名 参数类型[...])返回参数...{函数体}

### 结构体struct
type 结构体名 struct{
  结构体
}

### 接口interface
type 接口名 interface{
  方法声明
}

命名接口的时候，需要遵守Go语言的命名惯例，如果接口类型只包含一个方法，那么这个类型的名字以er 结尾


### 关键字
defer:关键字defer 会安排随后的函数调用在函数返回时才执行。这个函数一定会被调用，哪怕函数意外崩溃终止，也能保证关键字defer 安排调用的函数会被执行。
### 常用包
fmt
encoding/json
os
log
