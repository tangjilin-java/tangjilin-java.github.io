---
layout: pages
title: Markdown基本使用
date: 2019-10-31 18:19:10
tags: ["markdown"]
categories: 测试
---
# MarkDown基本使用
# 一级标题
## 二级标题
### 三级标题
- 列表1
- 列表2
 a 子列表
 b 子列表
- 列表3
<!-- more -->
[链接](http://www.abtjlwxj.club/tscommunity/)

  ![插入图片](http://img3.cache.netease.com/photo/0001/2010-03-01/60M9HDLL00AQ0001.JPG)
  
*斜体字*
**加粗字体**

`单行代码<html></html>`

```
<script>
多行代码
            var canvas = document.createElement('canvas'),
            context = canvas.getContext('2d'),
            windowW = window.screen.width ,
            windowH = window.screen.height ,
            Mx,
            My,
            paused = true;
            suzu = [];
            booms = [];
            boomks = [];
            start();

            canvas.onmousemove = function(e) {
                var loc = canvasMove(e.clientX, e.clientY);
                Mx = loc.x;
                My = loc.y
            };

            canvas.onmousedown = function() {
                creatarry(Mx, My);
                paused = !paused
            };

            function creatarry(a, b) {
                for (var i = 0; i < 100; ++i) {
                    booms[i] = {
                        x: a,
                        y: b,
                        gravity: 0.3,
                        speedX: Math.random() * 20 - 10,
                        speedY: Math.random() * 15 - 7,
                        radius: Math.random() * 15,
                        color: Math.random() * 360,
                        apc: 0.6
                    };
                    boomks.push(booms[i]);
                    if (boomks.length > 300) {
                        boomks.shift()
                    };
                    console.log(boomks)
                }
            };
	</script>
```

> 引用内容
---
横线
---