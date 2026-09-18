---
title: 学习记录
date: 2026-09-18 21:36:16
tags:
---# 2026萌新计划Web - Week1 学习记录

> 本节主要学习 HTTP 协议基础、Burp Suite 抓包以及前端三件套。

## 1. HTTP 协议学习

### 1.1 GET 与 POST 请求的区别
* GET 请求通常用于获取数据，参数在 URL 中可见。
* POST 请求通常用于提交数据，参数在请求体中。

### 1.2 常见状态码
| 状态码 | 含义 |
| :--- | :--- |
| 200 | 请求成功 |
| 302 | 重定向 |
| 403 | 禁止访问 |
| 404 | 未找到 |
| 500 | 服务器内部错误 |

## 2. Burp Suite 初体验

### 2.1 抓取浏览器请求

### 2.2 常用模块功能
1. **Proxy**: 拦截和修改请求。
2. **Repeater**: 重放请求。

## 3. 本地 Flask 登录页面实战

### 3.1 后端代码 (app.py)
https://imgchr.com/i/pnMkJJK
https://imgchr.com/i/pnMkGi6
https://imgchr.com/i/pnMk3Ix
```python
from flask import Flask, request, render_template

app = Flask(__name__)

@app.route('/login', methods=['POST'])
def login():
    # 你的代码
    pass
