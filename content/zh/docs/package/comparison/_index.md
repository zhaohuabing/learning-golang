
---
title: "对比JAVA和Go的Package"
linkTitle: "对比JAVA和Go的Package"
weight: 2
date: 2017-01-05
description: 
---

Go语言中的package和java类似，都用于将一组相关代码组织在一起，但两个语言对packag的使用又有不同之处。本文对比go和java package的异同，以帮助java程序员更好理解go的package。

## Package声明

### Java package声明
Java文件中的package声明和其文件路径是完全一致的。package是以.分割开来的文件名。

java 文件中的package命名：

```java
package com.zhaohuabing.demo
......
```

其对应的目录结构如下：

```
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── zhaohuabing
│   │   │           └── demo
│   │   │               ├── test.java
......
```language
```

### Go package声明

Go 文件中的package声明中并没有层级结构。推荐将package名称和该package所在的源文件的目录名称保持相同。虽然这并不是强制要求，但遵循该建议会让Package的组织和使用容易很多。

```go
package demo
......
```
其对应的目录结构如下：

```language
├── src
│   ├── github.com
│   │   ├── zhaohuabing
│   │   │   └── demo
│   │   │       └── test.go
....
```

## Package引用

在引用package时，java和go都需要采用完整路径名称。但import的粒度不同，java的最小粒度是class,而go是package。

### Java package引用

Java语言模型一切皆为对象，因此在引用时以类为基本单位。在引用时要么引用一个具体的类，要么用*表示引用该package下的所有类。

```java
import com.zhaohuabing.demo.*; //import demo包下面的所有class
import java.util.list;         //import一个class
```

### Go package引用

Go语言有Struct，而且Struct也可以有成员函数，类似于Java的class。但Go并不是严格的面向对象的语言，Go的package中可以直接定义变量和函数。因此Java要求所有文件必须对应到一个类，但Go的文件和Struct之间没有必然的对应关系。

在Go语言中，只能import一个package，不能import一个Struct（类）。

```
import "github.com\zhaohuabing\demo"
```

## 源文件

### Java

在Java语言中一切皆是对象，Java中类是一等公民，一个源文件对应于一个class，而package只是class的目录，package自身不能拥有方法和变量。

这样组织的优点是代码结构非常清晰，但约束性很强，无法在package层次上定义公用的方法及变量，一个变通的方法是在一个类中使用static来定义package中的全局变量和方法。该方式又反过来打破了Java中一切皆为对象的约定，是一种为了解决问题的不得已的“丑陋”解决方案。

### Go

Go语言中package的使用更为灵活，package是一组相关Variable，Function和Struct的集合。由于可以直接在package上定义变量和方法，Go语言解决了Java中的缺点。

## 小结

Go语言中package的声明只取路径的最后一段，而引用需要采用全路径。Go语言中package声明和应用的不一致导致从java刚开始转向go的程序员比较难以理解go的package的使用。

除此以外，Go语言还有一些类似的和Java不一致的，但感觉没有必要的设计，例如函数的返回值在后面而不是前面。这些语言设计的细节不知是否为了和Java区分而故意为之？考虑到Java程序员的广大基数，如果换做是我来设计一门新的语言，我会尽量考虑遵从一些Java程序员的习惯，以吸引更多的潜在用户。

Java语言“一切皆为对象”的设计原则太过于理想化，而在解决实际问题时，一个过于理想化的方案往往是行不通的。Go语言通过Struct和Interface支持了面向对象的特性，也可以在package上定义变量和方法，比Java语言更为灵活。