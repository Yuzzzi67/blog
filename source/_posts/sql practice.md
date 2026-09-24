---
title: 练习
date: 2026-09-24 22:00:00
tags:sql
---
前情提要：上次的CTFHub页面无回显，所以我选择了PortSwigger

第一关；UNION攻击之查看隐藏数据
（利用SQL注入，让网站显示未发布的隐藏商品）
1.寻找注入点：点击分类gifts
2.观察URL：发现地址栏变成了
![9](/img/9.jpg)
3.构造Payload:在URL末尾加上单引号和注释符
4.然后就发现了隐藏商品
![10](/img/10.jpg)
漏洞原理：后台 SQL 为 SELECT * FROM products WHERE category = 'Gifts' AND released = 1。
Payload Gifts'-- 闭合了原查询，并用 -- 注释掉了 AND released = 1，所以隐藏商品暴露

第二关：确定列数
1.随便找了个分类，测试列数第一次
![11](/img/11.jpg)
页面正常，说明列数至少为2
2.测试第二次
![12](/img/12.jpg)
页面还是正常，说明列数至少为3
3.测试第三次
![13](/img/13.jpg)
报错了，说明超出列数
4.结论：当前查询返回的字段数为3
漏洞原理：ORDER BY 用于按列排序，当数字超过实际列数时数据库报错。这次通过4报错，3正常推出当前查询返回的字段数为3


