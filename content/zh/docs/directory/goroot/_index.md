
---
title: "GOPATH"
linkTitle: "GOPATH"
weight: 2
date: 2017-01-05
description: 
---

GOPATH目录是Go的工作目录，其中包含本地的项目文件，项目中引用的的第三方package，以及生成的二进制文件。

## 目录结构

Go语言工具要求GOPATH的目录结构包含bin,pkg,src三个子目录。

* bin目录下是项目编译生成的二进制文件。
* pkg目录下是项目需要依赖的一些第三方package,这些第三方package并不包含在GOROOT中pkg目录下的基础package中。例如mysql数据库驱动，web框架等。
* src目录中包含项目的源文件，以及通过go get下载的第三方package的源码。

## 通过go get下载第三方包
可以用go get命令下载第三方包，go get会将源码下载到src目录下，并编译源码生成.a 二进制文件放到pkg目录下。如果源码中包含main文件，则会生成对应的二进制文件放到bin目录中。

使用go get命令安装mysql驱动和代码规范检查工具golint

```bash
go get github.com/go-sql-driver/mysql
go get golang.org/x/lint/golint
``` 

上面的命令会下载mysql driver和golint的源码，并编译生成二进制package包，由于golint源码中包含了main方法，还会在bin目录生成对应的可执行文件。

## 目录示例

```
├── bin                               //项目生成的可执行文件和通过go get安装的可执行文件
│   ├── golint
│   └── myproject
├── pkg                               //通过go get安装的第三方包二进制文件
│   └── linux_amd64
│       ├── github.com
│       │   └── go-sql-driver
│       │       └── mysql.a
│       └── golang.org
│           └── x
│               └── lint.a
└── src                              //项目代码和通过go get安装的第三方包源码
    ├── golang.org
    │   └── x
    │       ├── lint
    │       │   ├── CONTRIBUTING.md
    │       │   ├── golint
    │       │   │   ├── golint.go
    │       │   │   ├── importcomment.go
    │       │   │   └── import.go
    │       ......                
    ├── go-sql-driver
    │   │   └── mysql
    │   │       ├── appengine.go
    │   │       ├── auth.go
	│   ......
    │
    └── myproject                   //本地项目代码
        └── myapp.go
```

## GOPATH中是否可以采用多个目录？

GOPATH可以允许设置为多个目录，多个目录之间用:(Linux)或者;(Windows)隔开。在GOPATH设置为多个目录的情况下，go get下载的第三方包会安装到第一个目录下。可以通过设置两个目录来将本地工作目录和第三方包分开：因为go get只会将通过go get下载的第三方包安装在第一个目录中，因此可以将第二个目录作为本地工作目录，以保持工作目录的整洁。