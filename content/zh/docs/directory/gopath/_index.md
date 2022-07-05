
---
title: "GOROOT"
linkTitle: ""
weight: 3
date: 2017-01-05
description: 
---

GOROOT是Go的安装目录。Go安装程序会自动设置$GOROOT环境变量，一般不需要手动进行设置。

Linux下GOROOT的缺省目录为 /usr/local/go/，其目录结构如下所示。可以看到，GOROOT目录中包含了go命令行和go语言自带的一些基础包，如io，net，math等。在安装后，GOROOT目录中的内容不会变化。

```
├── bin                            //go命令行二进制
│   ├── go
│   ├── godoc
│   └── gofmt                            
├── pkg                            //go标准库的package二进制包，如io，net，math等。
│   ├── include
│   ├── linux_amd64
│   │   ├── archive
│   │   │   ├── tar.a
│   │   │   └── zip.a
│   │   ├── bufio.a
│   │   ├── bytes.a
│   │   ├── compress
│   │   │   ├── bzip2.a
│   │   │   └── ......
│   └── tool
├── src                           //go标准库源文件，如io，net，math等。
│   ├── archive
│   │   ├── tar
│   │   │   ├── common.go
│   │   │   ├── example_test.go
│   │   │   └── ......
│   ├── bufio
│   ├── builtin
│   ├── bytes
│   ├── ......
│   └── unsafe
└── ......
```


