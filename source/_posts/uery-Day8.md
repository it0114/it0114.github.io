title: jQuery-Day8
toc: true
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-02-25 20:59:00
---
# 过滤器
 ```javascript
 	<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        div{
            padding: 5px;
            margin-bottom: 2px;
            background: rgba(0,0,0,.1);
        }
    </style>
    <script src="js/jquery-1.12.4.js"></script>
    <script>
        $(function () {
            //编写jQuery代码
            //先找到最外层，然后找里面的
            $(".grandpa")
                .find(".child")
                .css("border","2px solid #999");
            //用子元素找父元素
            $("#child1")
                .parent()
                .css("border","2px solid #666");
            //用子元素找父级中带.grandpa的元素
            $("#child1")
                .parents(".grandpa")
                .css("border","2px solid #333");
            //找到元素中带有.not-gay的元素，单独设置
            $(".child")
                .filter(".not-gay")
                .css("background","red");
        })
    </script>
</head>
<body>

<div class="grandpa">
    <div class="pa">
        <div id="child1" class="child not-gay"></div>
        <div id="child2" class="child"></div>
    </div>
</div>

</body>
</html>
 ```



![upload successful](https://img.haote.com/upload/news/image/20180717/20180717144625_95316.jpg)