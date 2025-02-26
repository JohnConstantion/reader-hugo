---
title: "博客项目规划"
date: 2024-12-30T11:17:30+08:00
# post thumb
images:
  - "images/blog/funingna.jpg"
#author
author: "Crucio"
# description
description: "定义一个属于自己的项目博客网站"
# Taxonomies
categories: [ "videography","blog" ]
tags: [ "skill","java" ]
type: "regular" # available type (epic, trending, popular, or regular)
draft: false
---

## TOTO:

搭建一个博客项目
前后端分离
需要的技术为Spring Boot、MySQL、Vue

### 相关模块
TODO 模块
博客正文模块
时间模块
日记模块

### docker跑deepseek模型
```shell
docker exec -it ollama ollama run deepseek-r1:14b
```

### 加速ollama下载速度
```shell
while true; do
    ollama run mistral-small:24b &
    CMD_PID=$!
    echo $CMD_PID
    sleep 60
    kill -9 $CMD_PID
    wait $CMD_PID 2>/dev/null
done
```
### RagFlow安装教程
