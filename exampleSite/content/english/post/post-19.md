---
title: "The Design Files - Homes Minimalist"
date: 2020-03-14T15:40:24+06:00
# post thumb
images:
  - "images/blog/blog-2.jpg"
#author
author: "Kate Stone"
# description
description: "This is meta description"
# Taxonomies
categories: ["videography","vlog"]
tags: ["food","vlog","nice"]
type: "epic" # available type (epic, trending, popular, or regular)
draft: false
---
在Junit中引入Tika类运行时显示空指针异常，容器找不到对应的类对象

## 出问题的代码编写格式
```java
   @Autowired
   private Tika tika;

    @Test
    public void tika() throws TikaException, IOException {
        Path path = Paths.get("/Users/johnconstantine/Downloads/John/", "《发呆改变世界》沃玛（一次小练习）.pdf");
        File file = path.toFile();
        String parse = tika.parseToString(file);
        System.out.println(parse);
    }
```
>> 在测试运行爆出异常信息为：java.lang.NullPointerException: Cannot invoke "org.apache.tika.Tika.parseToString(java.io.File)" 
   该原因是找不到相关容器bean所以注解里获取的是空值

## 解决的方案为
```java
    @Test
    public void tika() throws TikaException, IOException {
        Tika tika = new Tika();
        Path path = Paths.get("/Users/johnconstantine/Downloads/John/", "《发呆改变世界》沃玛（一次小练习）.pdf");
        File file = path.toFile();
        String parse = tika.parseToString(file);
        System.out.println(parse);
    }
```
>> 因为相关的容器无法注入，所以最简洁的解决方案是直接在方法内创建新的对象，这样就可以直接找到，无需容器去寻找对应的对象再注入到容器内。
