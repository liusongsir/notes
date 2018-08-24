# Go基础笔记
1. GOPATH
GOPATH指定你的工作空间，windows默认是C:\Users\YourName\go。可以通过自定义工作空间，同时将GOPATH指到自定义工作路径。注意，工作空间不能和Go的安装路径（GOROOT）相同
查看GOPATH和GOROOT
C:\Users\liusong>go env GOPATH
E:\Go
C:\Users\liusong>go env GOROOT
D:\Go
为了方便，建议将%GOPATH%/bin也添加到PATH

2. go build
默认构建出的可执行文件xx.exe名称为包名。如:%GOPATH%/src/hello/world.go   在当前目录下生成hello.exe

3. go install
默认构建出的可执行文件xx.exe名称为包名。如:%GOPATH%/src/hello/world.go   hello.exe被安装到%GOPATH%/bin/下

4. package name
name为import时的最后一个名词 如import "A/B/C" 则name就是C，即package C
可执行命令的package必须为package main

