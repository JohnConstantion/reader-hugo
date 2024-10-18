---
title: "git的使用方法收集"
date: 2024-10-18T10:06:36+08:00
# post thumb
#images:
#  - "images/blog/blog-long.jpg"
#author
author: "Crucio"
# description
description: "git使用方法"
# Taxonomies
categories: [ "git" ]
tags: [ "skill" ]
type: "regular" # available type (epic, trending, popular, or regular)
draft: false
---

##### 项目设定提交的用户姓名和邮箱
```shell
# 全局设定
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
# 当前项目设定
cd path/to/your/project
git config user.name "Your Name"
git config user.email "your_email@example.com"

# 查询全局设定提交的用户名和邮箱
git config --global user.name
git config --global user.email
# 查询当前项目设定提交的用户名和邮箱
cd path/to/your/project
git config user.name
git config user.email

# 查询所有的配置信息
git config --list
```
