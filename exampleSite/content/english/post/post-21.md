---
title: "注解解释合集"
date: 2024-09-03T02:51:38+06:00
# post thumb
images:
  - "images/blog/sheen.jpg"
#author
author: "Crucio"
# description
description: "This is meta description"
# Taxonomies
categories: [ "videography","vlog" ]
tags: [ "code","learn","java" ]
type: "regular" # available type (epic, trending, popular, or regular)
draft: false
---

##### java中的 @Serial 注解是什么意思

> @Serial 是java中的预定义注解，用于指定类的序列化版本号。它可以用来确保在反序列化的时候，序列化对象的版本号与反序列化对象的版本匹配，避免因版本不匹配而导致的反序列化失败的问题。

<hr>

Java中，当一个类被序列化的时，会自动生成一个序列化版本号（serialVersionUID），用于确定该类的序列化版本。
在反序列化时，Java虚拟机会比较序列化对象的serialVersionUID和反序列化对象的serialVersionUID是否一致，如果不一致，则会抛出InvalidClassException异常，
因此，为了避免这种异常的发生，可以使用@Serial注解来指定类的序列化版本号，以确保序列化对象和反序列化对象的版本一致

```java
import java.io.Serializable;
public class User implements Serializable {
    @Serial // 指定序列化版本号
    private static final long serialVersionUID = 1L;
    
    private String name;
    private int age;
    
    // 构造函数、getter和setter方法省略
}
```

<hr>

##### @EqualsAndHashCode(callSuper = true)

> 是lombok库中的一个注解，用于自动生成equals()和hashCode()方法；callSuper字段是指该类是否继承调用父类的方法，默认情况下属性为false,如果有相应的需求，就设定为true。
