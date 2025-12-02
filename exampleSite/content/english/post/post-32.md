---
title: "Spring Boot 版本"
date: 2025-12-01T09:52:15+08:00
# post thumb
images:
  - "images/blog/blog-long.jpg"
#author
author: "Crucio"
# description
description: "Spring Boot 版本"
# Taxonomies
categories: [ "code" ]
tags: [ "code",“project”]
type: "popular" # available type (epic, trending, popular, or regular)
draft: false 
---
Spring Boot 的版本4有什么优化

### Spring Boot 4.0 更新

#### 一、核心依赖与环境要求
* Spring Boot 4.0 对底层依赖进行全面升级，明确最低技术基线，以适配现代Java生态和云原生需求：
  1. Java 版本：最低要求JDK17,官方强烈推荐JDK21（以解锁虚拟线程特性）及JDK25，充分利用JVM新功能提升性能。
  2. 规范基座：全面升级至Jakarta EE 11，强制要求Servlet 6.1 规范。
  3. web容器支持：仅兼容Tomcat 11.0 和 Jetty 12.1; **暂时移除Undertow支持**，Undertow目前不支持Servlet 6.1 规范，且社区维护团队人员不足，更新慢，迭代效率低。
  4. 构建工具：Maven 版本需求 3.6.3+ ，Gradle 需求 7.6.4+（推荐使用 8.14+ 或者 9.X 版本以支持原生镜像编译等新特性。）

#### 二、关键特性：性能、体验与框架三重升级


