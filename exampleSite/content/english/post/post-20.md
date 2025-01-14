---
title: "node版本控制器nvm的安装管理步骤"
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

## nvm 是什么？
<hr>
nvm是关于node.js的版本管理工具，可以实现多版本环境的切换，根据需求变更版本环境，解决版本不兼容的问题。安装nvm前需要清理干净node.js

### 操作步骤，系统为mac,window直接官网下载安装包。



> 该命令为消除nodejs包中的的版本强关联，从淘宝的镜像中拉取相关的包
```shell
npm install --legacy-peer-deps --registry=https://registry.npmmirror.com 
```

### nvm 相关的操作命令

>查询安装好的版本
```shell
nvm ls
```
>查询可以安装的node版本
```shell
nvm list available
```
>显示当前正在使用的版本号
```shell
nvm current
```
>安装自己需要的版本
```shell
nvm install <version>
```
>切换到需要的版本
```shell
nvm use <version>
```
>更换默认需要使用的版本号
```shell
nvm alias  default <version> 
```
>删除指定的别名
```shell
nvm unalias <name> 
```
>删除nodejs的版本号
```shell
nvm uninstall <version>
```

```shell
nvm reinstall-packages <version>
```

### 安装管理的源nrm

> 原本的npm源是国外的源，可以使用下面的方法去安装
```shell
npm install -g nrm --registry=https://mirrors.tencent.com/npm/
```
>查询可以使用的源
```shell
nrm ls 
```
>切换使用的源
```shell
nrm use huawei
```




// todo JavaMailSenderImpl 邮件类的学习


