---
title: "查看目录"
linkTitle: "查看目录"
weight: 1
description: 
---

在操作系统中安装Go语言编译环境后，有几个需要注意的重要目录，包括GOROOT,GOPATH和GOBIN等。

可以使用 ```go env```命令查看Go环境变量，包含这几个目录对应的环境变量。

```bash
 $ go env
GOARCH="amd64"
GOBIN=""
GOCACHE="/home/huabing/.cache/go-build"
GOEXE=""
GOFLAGS=""
GOHOSTARCH="amd64"
GOHOSTOS="linux"
GOOS="linux"
GOPATH="/home/huabing/go"
GOPROXY=""
GORACE=""
GOROOT="/usr/local/go"
GOTMPDIR=""
GOTOOLDIR="/usr/local/go/pkg/tool/linux_amd64"
GCCGO="gccgo"
CC="gcc"
CXX="g++"
CGO_ENABLED="1"
GOMOD=""
CGO_CFLAGS="-g -O2"
CGO_CPPFLAGS=""
CGO_CXXFLAGS="-g -O2"
CGO_FFLAGS="-g -O2"
CGO_LDFLAGS="-g -O2"
PKG_CONFIG="pkg-config"
GOGCCFLAGS="-fPIC -m64 -pthread -fmessage-length=0 -fdebug-prefix-map=/tmp/go-build688094926=/tmp/go-build -gno-record-gcc-switches"
```