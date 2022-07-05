
---
title: "其他目录"
linkTitle: "其他目录"
weight: 4
date: 2017-01-05
description: 
---

* GOBIN： go install 和 go get 命令在编译main package后生成的可执行文件的保存目录。如果没有设置GOBIN环境变量，可执行文件会被安装到$GOPATH/bin目录下。
* GOCACHE：在该目录中保存了go编译过程中生成的一些文件，这些文件可以被以后的编译过程重用，以加快编译过程，不用每次都从头开始编译。
* GOTMPDIR：go命令行会在该目录中写入一些临时文件。