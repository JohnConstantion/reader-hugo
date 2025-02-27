---
title: "本地搭建Ollama大模型"
date: 2025-02-26T13:46:13+08:00
# post thumb
images:
  - "images/blog/funingna.jpg"
#author
author: "Crucio"
# description
description: "搭建本地的ollama加载本地的大模型并关联本地的知识库"
# Taxonomies
categories: [ "ollama" ]
tags: [ "ollama" ]
type: "popular" # available type (epic, trending, popular, or regular)
draft: false
---

### Ollama 是什么？他有什么作用？
`Ollama`([官网跳转](https://ollama.com/)) 是一个可以本地运行大模型的开源框架，专为在本地计算机上高效运行大模型LLM而设计。
ollama相比其他开源软件入门更简单，只需官网下载软件即可完成安装，适合小白入门，快速完成本地大模型部署。
同时ollama也支持多种方式部署，可以格局自己的需求设置自己的专属运行模式。
>一句话：Ollama是一个简明易用的本地大模型运行框架，有点类似docker的概念。

### 本地命令行安装方式
#### 方法一：使用 Homebrew（macOS/Linux）
```bash
brew tap sullay/ollama
brew install --cask ollama
```
#### 方法二：使用docker安装（所以操作系统）
```bash
docker pull ghcr.io/sullay/ollama:latest
docker run -d --name ollama -p 11434:11434 ghcr.io/sullay/ollama:latest
```
#### 方法三：访问官网根据自己的系统类型安装对应的安装包
> [官网跳转](https://ollama.com/)

### 运行ollama
打开ollama软件，在浏览器中输入 http://127.0.0.1:11434 测试是否运行成功
```html
Ollama is running
```
页面显示代表运行成功

### ollama 如何加载大数据模型（Mac系统）
打开终端并输入命令
```bash
ollama run deepseek-r1:32b
```
ollama 下载模型会出现网速过慢的问题，根据需求修改命令提升下载速度
```bash
while true; do
    ollama run mistral-small:24b &
    CMD_PID=$!
    echo $CMD_PID
    sleep 60
    kill -9 $CMD_PID
    wait $CMD_PID 2>/dev/null
done
```


