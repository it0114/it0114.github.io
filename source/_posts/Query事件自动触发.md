title: jQuery事件自动触发
toc: true
author: Yam
tags:
  - jQuery
categories:
  - 学习
date: 2019-03-05 23:28:00
---
# jQuery 事件自动触发
```javascript
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Title</title>
    <style>
        * {
            margin: 0;
            padding: 0;
        }

        .father {
            width: 200px;
            height: 200px;
            background: red;
        }

        .son {
            width: 100px;
            height: 100px;
            background: skyblue;
        }
    </style>
    <script src="js/jquery-1.12.4.js"></script>
    <script>
        $(function () {
            //编写jQuery代码

            // $(".son").click(function () {
            //     alert("son")
            // });
            //
            // $(".father").click(function () {
            //     alert("father");
            // });

            //自动触发事件
            // $(".father").trigger("click");
            // $(".father").triggerHandler("click");

            //注意点:
            //     如果使用trigger触发自动事件，那么会引发事件冒泡
            //     $(".son").trigger("click");
            //      如果使用triggerHandler则不会触发事件冒泡
            //     $(".son").triggerHandler("click");

            // $("input[type='submit']").click(function(){
            //     alert("submit");
            // });

            //如果利用trigger触发自动事件，那么会触发事件默认行为
            //$("input[type='submit']").trigger("click");
            //如果利用triggerHandler触发自动事件，那么则不会触动事件默认行为
            // $("input[type='submit']").triggerHandler("click");


        });
    </script>
</head>
<body>
<div class="father">
    <div class="son"></div>
</div>
<a href="https://www.it0114.xyz">我是Yam</a>
<form action="https://www.taobao.com">
    <input type="text">
    <input type="submit">
</form>
</body>
</html>
```