---
title: "MarkDown语法"
date: 2024-10-22T17:58:03+08:00
# post thumb
#images:
#  - "images/blog/blog-2.jpg"
#author
author: "Crucio"
# description
description: "This is meta description"
# Taxonomies
categories: [ "videography","vlog" ]
tags: [ "food","vlog","nice" ]
type: "regular" # available type (epic, trending, popular, or regular)
draft: false
---

### UML 图

sequenceDiagram
张三 ->> 李四: 你好！李四, 最近怎么样?
李四-->>王五: 你最近怎么样，王五？
李四--x 张三: 我很好，谢谢!
李四-x 王五: 我很好，谢谢!
Note right of 王五: 李四想了很长时间, 文字太长了<br/>不适合放在一行.

李四-->>张三: 打量着王五...
张三->>王五: 很好... 王五, 你怎么样?

---

### 甘特图

gantt
dateFormat  YYYY-MM-DD
title Adding GANTT diagram functionality to mermaid
section 现有任务
已完成               :done,    des1, 2014-01-06,2014-01-08
进行中               :active,  des2, 2014-01-09, 3d
计划中               :         des3, after des2, 5d

---

###  flow 流程图

lowchat
st=>start: 开始
e=>end: 结束
op=>operation: 我的操作
cond=>condition: 确认？

st->op->cond
cond(yes)->e
cond(no)->op

---

### Mermaid 类图

graph LR
A[长方形] -- 链接 --> B((圆))
A --> C(圆角长方形)
B --> D{菱形}
C --> D

---



