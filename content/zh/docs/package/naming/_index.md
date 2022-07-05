
---
title: "Package 命名"
linkTitle: ""
weight: 1
date: 2017-01-05
description: 
---

## Package声明

在go源文件的开头必须申明文件所属的package，如下所示：


```
package name
......
```

## 命名规范

* 建议package命名用小写字母
* 建议package命名必和其路径的最后一段一致（main package除外）。注意，这并不是Golang的强制要求，文件目录只是用于存放同一个package的所有源文件，Golang对目录名并无要求。但一个目录下不允许有多个package的源文件。
* main package中的main方法是可执行文件的入口，main package名一般和路径名不一致
* 不同路径下package命名可以重复，但其完整路径名必须唯一


## package 名和导入路径

package的导入路径是指从$GOPATH/src/开始的路径名。

例如 package github.com/zhaohuabing/demo 在文件系统中的路径为：$GOPATH/src/github.com/zhaohuabing/demo