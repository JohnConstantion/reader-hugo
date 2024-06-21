---
title: "在Junit中引入Tika类运行时显示空指针异常，容器找不到对应的类对象"
date: 2024-05-31T15:50:24+06:00
# post thumb
images:
  - "images/blog/sheen.jpg"
#author
author: "Kate Stone"
# description
description: "This is meta description"
# Taxonomies
categories: [ "videography","vlog" ]
tags: [ "code","learn","java" ]
type: "regular" # available type (epic, trending, popular, or regular)
draft: false
---

### 查询用户时redis是如何处理的

#### 单用户查询

> 查询 -> redis -> mysql
> 疑问：用户中台是否可以引入本地缓存
> 如果使用本地缓存会减少调用网络查询用户信息，减少查询redis和mysql的次数，减少负载。
> 但是也有相关的弊端，本地缓存如果存储的数据过大会对java进程产生严重的性能影响,频繁触发gc操作
> 本地缓存要是要用最好是在调用方那边使用，减少rpc的调用
<p> 结合业务来看，如果数据是热数据，代表会经常更新，过大的热数据不断更新会导致本地缓存不断触发缓存淘汰 </p>

> 用户数据在redis中存储注意的点：key不要太长（50个字符内)、存储的数据结构采用String类型、采取的序列化方式推荐FST和Kryo

#### 批量用户查询

> 存在的问题
> 是否都是热点数据？
> 批量查询会导致缓存命中率降低

> 如果是热点数据，如何批量的从缓存中查？
<p>
推荐使用redis的命令查询

```java
Redis.multiGet
```

</p>
批量查询最好是两个接口都提供出来，分别是查询缓存和直接查询数据库

### 用户信息数据更新

> 先删除Redis,再更新Mysql?
<p> 可能会导致旧数据被读入到缓存中 </p>
<p> 使用延迟双删的做法，先是删除redis,基于订阅binlog去做缓存删除操作 </p>

> 先更新Mysql,再删除Redis?
<p> 可能会导致旧数据被读入到缓存中 
    极端情况，主从数据库，主库更新好了，也删除了redis,但是从库数据没有同步，读取旧数据被放入到redis 
</p>




