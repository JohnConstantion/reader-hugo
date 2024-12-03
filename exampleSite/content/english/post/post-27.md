---
title: "redis 缓存"
date: 2024-12-03T09:36:29+08:00
# post thumb
#images:
#  - "images/blog/sheen.jpg"
#author
author: "Crucio"
# description
description: "Redis缓存穿透+缓存击穿+缓存雪崩 案例及解决方案"
# Taxonomies
categories: [ "videography","vlog" ]
tags: [ "skill","learn","java" ]
type: "regular" # available type (epic, trending, popular, or regular)
draft: false
---

### 缓存穿透

根据redis中的key查询对应的数据，在redis中查询不到对应的数据的时候，会去数据库查询对应的数据。
大量的数据库查询会拉爆数据库的线程，导致数据库宕机，这个现象就是缓存穿透。

#### 产生的原因

黑客查询大量不存在的key,导致数据库查询大量的数据。

#### 解决的方案

1、缓存空数据<br/>
2、布隆过滤器

### 缓存击穿

在redis的存储中，会有一些数据是经常查询的热点数据。
如果这个热点数据，在redis中失效，会导致大量的查询访问到数据库。
这种现象就叫缓存击穿。

#### 产生原因

缓存热点数据突然失效。

#### 解决方案
1、设置热点数据永不过时，或者是使用异步后台更新<br/>
2、采用互斥锁

### 缓存雪崩

缓存数据在同一时间点失效，导致大量请求到数据库，从而使得数据库崩溃。

#### 产生的原因

1、大量数据使用同一时间过期<br/>
2、redis故障

#### 解决方案

1、缓存数据过期时间设置为随机时间，防止同一时间大量缓存数据集体失效，导致数据库访问过大。<br/>
2、采用redis高可用架构，可将热点数据分别存放在不同缓存的数据库中，避免某一点由于压力过大而down掉<br/>
3、请求限流、熔断机制、服务降级等机制，降低服务器负载。
