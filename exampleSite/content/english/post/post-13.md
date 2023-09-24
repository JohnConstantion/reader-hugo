---
title: "问题收集"
date: 2023-09-04T11:02:24+06:00
# post thumb
images:
  - "images/blog/blog-11.jpg"
#author
author: "Crucio"
# description
description: "This is meta description"
# Taxonomies
categories: [ "plan","arts" ]
tags: [ "arts","plan" ]
type: "regular" # available type (epic, trending, popular, or regular)
draft: false
---

## 创建idea项目之后，maven插件报错，显示找不到对应的插件
>  Cannot resolve plugin org.apache.maven.plugins:maven-compiler-plugin:3.1.1 问题

解决方案是：
在 `maven` 安装路径下的conf文件夹下的 `settings.xml` 文件中添加如下代码

```java
<mirror> 
   <id>alimaven</id> 
   <name>aliyun maven</name> 
   <url>http://maven.aliyun.com/nexus/content/repositories/central/</url> 
   <mirrorOf>central</mirrorOf> 
  </mirror> 
  
  <mirror> 
   <id>junit</id> 
   <name>junit Address/</name> 
   <url>http://jcenter.bintray.com/</url> 
   <mirrorOf>central</mirrorOf> 
  </mirror>
  
  <mirror> 
   <id>alimaven</id> 
   <name>aliyun maven</name> 
   <url>http://central.maven.org/maven2</url> 
   <mirrorOf>central</mirrorOf> 
  </mirror> 
```

问题解决
